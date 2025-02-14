# 会話APIのドキュメント

## ベースURL: `/conversations/`

## エンドポイント

### 1. 会話の作成
- **エンドポイント**: `/conversations/`
- **メソッド**: `POST`
- **リクエストボディ**:
  - **型**: `CreateConversationRequest`
  - **説明**: 会話を作成するために必要な詳細情報を含みます。
  - **スキーマ**:
    ```json
    {
      "user_id": "string",           // 会話を作成するユーザーの一意の識別子
      "title": "string",             // 会話のタイトル
      "status": "ConversationStatus", // 会話のステータス (active, archived, deleted)
      "project_ids": ["string"]      // 会話に関連付けられたプロジェクトIDのリスト
    }
    ```
- **レスポンス**:
  - **型**: `CreateConversationResponse`
  - **説明**: 作成された会話の詳細を返します。
  - **スキーマ**:
    ```json
    {
      "message": "string",          // 確認メッセージ
      "conversation_id": "string"   // 作成された会話の一意の識別子
    }
    ```
- **リクエスト例**:
    ```json
    {
      "user_id": "user123",
      "title": "新しい会話",
      "status": "active",
      "project_ids": ["project1", "project2"]
    }
    ```
- **レスポンス例**:
    ```json
    {
      "message": "会話が正常に作成されました。",
      "conversation_id": "123"
    }
    ```
- **可能なステータスコード**:
  - `201 Created`: 会話が正常に作成されました。
  - `400 Bad Request`: 無効な入力データ。
  - `500 Internal Server Error`: 予期せぬサーバーエラー。

### 2. 会話情報の取得
- **エンドポイント**: `/conversations/{conversation_id}/info/`
- **メソッド**: `GET`
- **パスパラメータ**:
  - **conversation_id**: `string` - 会話の一意の識別子。
- **レスポンス**:
  - **型**: `ConversationInfoResponse`
  - **説明**: 指定された会話に関する情報を返します。
  - **スキーマ**:
    ```json
    {
      "id": "string",               // 会話の一意の識別子
      "title": "string",            // 会話のタイトル
      "status": "ConversationStatus", // 会話の現在のステータス
      "project_ids": ["string"],    // 会話に関連付けられたプロジェクトIDのリスト
      "created_at": "datetime",     // 会話が作成されたタイムスタンプ
      "updated_at": "datetime",     // 会話が最後に更新されたタイムスタンプ
      "total_messages": "int"       // 会話内のメッセージ総数
    }
    ```
- **レスポンス例**:
    ```json
    {
      "id": "123",
      "title": "新しい会話",
      "status": "active",
      "project_ids": ["project1", "project2"],
      "created_at": "2024-08-24T12:00:00Z",
      "updated_at": "2024-08-24T12:05:00Z",
      "total_messages": 5
    }
    ```
- **可能なステータスコード**:
  - `200 OK`: 会話情報の取得に成功。
  - `404 Not Found`: 会話が見つかりません。
  - `500 Internal Server Error`: 予期せぬサーバーエラー。

### 3. 会話メッセージの取得
- **エンドポイント**: `/conversations/{conversation_id}/messages/`
- **メソッド**: `GET`
- **パスパラメータ**:
  - **conversation_id**: `string` - 会話の一意の識別子。
- **クエリパラメータ**:
  - **start**: `int` - メッセージの開始インデックス。デフォルトは`0`。
  - **limit**: `int` - 返すメッセージの最大数。デフォルトは`10`。
- **レスポンス**:
  - **型**: `List[MessageResponse]`
  - **説明**: 指定された会話のメッセージのリストを返します。
- **レスポンス例**:
    ```json
    [
      {
        "id": "msg1",
        "content": "こんにちは！",
        "sender": "user1",
        "timestamp": "2024-08-24T12:01:00Z"
      },
      {
        "id": "msg2",
        "content": "やあ！",
        "sender": "user2",
        "timestamp": "2024-08-24T12:02:00Z"
      }
    ]
    ```
- **可能なステータスコード**:
  - `200 OK`: メッセージの取得に成功。
  - `404 Not Found`: 会話が見つかりません。
  - `500 Internal Server Error`: 予期せぬサーバーエラー。

