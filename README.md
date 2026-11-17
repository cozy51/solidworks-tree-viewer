# SOLIDWORKS 構成ツリービューア

SOLIDWORKSからエクスポートしたアセンブリ構成CSVを、ブラウザ上で階層ツリーとして表示する静的Webアプリです。

## 使い方

1. `index.html` をブラウザで開く（または公開ページを利用する）。
2. 「CSVを追加」から構成ツリーCSVを選択する。
3. フォルダ・モデルを展開し、検索や詳細表示を利用する。
4. 必要ならJSONでダウンロードする。

## CSV形式

必須列: `NodeId, ParentId, NodeType, Order, FolderName, ModelName`

推奨列: `Level, FolderPath, ComponentType, FilePath, Configuration, Suppressed, AssemblyName`

ノードは `ParentId` で親子関係を表します。`NodeType` は `folder` または `component`、`ComponentType` は `part` または `assembly` を想定しています。

## プライバシー

- CSVはブラウザ内で解析し、サーバーへ送信しません。
- 実際のCAD構成データ、ファイルパス、部品番号などの業務情報を**公開GitHubリポジトリにアップロードしないでください**。
- Google Drive保存・認証機能は未実装です。
- SOLIDWORKS本体やCADモデルの変更は行いません。

## 公開

GitHub Pagesなら、リポジトリの Settings → Pages で `main` ブランチのルートを公開元に設定できます。
