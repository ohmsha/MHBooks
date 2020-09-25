# 2. Notebookの使い方

Notebook（Jupyter Notebookの略）の起動は**1. JupyterLabの起動**を参照してください。
（代わりにJupyter notebookの起動の方が開発は便利です（2020年9月時点））

起動の後に，次のサイトに使い方がよく書かれています。
- [Jupyter Notebookの使い方を覚えればPythonを使いこなせるのか？ (ファイル名のrenameなどがある）](https://attracter.tokyo/tech/python3/)
- [図解！Jupyter Notebookを徹底解説！(インストール・使い方・起動・終了方法)](https://ai-inter1.com/jupyter-notebook/)
- [さくらのナレッジ > エンジニア向け > 非エンジニアでも使いやすい高機能なPython環境「IPython」「Jupyter」を使ってみよう](https://knowledge.sakura.ad.jp/17727/)

次はJupyterの使い方というよりは，ArcGIS（空間データの作成、管理、共有、分析を行う組織向けのプラットフォーム）をJupyterLabで開発している事例です。
- [ArcGIS API for Python > Jupyter Lab を使ってみよう](https://esrijapan.github.io/arcgis-dev-resources/tips/python/python-api-jnlabsetup/)

### 備考：開発のTips
- デバッグは大抵，計算途中の変数の値を知ることにあります。この場合，適当な場所（筆者はよくNotebookの最後）にセルを追加（キーボード"b"を押すと，"b"elowにセルを追加）して，ここで，変数の値を確かめています。
- 数式の書き方，ほぼLaTeXに準じています。ただし，文章中の式は $・・ $と1個のドル記号で両側を挟みます。式だけを独立して文章中に入れるには$$ .. $$と2個のドル記号で挟みます。さらに，そのセルはMarkdown（HTMLライクな文章を書くとき）に変えてから実行してください。
