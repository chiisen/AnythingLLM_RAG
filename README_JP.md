# AnythingLLM_RAG
AnythingLLM RAG - 独自のオンプレミス AI カスタマーサービスシステム、AI ナレッジベースシステム、AI スマートアシスタント、AI エキスパートロボットを構築。

![AnythingLLM](./images/AnythingLLM.png)

[View in English](./README_EN.md) | [切換到中文](./README.md)

# RAG
RAG は「検索拡張生成」（Retrieval-Augmented Generation）を表し、「データ検索」と「生成AI」を組み合わせた技術です。  
大規模言語モデル（LLM）が質問に答える前に、外部知識ベース（企業内部データなど）から関連情報を検索し、  
これらの最新で正確なデータを生成された応答に統合することで、回答の正確性と信頼性を向上させ、LLM の情報の古さと幻覚生成の問題を解決します。

## RAG の動作方式
- 検索（Retrieval）： ユーザーが質問を提出すると、システムはまず外部知識ベース（文書、データベースなど）から関連情報を検索します。
- 拡張（Augmentation）： 検索された情報を元の質問と組み合わせて、より豊かで具体的なプロンプトを形成します。
- 生成（Generation）： 大規模言語モデル（LLM）がこの拡張されたプロンプトを使用して最終的な答えを生成します。

## RAG の主な利点
- 正確性と時効性の向上： 回答内容が最新の特定データに基づいていることを保証し、訓練時の静的データのみに依存することを避けます。
- コスト効率： 大規模言語モデル全体を再訓練する巨大なコストを避け、追加の知識ベースを提供するだけで済みます。
- ユーザー信頼の向上： 回答の出典を提供でき、ユーザーが情報を追跡・検証できるため、信頼感を高めます。
- 制御可能性の提供： 開発者は知識源を制御・更新でき、機密情報へのアクセスを制限して、AI の応答を企業ニーズにより適合させることができます。

## 応用シナリオ
- 企業内部知識管理： 従業員が会社内部文書やポリシーに関する正確な答えを迅速に取得できるようにします。
- カスタマーサービス： チャットボットが最新の製品情報やよくある質問に基づいて正確な応答を提供できるようにします。
- 意思決定支援システム： 最新データに基づく推奨事項と分析を提供します。

# インストール
ターミナルまたはコマンドプロンプトで、AnythingLLM の Docker イメージをプルします：
```bash
docker pull mintplexlabs/anythingllm
```
ターミナルまたはコマンドプロンプトで、以下のコマンドを入力して AnythingLLM の Docker コンテナを起動します：
```bash
docker run -d -p 3001:3001 mintplexlabs/anythingllm
```

# 起動
ブラウザを開き、ブラウザのアドレスバーに http://localhost:3001 を入力すると、anythingllm アプリケーションの Web インターフェースが表示されます。

# オンプレミス LLM のインストール
ターミナルまたはコマンドプロンプトで、Ollama の Docker イメージをプルします：
```bash
docker pull ollama/ollama
```
ターミナルまたはコマンドプロンプトで、以下のコマンドを入力して Ollama の Docker コンテナを起動します：
- CPU のみ
```bash
docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama
```
- Nvidia GPU
Nvidia GPU を使用するには、多くのツールライブラリのインストールが必要で、こちらは公式サイトで言及されているため、ここでは詳しく説明しません。
```bash
docker run -d --gpus=all -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama
```

# RAG サンプルの作成（テキストファイルを例として）
![RAG_TXT](./images/RAG_TXT.png)  
あなたのプライベート RAG テキストファイルを作成します。  

# RAG ファイルのインポート
![RAG_IMPORT](./images/RAG_IMPORT.png)  
以前に作成した RAG テキストファイルをインポートします。  

# ブラウザで AnythingLLM ウェブページにアクセス
![RAG_AnythingLLM](./images/RAG_AnythingLLM.png)  
ブラウザを開き、ブラウザのアドレスバーに `http://localhost:3001` を入力すると、AnythingLLM アプリケーションの Web インターフェースが表示されます。  

# RAG の情報を取得し、情報応答を生成
![RAG_ASK](./images/RAG_ASK.png)  
