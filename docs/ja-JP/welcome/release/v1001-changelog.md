# v1.0：2024-04-28

## v1.0 マイルストーン

3 年の歳月を経て、NocoBase は初のメジャーバージョンアップを迎え、バージョン番号が 0.x から 1.0 にアップグレードされました。これは新しいマイルストーンです。

- 0.x 段階では、コア API と機能が急速に変化し、新しいバージョンごとに互換性のない変更がある可能性がありました。
- 1.x 段階では、コア API が基本的に安定し、NocoBase は安定性を維持しながら新しいプラグインを追加し、安全性とパフォーマンスを最適化していきます。

## 新機能

- テーマエディタでページやポップアップの内側の余白、ブロック間の余白、ブロックの角の丸みを設定できるようになりました。
- ブロック追加時にデータテーブルのフィルタリングをサポートします。
- 関係データのソートをサポートします。
- データの可視化インタラクションが改善されました。
- モバイル端末でのチャートブロック追加をサポートします。
- チャートフィルターブロックでフィールドデータ範囲の設定をサポートします。
- より多くの変数を追加しました。[詳細を見る](https://docs-jp.nocobase.com/handbook/ui/variables)
- ポップアップ内で任意のデータテーブルのブロックを追加できるようになりました。
- ワークフロー機能として、「操作後イベント」が関係ブロック内のボタンをトリガーとしてサポートします。
- ポップアップ内のデータが変更された場合、ポップアップを閉じると自動的に上位コンテナのデータが更新されます。
- テーブルブロックのパフォーマンスが大幅に向上しました。
- テストカバレッジが大幅に向上しました。

## 新プラグイン

- フィールド: Markdown(Vditor)

  - Markdown を保存し、Vditor エディタでレンダリングを行います。リスト、コード、引用などの一般的な Markdown 構文をサポートし、画像や音声のアップロードも可能です。また、即時レンダリングが可能で、見たままの編集ができます。

- コメント

  - コメント用のデータテーブルテンプレートとブロックを提供し、任意のデータテーブルのデータにコメント機能を追加します。

## 完全な更新履歴
<details>
<summary>完全な履歴を見る</summary>

- feat(plugin-workflow): 同期後にリストを更新 <u>#4177</u>
- feat(plugin-workflow): タイトル上にワークフローキーをツールチップとして表示 <u>#4178</u>
- test(plugin-workflow): テストケースを追加 <u>#4199</u>
- chore: APIキャッシュ制御ヘッダー <u>#4203</u>
- feat: ローカルから vditor の依存関係を読み込む <u>#4190</u>
- test: 数字の区切り文字テスト <u>#4204</u>
- fix: 数値フィールドは区切り設定をサポートする必要があります <u>#4197</u>
- fix(plugin-workflow): 体験を洗練する <u>#4195</u>
- chore: インポートおよびエクスポートの警告文を最適化 <u>#4196</u>
- refactor: 外部データソースコレクションマネージャー <u>#4193</u>
- fix: 環境バグ <u>#4191</u>
- fix: 関連フィールドの空のオペレーター <u>#4189</u>
- chore: e2e テストを追加 <u>#4184</u>
- fix: vditor のバージョン <u>#4183</u>
- refactor: フォームデータテンプレートのロケール改善 <u>#4188</u>
- test: 自動テストを追加 <u>#4098</u>
- chore: データソースロガーインスタンス <u>#4181</u>
- chore: 関連リポジトリでデータベースインスタンスを取得 <u>#4179</u>
- chore: 変数用の e2e テストを追加 <u>#4152</u>
- chore: コレクションのデバッグメッセージを定義 <u>#4176</u>
- chore: ビューコレクションの unsupportedFields <u>#4155</u>
- feat: プラグインフィールドマークダウン vditor を追加 <u>#4065</u>
- fix: バルク編集フォームの acl アクションエラー <u>#4166</u>
- fix: 関連フィールドで uuid 外部キーを自動作成 <u>#4160</u>
- fix(plugin-fm): 混乱を招くサイズ制限ヒントを修正 <u>#4153</u>
- fix(users): users:updateProfile の改善 <u>#4162</u>
- fix(client): API URL を取得 <u>#4161</u>
- feat: plugin-ui-routes-storage を削除 <u>#4140</u>
- fix: cytoscape のバージョンをロック <u>#4158</u>
- refactor: コレクションテンプレートの presetFieldsDisabled サポート <u>#4159</u>
- fix: グリッドスキーマ <u>#4157</u>
- client ユニットテスト <u>#4150</u>
- fix: 対象キーが主キーでない多対多の関連を更新 <u>#4146</u>
- refactor: フォームデータテンプレートのロケール改善 <u>#4148</u>
- fix(database): 配列フィールドの列名 <u>#4110</u>
- test: アクション e2e テストでリフレッシュ <u>#4147</u>
- fix(custom-request): コンテンツタイプの設定をサポート <u>#4144</u>
- chore: 現在のレコード変数をフォームから非推奨にする <u>#4063</u>
- feat(Theme): トークンをいくつか追加 <u>#4137</u>
- fix(client): 警告をいくつか修正 <u>#4143</u>
- style: tableActionColumn スタイルを改善 <u>#4138</u>
- fix: actionBar スタイルを改善 <u>#4123</u>
- chore: 削除競合時の警告メッセージ <u>#4141</u>
- fix(plugin-workflow-manual): 担当者がいないときにノードを通過させることを許可 <u>#4139</u>

</details>

## プラグインの変更

以下のプラグインは、オープンソース版を提供しなくなりました（すでに本番環境で使用しているユーザーは、アップグレードのためにお問い合わせください）。

- @nocobase/plugin-auth-cas：CASプロトコルを使用して認証を行います。
- @nocobase/plugin-auth-odic：OIDC（OpenID Connect）プロトコルを使用して認証を行います。
- @nocobase/plugin-auth-saml：SAML 2.0を使用して認証を行います。

以下のプラグインは廃止され、近日中に削除される予定です。

- @nocobase/plugin-audit-logs：廃止されましたが、すぐには削除されず、新しい版にはインストールされません。
- @nocobase/plugin-snapshot-field：廃止されましたが、すぐには削除されず、新しい版にはインストールされません。
- @nocobase/plugin-charts：@nocobase/plugin-data-visualizationに置き換えられます。
- @nocobase/plugin-excel-formula-field：@nocobase/plugin-field-formulaに置き換えられます。
- @nocobase/plugin-math-formula-field：@nocobase/plugin-field-formulaに置き換えられます。
- @nocobase/plugin-ui-routes-storage：廃止され、フロントエンドルーティングはフロントエンドで直接拡張できます。

完全なプラグインリストについては、次のリンクをご覧ください：[https://cn.nocobase.com/plugins-cn.html](https://cn.nocobase.com/plugins-cn.html)

## コードコメント

より良い開発体験を提供するために、いくつかの特別なAPIにコメントを追加しました。

- `@internal` は、コード内の内部実装の詳細や内部メソッドを示すために使用されます。これらのメソッドや機能は公共の使用のためには設計されておらず、コード内部での使用のために存在します。
- `@experimental` は、実験的な機能やAPIを示すために使用されます。このAPIはまだ開発とテストの段階にあり、大きな変更が加わる可能性があり、将来的なバージョンで削除または置き換えられる可能性があります。
- `@deprecated` は、コード内で時代遅れまたは推奨されない機能、メソッド、またはAPIを示すために使用されます。これは、まだ使用可能ですが、将来的なバージョンで削除される可能性があるか、より良い代替案が利用可能であることを意味します。

## ライセンス契約

NocoBaseはAGPL-3.0および商業ライセンスの二重ライセンスです。詳細については[NocoBaseライセンス契約](https://cn.nocobase.com/agreement-cn.html)をご覧ください。

## アップグレードガイド

- アップグレード前に必ずデータベースをバックアップしてください！データベースのバックアップは必須です！
- プロジェクト全体のコードもバックアップすることをお勧めします。

Auth: CAS、Auth: OIDC、Auth: SAMLの3つのSSOプラグインがオープンソースコードから削除されたため、アップグレードは2つのケースに分けられます。

### SSOプラグインを使用していない場合

[一般的な方法](https://docs-jp.nocobase.com/welcome/getting-started/upgrading)に従って、通常通りアップグレードしてください。

### SSOプラグインを使用している場合

以下の手順に従ってアップグレードしてください：

#### 1. アプリをアップグレード

[NocoBaseアップグレード概要](/welcome/getting-started/upgrading)を参照し、NocoBaseを最新バージョンにアップグレードしてください。

以前にCAS、OIDC、SAMLプラグインを有効にしていた場合、アップグレード時に以下のメッセージが表示されます：

コマンドラインアップグレード時のターミナルメッセージ：

![20240428212151](https://static-docs.nocobase.com/20240428212151.png)

Docker版のインターフェースメッセージ：

![20240428194926](https://static-docs.nocobase.com/20240428194926.png)

#### 2. プラグインを削除するか、プラグインの1.0バージョンを取得するか？

***プラグインを削除してアップグレードを続行する場合：***

指示に従ってプラグインを削除します。

```bash
# メインアプリ
yarn pm remove cas oidc saml --force
# サブアプリの場合は --app パラメータを追加
yarn pm remove cas oidc saml --force --app=sub-app1
```

アップグレードを続行します。

```bash
yarn nocobase upgrade
```

***プラグインを1.0バージョンに更新する場合***

NocoBaseチームに連絡してプラグインの1.0バージョンを取得し、アップグレードを続行してください。

#### 3. CAS、OIDC、SAMLプラグインのアップグレードプロセス

この時、アプリケーションのインターフェースにはアクセスできなくなるため、手動でアップグレードを行う必要があります。

1. アカウントを使用してビジネスユーザーサービスプラットフォームにログインし、最新のプラグインをダウンロードします。
2. プラグインを指定されたディレクトリに解凍します。
    - CAS プラグインは `./storage/plugins/@nocobase/plugin-auth-cas` に解凍してください。
    - OIDC プラグインは `./storage/plugins/@nocobase/plugin-auth-oidc` に解凍してください。
    - SAML プラグインは `./storage/plugins/@nocobase/plugin-auth-saml` に解凍してください。
3. アプリケーションをアップグレードします。
    - Docker バージョンの場合は、コンテナを再起動するだけです。
    - ソースコードまたは create-nocobase-app バージョンの場合
        1. 依存関係をダウンロードします：`yarn install`
        2. アップグレードコマンドを実行します：`yarn nocobase upgrade`
        3. アプリケーションを再起動します。

