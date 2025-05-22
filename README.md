# sustineo

## 概要
sustineoは個人向けAIアシスタントを実装するサンプルプロジェクトです。
FastAPIによるAPIとReactによるWebクライアントで構成します。

## フォルダ構成
```
api/    - FastAPIバックエンド
web/    - Reactフロントエンド
```

## Quick Start
1. リポジトリをクローン
   ```bash
   git clone <repo_url>
   cd sustineo
   ```
2. Python環境を準備
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   pip install -r api/requirements.txt
   ```
3. Node依存をインストール
   ```bash
   cd web
   npm install
   ```
4. APIサーバーを起動
   ```bash
   uvicorn api.main:app --reload
   ```
5. Webサーバーを起動
   ```bash
   cd web
   npm run dev
   ```

## Requirements
- Python 3.11 以上
- Node.js 22 以上

## Setup
環境変数でAzure関連の設定が必要です。`.env`に以下を記入します。
```
AZURE_VOICE_ENDPOINT=<endpoint>
AZURE_VOICE_KEY=<key>
```

## Run / Build Commands
- 開発: `uvicorn api.main:app --reload` と `npm run dev`
- ビルド: `cd web && npm run build`

## Testing
現在自動テストはありません。`npm run typecheck`で型検査します。

## Deployment / CI
デプロイやCIの設定は未定です。将来追加予定です。

## Troubleshooting
依存のインストールに失敗する場合はNodeやPythonのバージョンを確認します。

## Contributing
Issueを立ててからPull Requestを送ってください。画像は `docs/img` に保存します。

## License
本プロジェクトはMITライセンスです。