### 4. メッセージの投稿
- **エンドポイント**: `/conversations/{conversation_id}/message/`
- **メソッド**: `POST`
- **パスパラメータ**:
  - **conversation_id**: `string` - 会話の一意の識別子。
- **リクエストボディ**:
  - **型**: `MessageRequest`
  - **説明**: 送信するメッセージの内容を含みます。
- **レスポンス**:
  - **型**: `StreamingResponse`
  - **説明**: 投稿されたメッセージのレスポンスをストリーミングします。
- **リクエスト例**:
    ```json
    {
      "content": "これは新しいメッセージです。"
    }
    ```
- **可能なステータスコード**:
  - `200 OK`: メッセージの投稿に成功。
  - `400 Bad Request`: 無効なメッセージ内容。
  - `404 Not Found`: 会話が見つかりません。
  - `500 Internal Server Error`: 予期せぬサーバーエラー。

### 5. 最後のメッセージの再生成
- **エンドポイント**: `/conversations/{conversation_id}/regenerate/`
- **メソッド**: `POST`
- **パスパラメータ**:
  - **conversation_id**: `string` - 会話の一意の識別子。
- **レスポンス**:
  - **型**: `MessageResponse`
  - **説明**: 再生成された最後のメッセージを返します。
- **レスポンス例**:
    ```json
    {
      "id": "msg1",
      "content": "これは再生成されたメッセージです。",
      "sender": "user1",
      "timestamp": "2024-08-24T12:03:00Z"
    }
    ```
- **可能なステータスコード**:
  - `200 OK`: 最後のメッセージの再生成に成功。
  - `404 Not Found`: 会話が見つかりません。
  - `500 Internal Server Error`: 予期せぬサーバーエラー。

### 6. 会話の削除
- **エンドポイント**: `/conversations/{conversation_id}/`
- **メソッド**: `DELETE`
- **パスパラメータ**:
  - **conversation_id**: `string` - 会話の一意の識別子。
- **レスポンス**:
  - **型**: `dict`
  - **説明**: 会話の削除を確認します。
- **レスポンス例**:
    ```json
    {
      "message": "会話が正常に削除されました。"
    }
    ```
- **可能なステータスコード**:
  - `200 OK`: 会話の削除に成功。
  - `404 Not Found`: 会話が見つかりません。
  - `500 Internal Server Error`: 予期せぬサーバーエラー。

### 7. 生成の停止
- **エンドポイント**: `/conversations/{conversation_id}/stop/`
- **メソッド**: `POST`
- **パスパラメータ**:
  - **conversation_id**: `string` - 会話の一意の識別子。
- **レスポンス**:
  - **型**: `dict`
  - **説明**: 生成プロセスが停止されたことを確認します。
- **レスポンス例**:
    ```json
    {
      "message": "生成が正常に停止されました。"
    }
    ```
- **可能なステータスコード**:
  - `200 OK`: 生成の停止に成功。
  - `404 Not Found`: 会話が見つかりません。
  - `500 Internal Server Error`: 予期せぬサーバーエラー。

## スキーマ定義

### CreateConversationRequest
- **説明**: 新しい会話を作成するためのリクエストボディ。
- **フィールド**:
  - `user_id` (string): 会話を作成するユーザーの一意の識別子。
  - `title` (string): 会話のタイトル。
  - `status` (ConversationStatus): 会話のステータス（例：active, archived）。
  - `project_ids` (List[string]): 会話に関連付けられたプロジェクトIDのリスト。

### CreateConversationResponse
- **説明**: 作成された会話のレスポンスボディ。
- **フィールド**:
  - `message` (string): 成功を示す確認メッセージ。
  - `conversation_id` (string): 作成された会話の一意の識別子。

### ConversationInfoResponse
- **説明**: 会話に関する情報を含むレスポンスボディ。
- **フィールド**:
  - `id` (string): 会話の一意の識別子。
  - `title` (string): 会話のタイトル。
  - `status` (ConversationStatus): 会話の現在のステータス。
  - `project_ids` (List[string]): 会話に関連付けられたプロジェクトIDのリスト。
  - `created_at` (datetime): 会話が作成されたタイムスタンプ。
  - `updated_at` (datetime): 会話が最後に更新されたタイムスタンプ。
  - `total_messages` (int): 会話内のメッセージ総数。
