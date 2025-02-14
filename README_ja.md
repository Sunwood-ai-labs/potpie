<p align="center">
  <a href="https://potpie.ai?utm_source=github">
    <img src="https://github.com/user-attachments/assets/1a0b9824-833b-4c0a-b56d-ede5623295ca" width="318px" alt="Momentum logo" />
  </a>
</p>

<br/>
<p align="center">
<a href="https://trendshift.io/repositories/12918" target="_blank"><img src="https://trendshift.io/api/badge/repositories/12918" alt="potpie-ai%2Fpotpie | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/></a>
</br>
  <br />
  <a href="https://app.potpie.ai" rel="dofollow">アプリ</a> | <a href="https://docs.potpie.ai" rel="dofollow">ドキュメンテーション</a> | <a href="https://docs.potpie.ai/open-source"  rel="dofollow">APIリファレンス</a> | <a href="https://app.potpie.ai/newchat?repo=potpie-ai/potpie&branch=main" rel="dofollow">🥧リポジトリとチャット</a>
  <br />
</p>

<p align="center">
  <a href="https://github.com/potpie-ai/potpie/blob/main/LICENSE">
    <img src="https://img.shields.io/github/license/potpie-ai/potpie" alt="Apache 2.0">
  </a>

  <a href="https://github.com/potpie-ai/potpie">
    <img src="https://img.shields.io/github/stars/potpie-ai/potpie" alt="GitHub Repo stars">
  </a>
</br>

<a href="https://discord.gg/ryk5CMD5v6">
    <img src="https://img.shields.io/badge/Join%20our-Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="Join our Discord">
</a>
</br>
<a href="https://twitter.com/intent/tweet?text=I%20created%20custom%20engineering%20agents%20for%20my%20codebase%20in%20minutes%20with%20potpie.ai%20@potpiedotai%20!🥧">
    <img alt="tweet" src="https://img.shields.io/twitter/url/http/shields.io.svg?style=social">
</a>
</p>

<h1 align="center">
Prompt-To-Agent: コードのためのカスタムエンジニアリングエージェントを作成
</h1>

Potpieは、コードベースに特化したAIエージェントを作成するオープンソースプラットフォームです。これにより、コードの自動分析、テスト、および開発タスクが可能になります。Potpieのエージェントは、コードの包括的なナレッジグラフを構築することで、複雑な関係を理解し、デバッグから機能開発まであらゆることを支援できます。

<p align="center">
<img width="1506" alt="Screenshot 2025-01-09 at 2 18 18 PM" src="https://github.com/user-attachments/assets/a400b48f-dc4c-47b1-a42b-26eaf062adb2" />
</p>

