# Global / Workspace Rules for Memory MCP Integration

## 🧠 常時 Memory MCP 読み込み・参照ルール (Mandatory Always-On Rule)

1. **セッション・対話開始時の Memory 自動読み込み (Always Active)**:
   - ユーザーとのすべてのやり取り（特に個人嗜好、過去のプロジェクト `Anigma`、コンテキスト `3z_at` / サズアト、タスク管理に関わる内容）において、回答を構築する前に **必ず Memory MCP (`call_mcp_tool` 経由で `memory/read_graph` または `memory/search_nodes`) を実行し、ナレッジグラフを読み込んで最新のコンテキストを取得してください。**
   - 会話が始まった段階で、最新のナレッジをメモリからインポートしてコンテキストに反映させた上で対話を行ってください。

2. **Memory MCP への知識自動蓄積・更新**:
   - 会話中に得られたサズアト (3z_at) の新しい決定事項、技術的知見、プロジェクトの進捗、新しい嗜好・思想などは、セッション内または会話の区切りで Memory MCP (`create_entities`, `add_observations`, `create_relations`) を使用して自動的に更新・同期してください。

## 🔍 調査・検索の必須化ルール (Mandatory Search Rule)

- **不明点・不確実な情報の必須検索 (Mandatory Search on Unknowns)**:
  - わからないこと、不確実な点、疑問点、最新の仕様や文脈について少しでも曖昧さがある場合は、推測や思い込みで回答・判断せず、**毎回必ず Web 検索 (`search_web`) やコードベース/ファイル検索などを実行し、ファクトと最新情報を確認した上で対応してください。**
- **製品・ハードウェア・サービス情報の検索徹底 (Product Information Priority)**:
  - **マイク、ガジェット、ハードウェア、ソフトウェア製品、サービス仕様等の「製品系」の話題・選定・比較・推論においては、知識だけに頼らず毎回必ず最新の Web 検索 (`search_web`) を実行し、最新の製品情報、価格、評価、スペック、発売状況などの最新ファクトを確認した上で回答してください。**



## 📘 Notion Personal/glossary 自動更新ルール (Mandatory Notion Sync Rule)

- **新用語・知見の Notion 自動追加・同期**:
  - 会話中やプロジェクト進行において、新しい専門用語、概念、技術決定事項、アーキテクチャ思想、個人ルールなどが定義・提示された場合、Memory MCP への記録と並行して、Notion 上の `Personal/glossary` ページ（または Notion 側の対象グロッサリーページ）へ Notion MCP を使用して自動的に用語と解説を追記・同期してください。

## 🏥 ヘルスケア・健康データ参照ルール (Healthcare Data Routing Rule)

- **健康・生体・運動データの問い合わせ時の自動参照**:
  - ユーザーから健康状態、睡眠、歩数、心拍数（RHR / 最高 / 最低 / 心拍ゾーン）、HRV（心拍変動）、ストレス、消費カロリー、運動・アクティビティ履歴などの「健康・ヘルスケア」に関する質問や話題があった場合は、必ず ディレクトリ配下のレポート（***/***/*.md`、年別 `Personal/Healthcare/YYYY/README.md`、月別 `Personal/Healthcare/YYYY/YYYY-MM/README.md`、日別 `Personal/Healthcare/YYYY/YYYY-MM/YYYY-MM-DD.md`）を参照し、該当ファイルへのリンクやデータを提示して回答を作成してください。

