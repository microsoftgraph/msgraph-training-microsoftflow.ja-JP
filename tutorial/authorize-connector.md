<!-- markdownlint-disable MD002 MD041 -->

コネクタが使用できる状態になっていることを確認するための最後の構成手順は、キャッシュされた接続を作成するためにカスタムコネクタを承認およびテストすることです。

> [!IMPORTANT]
> 次の手順では、管理者特権でログインしている必要があります。

[Microsoft Flow](https://flow.microsoft.com)で、[コネクタ構成] 画面に移動し、ナビゲーションメニューの [**テスト**] リンクを選択します。 [**新しい接続**] リンクを選択します。 Office 365 テナント管理者の Azure Active Directory アカウントでサインインします。

要求されたアクセス許可の入力を求められたら、**組織に代わって同意**を確認し、[**同意**する] を選択してアクセス許可を承認します。

![アクセス許可のプロンプトのスクリーンショット](./images/flow-conn8.png)

アクセス許可を承認すると、フローに接続が作成されます。

![Microsoft Flow で作成された接続のスクリーンショット](./images/flow-conn9.png)

これで、カスタムコネクタが構成され、有効になりました。 アクセス許可が適用されて使用可能になるまでに遅延が発生することがありますが、コネクタは現在構成されています。