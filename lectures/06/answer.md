# 第6回 解答

## 演習

<!-- [tool call] の行は、表示された行をそのまま貼り付けてください。終わらなかった STEP は、空欄のままでかまいません。 -->

- STEP 1 のツールの名前：MCP サーバー
- STEP 2 の [tool call]：glossary_search_glossary({'query': '3レベル'})
- STEP 3 の [tool call]：fetch_fetch({'url': 'https://modelcontextprotocol.io/'})
- STEP 4 の [tool call]：aws_aws___search_documentation({'topics': ['general'], 'search_phrase': 'Amazon S3 バージョニング 概要'})
- 気づき・疑問：
サーバーの設定、接続が以外に簡単だと思いました。
## 宿題

<!-- 基礎・実装・発展のどれか1つに取り組めば完了です。 -->

- 取り組んだレベル：基礎
- やったこと：
- app/mcp_server.pyを開き　# TODO(宿題・基礎): get_lecture_summary も公開しよう
server.tool()(tools.get_lecture_summary)　を追加しました
- 結果：
- [server] glossary: コマンドで起動（uv run python -m app.mcp_server）
[server] fetch: コマンドで起動（uvx mcp-server-fetch==2026.11.11 --no-readability-js）
[server] aws: URL に接続（https://knowledge-mcp.global.api.aws）
[model] gemini-3.5-flash-lite
[tools] MCP サーバー（app/mcp_servers.json）
第2回では、**「ファインチューニングとLoRA」**をテーマに学びます。

主な内容は以下の通りです：

1. **事前学習とファインチューニングの違い**
   - ファインチューニングが向く場面（出力形式、口調、特定タスクの振る舞い）と向かない場面の理解。
2. **SFT（教師あり微調整）**
   - 入力と望ましい出力のペアを使った学習と、データの質・形式の重要性。
3. **PEFTとLoRA**
   - 全パラメータを更新せず、低ランク行列（LoRA）だけを学習することでGPUメモリや容量を大幅に削減する仕組み。
   - 主なハイパーパラメータ（ランク $r$、学習率、エポック数）や過学習への注意。
4. **QLoRAとの関係**
   - モデルを4bit量子化してLoRAを適用する方法（発展内容）。
5. **演習**
   - Google Colab上で小さなモデルを架空FAQデータでLoRA学習させ、学習前後でのJSON出力の遵守率や正解率を比較します。

関連する回：第2回

--- trace ---
[tool call]   glossary_get_lecture_summary({'lecture': 2})
[tool return] glossary_get_lecture_summary -> # 第2回 ファインチューニングとLoRA

## この回のねらい

- 事前学習とファインチューニングの違い、ファインチューニングが向く場面と向かない場面を理解する
- LoRAの考え方を理解し、Google Colab上で小さなモデルを…
[usage] 入力 5,942 tokens / 出力 280 tokens / モデル応答 2 回

- 気づき・疑問：
一行の追加によって変更できる点、簡素化されていることに驚きました。
