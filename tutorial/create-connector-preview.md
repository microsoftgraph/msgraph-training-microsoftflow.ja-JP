<!-- markdownlint-disable MD002 MD041 -->

この演習では、フローまたは Azure ロジックアプリで使用できる新しいカスタムコネクタを作成します。 Open API 定義ファイルには、Microsoft Graph `$batch`エンドポイントの正しいパスと、簡易インポートを有効にするための追加設定があらかじめ用意されています。

テキストエディターを使用して、という名前`MSGraph-Delegate-Batch.swagger.json`の新しい空のファイルを作成し、次のコードを追加します。

[!code-json[](../LabFiles/MSGraph-Delegate-Batch.swagger.json)]

ブラウザーを開き、[ [Microsoft Flow](https://flow.microsoft.com)] に移動します。 Office 365 テナント管理者アカウントでサインインします。 右上の歯車アイコンを選択し、ドロップダウンメニューの [**カスタムコネクタ**] 項目を選択します。

![Microsoft Flow のドロップダウンメニューのスクリーンショット](./images/flow-conn1.png)

[**カスタムコネクタ**] ページの右上にある [**カスタムコネクタの作成**] リンクを選択し、ドロップダウンメニューの [開いている**API ファイルをインポート**する] 項目を選択します。

 ![Microsoft Flow の [カスタムコネクタの作成] ドロップダウンメニューのスクリーンショット](./images/flow-conn2.png)

[ `MS Graph Batch Connector` **カスタムコネクタ名**] テキストボックスにを入力します。 [フォルダー] アイコンを選択して、開いている API ファイルをアップロードします。 作成した`MSGraph-Delegate-Batch.swagger.json`ファイルを参照します。 [**続行**] を選択して、開いている API ファイルをアップロードします。

 ![[カスタムコネクタの作成] ダイアログのスクリーンショット](./images/flow-conn3.png)

[コネクタの構成] ページで、ナビゲーションメニューの [**セキュリティ**] リンクを選択します。 フィールドに次のように入力します。

- **API によって実装されている認証を選択し**ます。`OAuth 2.0`
- **id プロバイダー**:`Azure Active Directory`
- **クライアント id**: 前の手順で作成したアプリケーション id
- **クライアントシークレット**: 前の手順で作成したキー
- **ログイン url**:`https://login.windows.net`
- **テナント ID**:`common`
- **リソース URL**: `https://graph.microsoft.com` (末尾がありません)
- **範囲**: 空白のままにする

右上の [**コネクタの作成**] を選択します。

![コネクタ構成の [セキュリティ] タブのスクリーンショット](./images/flow-conn4.png)

コネクタが作成されたら、生成された**リダイレクト URL**をコピーします。

![生成されたリダイレクト URL のスクリーンショット](./images/flow-conn5.png)

前の手順で作成した[Azure Portal](https://aad.portal.azure.com)の登録済みアプリケーションに戻ります。 **MS Graph バッチアプリ**ブレードの [**概要**] を選択し、[**リダイレクト URI の追加**] を選択します。 **リダイレクト URI**フィールドにコピーした**リダイレクト URL**を追加し、[**保存**] を選択します。

![Azure portal の応答 url ブレードのスクリーンショット](./images/flow-conn-preview6.png)