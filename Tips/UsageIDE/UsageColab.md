# Colabの使い方

下記は，ブラウザChrome, OS Windows10を用いて説明していますが，
他のブラウザやOSでも使用できます（一部できないものもあります）。
PC以外で，スマホ＋Chromeの動作も確認していますが，見にくく，スクリプトの変更が大変手間がかかります。

- 概要
- さあ始めよう

---------------------------------------------------------------------------
# 概要
#### Colaboratoryを使用できるための必須条件
- Googleのアカウントを持っていること
    - アカウントを新たに作る場合 &rarr; https://support.google.com/accounts/answer/27441?hl=ja
- インターネットに接続していること
- Google ドライブの使い方を知っている

#### Colaboratoryとは
Colab（略称）は，クラウドで実行され，Jupyter NotebookをGoogleドライブに保存する無料のJupyter Notebook環境です。
よって，Googleドライブの使い方も知っておく必要があります。
ColaboratoryはProject Jupyterの一部として始まり，この後の開発はGoogle（米国）に引き継がれた。
ユーザは，Googleのアカウントを有しているという前提で，インターネット接続されて適当なブラウザを有するPCを用意するだけでよく，Jupyter Notebookの使い方に慣れていれば，直ちに使用することができる。
Colabは，強力な計算パワーを提供している。

**使用時間制限**があるため，開発中のNotebookはGoogle ドライブに保存することが推奨されている。

**データのアクセス（入出力）**について，クラウドコンピューティングの性質上，Googleドライブとリンクして， ドライブ上でデータのアクセスを行うようにする。

初めて使う場合には，次を参照すると良い。

-“Colaboratory へようこそ”　https://colab.research.google.com/notebooks/welcome.ipynb


#### Colabが有するライブラリ
※Googleはパッケージと言わず、ライブラリと言う。

Importing a library that is not in Colaboratory　

https://colab.research.google.com/notebooks/snippets/importing_libraries.ipynb

Colaboがデフォルトで有するライブラリの一部

numpy, scipy, matplotlib, pandas, statsmodels
sklearn
mlxtend, seaborn
cv2 (OpenCV ver.3)

#### Colabに含まれないライブラリのインストール
例えば次があります。
- mpl_finance	株価データの時系列分析
    - 下記に、インストールの仕方を記述します。

Colab
mpl_financeのインストールの仕方：
Colabのコードセルの１番目で、次の１行を実行する。
```
!pip install https://github.com/matplotlib/mpl_finance/archive/master.zip
```
-----------------------------------------------------------
# さあ始めよう

次の3点を説明します。他の使い方は，他のサイトなどを参照してください。

1. 新規にスクリプトをアップロードして実行する
2. 保存されているNotebookを再度実行したい場合
3. データを読込む
 
ここに，すでに、Googleにログインしているものとする。ここから、
https://colab.research.google.com　にアクセスしているものとします。

-----------------------------------------------------------
### 1. 新規にスクリプトをアップロードして実行する

Colabのオープニング画面が次です。
![ColabOpeing](./figs/fig_IDE_Colab_Opening.png) 

<img src="./figs/fig_IDE_Colab_Opening.png" width="320px">

アップロードの仕方は、赤枠（右上の[アップロード]または右下の[ノートブックを新規作成]）のいずれかをクリックする。

ここでは、[ノートブックを新規作成]をクリックするを選ぶものとする。
次の画面で、メニュー[ファイル] &rarr; [ノートブックをアップロード]を選ぶ。



### 2. 保存されているNotebookを再度実行したい場合


### 3. データを読込む

