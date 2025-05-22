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
環境変数でAzureやデータストアの設定が必要です。プロジェクトルートに`.env`ファイルを作成し、以下のキーを設定してください。

| Key | 説明 | 参照ファイル |
| --- | --- | --- |
| `AZURE_VOICE_ENDPOINT` | Azure Speech サービスのエンドポイント | `api/main.py` |
| `AZURE_VOICE_KEY` | Azure Speech サービスのキー | `api/main.py` |
| `AZURE_IMAGE_ENDPOINT` | DALL·E 画像生成エンドポイント | `api/agent/agents.py` |
| `AZURE_IMAGE_API_KEY` | DALL·E API キー | `api/agent/agents.py` |
| `SUSTINEO_STORAGE` | 画像保存用 Azure Blob Storage | `api/main.py`, `api/agent/agents.py` |
| `COSMOSDB_CONNECTION` | Cosmos DB 接続文字列 | `api/main.py`, `api/voice/common.py` |
| `FOUNDRY_CONNECTION` | Azure AI Project (Foundry) の接続情報 | `api/agent/common.py` |
| `LOCAL_TRACING_ENABLED` | ローカルでのトレーシングを有効化するか | `api/main.py` |

`.env` は以下のようになります。
```env
AZURE_VOICE_ENDPOINT=<endpoint>
AZURE_VOICE_KEY=<key>
AZURE_IMAGE_ENDPOINT=<endpoint>
AZURE_IMAGE_API_KEY=<key>
SUSTINEO_STORAGE=<storage_url>
COSMOSDB_CONNECTION=<connection_string>
FOUNDRY_CONNECTION=<connection_string>
LOCAL_TRACING_ENABLED=false
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