## 📚 目次
- [🥧 Potpieを選ぶ理由](#why-potpie)
- [🤖 プリビルドエージェント](#prebuilt-agents)
- [🛠️ ツール](#potpies-tooling-system)
- [🚀 はじめに](#getting-started)
- [💡 ユースケース](#use-cases)
- [🛠️ カスタムエージェント](#custom-agents-upgrade)
- [🗝️ APIキーによるエージェントへのアクセス](#accessing-agents-via-api-key)
- [🎨 Potpieをカスタマイズ](#make-potpie-your-own)
- [🤝 貢献](#contributing)
- [📜 ライセンス](#license)
- [💪 貢献者](#-thanks-to-all-contributors)

## 🥧 Potpieを選ぶ理由
- 🧠 **深いコード理解**: 組み込みのナレッジグラフがコードコンポーネント間の関係を把握
- 🤖 **プリビルド＆カスタムエージェント**: 一般的なタスクに対応するすぐに使えるエージェントと、独自のエージェントを構築可能
- 🔄 **シームレスな統合**: 既存の開発ワークフローと連携
- 📈 **柔軟性**: あらゆる規模または言語のコードベースに対応

## 🔌 VSCode拡張機能
PotpieのAIエージェントの力を、VSCode拡張機能で開発環境に直接取り込みます。

- **直接統合**: エディターから離れることなく、すべてのPotpieエージェントにアクセス
- **クイックセットアップ**: [VSCode Marketplace](https://marketplace.visualstudio.com/items?itemName=PotpieAI.potpie-vscode-extension)から直接インストール
- **シームレスなワークフロー**: 質問、説明の取得、提案の実装をコードの記述場所で直接実行

## 🤖 Potpieのプリビルドエージェント
Potpieは、ソフトウェア開発の主要な側面を自動化および最適化するための、特殊なコードベースエージェントのスイートを提供します。

- **デバッグエージェント**: スタックトレースを自動的に分析し、コードベースに固有のデバッグ手順を提供します。
- **コードベースQ&Aエージェント**: コードベースに関する質問に答え、関数、機能、およびアーキテクチャを説明します。
- **コード変更エージェント**: コードの変更を分析し、影響を受けるAPIを特定し、マージ前に改善を提案します。
- **統合テストエージェント**: コンポーネントが適切に連携するように、フローの統合テスト計画とコードを生成します。
- **ユニットテストエージェント**: テストカバレッジを強化するために、個々の関数のユニットテスト計画とコードを自動的に作成します。
- **LLDエージェント**: このエージェントに機能要件を提供することにより、新機能を実装するためのローレベル設計を作成します。
- **コード生成エージェント**: 新機能のコードを生成し、既存のコードをリファクタリングし、最適化を提案します。

## 🛠️ Potpieのツールシステム
Potpieは、エージェントがナレッジグラフおよび基盤となるインフラストラクチャと対話するために使用できる一連のツールを提供します。

- **get\_code\_from\_probable\_node\_name**: 可能性のあるノード名に基づいてコードスニペットを取得します。
- **get\_code\_from\_node\_id**: 特定のノードIDに関連付けられたコードを取得します。
- **get\_code\_from\_multiple\_node\_ids**: 複数のノードIDのコードスニペットを同時に取得します。
- **ask\_knowledge\_graph\_queries**: ベクトル類似性検索を実行して、関連情報を取得します。
- **get\_nodes\_from\_tags**: 特定のキーワードでタグ付けされたノードを取得します。
- **get\_code\_graph\_from\_node\_id/name**: 特定のノードのコードグラフ構造を取得します。
- **change\_detection**: デフォルトブランチと比較して、現在のブランチの変更を検出します。
- **get\_code\_file\_structure**: コードベースのファイル構造を取得します。

## 🚀 はじめに

### 前提条件
- Dockerがインストールされ、実行されていること
- OpenAI APIキー
- Gitがインストールされていること（リポジトリアクセス用）
- Python 3.10.x

### セットアップ手順

**Python 3.10をインストール**
   - 公式PythonウェブサイトからPython 3.10をダウンロードしてインストールします。
     https://www.python.org/downloads/release/python-3100/

1. **環境を準備**
   - `.env.template`に基づいて`.env`ファイルを作成します。
   - 以下の必須構成を追加します。
      ```bash
      isDevelopmentMode=enabled
      ENV=development
      OPENAI_API_KEY=<your-openai-key>
      POSTGRES_SERVER=postgresql://postgres:mysecretpassword@localhost:5432/momentum
      NEO4J_URI=bolt://127.0.0.1:7687
      NEO4J_USERNAME=neo4j
      NEO4J_PASSWORD=mysecretpassword
      REDISHOST=127.0.0.1
      REDISPORT=6379
      BROKER_URL=redis://127.0.0.1:6379/0
      CELERY_QUEUE_NAME=dev
      defaultUsername=defaultuser
      PROJECT_PATH=projects #リポジトリは、システム上のこのパスにダウンロード/クローンされます。
      ```
   - Python 3.10を使用して仮想環境を作成します。
      ```bash
      python3.10 -m venv venv
      source venv/bin/activate
      ```
      または、`virtualenv`ライブラリを使用することもできます。

    - venvに依存関係をインストールします。
      ```bash
      pip install -r requirements.txt
      ```

2. **Potpieを起動**
   ```bash
   chmod +x start.sh
   ./start.sh
   ```

3. **認証設定** (開発モードではこのステップをスキップ)
   ```bash
   curl -X POST 'http://localhost:8001/api/v1/login' \
     -H 'Content-Type: application/json' \
     -d '{
       "email": "your-email",
       "password": "your-password"
     }'
   # 後続のリクエストのために、レスポンスからベアラートークンを保存します
   ```

4. **リポジトリの解析を初期化**
   ```bash
   # 開発モードの場合:
   curl -X POST 'http://localhost:8001/api/v1/parse' \
     -H 'Content-Type: application/json' \
     -d '{
       "repo_path": "path/to/local/repo",
       "branch_name": "main"
     }'

   # 本番モードの場合:
   curl -X POST 'http://localhost:8001/api/v1/parse' \
     -H 'Content-Type: application/json' \
     -d '{
       "repo_name": "owner/repo-name",
       "branch_name": "main"
     }'
   # レスポンスからproject_idを保存します
   ```

5. **解析ステータスを監視**
   ```bash
   curl -X GET 'http://localhost:8001/api/v1/parsing-status/your-project-id'
   # 解析が完了するまで待ちます
   ```

6. **利用可能なエージェントを表示**
   ```bash
   curl -X GET 'http://localhost:8001/api/v1/list-available-agents/?list_system_agents=true'
   # 使用するagent_idをメモします
   ```

7. **会話を作成**
   ```bash
   curl -X POST 'http://localhost:8001/api/v1/conversations/' \
     -H 'Content-Type: application/json' \
     -d '{
       "user_id": "your_user_id",
       "title": "My First Conversation",
       "status": "active",
       "project_ids": ["your-project-id"],
       "agent_ids": ["chosen-agent-id"]
     }'
   # レスポンスからconversation_idを保存します
   ```

8. **エージェントとの対話を開始**
   ```bash
   curl -X POST 'http://localhost:8001/api/v1/conversations/your-conversation-id/message/' \
     -H 'Content-Type: application/json' \
     -d '{
       "content": "質問またはリクエストをここに"
     }'
   ```

9. **会話履歴を表示** (オプション)
   ```bash
   curl -X GET 'http://localhost:8001/api/v1/conversations/your-conversation-id/messages/?start=0&limit=10'
   ```

## 💡 ユースケース

- **オンボーディング**: コードベースに慣れていない開発者にとって、コードベースQ&Aエージェントは、コードベースを理解し、迅速に追いつくのに役立ちます。新しいプロジェクトのセットアップ方法、テストの実行方法などを質問します。
> Potpieを使用して[**AgentOps**](https://github.com/AgentOps-AI/AgentOps)コードベースにオンボーディングを試みたところ、うまくいきました：ビデオ[こちら](https://youtu.be/_mPixNDn2r8)。

- **コードベースの理解**: 統合しているライブラリに関する質問に答え、関数、機能、およびアーキテクチャを説明します。
> Q&Aエージェントを使用して、公式ドキュメントに記載されていない[**CrewAI**](https://github.com/CrewAIInc/CrewAI)コードベースの機能の基盤となる動作を理解しました：ビデオ[こちら](https://www.linkedin.com/posts/dhirenmathur_what-do-you-do-when-youre-stuck-and-even-activity-7256704603977613312-8X8G)。

- **ローレベル設計**: コードを記述する前に、新機能または改善のための詳細な実装計画を取得します。
> [**Portkey-AI/Gateway**](https://github.com/Portkey-AI/Gateway)プロジェクトのオープンな課題をこのエージェントにフィードして、ローレベル設計を生成しました：ビデオ[こちら](https://www.linkedin.com/posts/dhirenmathur_potpie-ai-agents-vs-llms-i-am-extremely-activity-7255607456448286720-roOC)。

- **コード変更のレビュー**: 変更の機能的な影響を理解し、変更の爆発半径を計算します。
> ここでは、[**mem0ai/mem0**](https://github.com/mem0ai/mem0)コードベースからのPRを分析し、その爆発半径を理解します：ビデオ[こちら](https://www.linkedin.com/posts/dhirenmathur_prod-is-down-three-words-every-activity-7257007131613122560-o4A7)。

- **デバッグ**: スタックトレースとコードベースのコンテキストに基づいて、ステップバイステップのデバッグガイダンスを取得します。

- **テスト**: コードベースの構造と目的を理解する、コンテキストを認識したユニットおよび統合テスト計画とテストコードを生成します。

## 🛠️ カスタムエージェント [アップグレード ✨](https://potpie.ai/pricing)

カスタムエージェントを使用すると、反復可能なタスクを正確に処理するパーソナライズされたツールを設計できます。主要なコンポーネントは次のとおりです。
- **システム指示**: エージェントのタスク、目標、および期待される出力を定義します
- **エージェント情報**: エージェントの役割とコンテキストに関するメタデータ
- **タスク**: ジョブ完了のための個々のステップ
- **ツール**: ナレッジグラフのクエリまたはコードの取得のための関数

## 🗝️ APIキーによるエージェントへのアクセス

APIキーを使用してPotpieエージェントにアクセスし、CI/CDワークフローやその他の自動化されたプロセスへの統合を可能にすることができます。詳細な手順については、[Potpie APIドキュメント](https://docs.potpie.ai/agents/api-access)を参照してください。

- **APIキーの生成**: 安全なアクセスのためにAPIキーを簡単に作成します。
- **リポジトリの解析**: Parse APIを使用してコードリポジトリを分析し、プロジェクトIDを取得します。
- **解析ステータスの監視**: 解析リクエストのステータスを確認します。
- **会話の作成**: プロジェクトIDとエージェントIDを使用して、特定のエージェントとの会話を開始し、会話IDを取得します。
- **メッセージの送信**: 会話内でメッセージを送信して、エージェントと通信します。

## 🎨 Potpieをカスタマイズ

Potpieは、柔軟でカスタマイズ可能になるように設計されています。独自のデプロイメントをパーソナライズするための主要な領域を次に示します。

### 1. システムプロンプトの構成
`app/modules/intelligence/prompts/system_prompt_setup.py`でプロンプトを変更します

### 2. 新しいエージェントの追加
`app/modules/intelligence/agents/chat_agents`および`app/modules/intelligence/agents/agentic_tools`で新しいエージェントを作成します

### 3. エージェントの動作のカスタマイズ
`app/modules/intelligence/agents`ディレクトリ内の各エージェントのプロンプト内のガイドラインを変更します

### 4. ツールの統合
`app/modules/intelligence/tools`ディレクトリでツールを編集または追加します

## 🤝 貢献

貢献を歓迎します！貢献するには：
1. リポジトリをフォークします
2. 新しいブランチを作成します (`git checkout -b feature-branch`)
3. 変更を加えます
4. コミットします (`git commit -m 'Add new feature'`)
5. ブランチにプッシュします (`git push origin feature-branch`)
6. プルリクエストを開きます

詳細については、[貢献ガイド](./contributing.md)を参照してください。

## 📜 ライセンス

このプロジェクトは、Apache 2.0ライセンスの下でライセンスされています - 詳細については、[LICENSE](LICENSE)ファイルを参照してください。

## 💪 すべての貢献者に感謝します

Potpieの構築にご協力いただきありがとうございます。これからもよろしくお願いします🥂

<img src="https://contributors-img.web.app/image?repo=potpie-ai/potpie" alt="Contributors"/>
