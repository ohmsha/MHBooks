# 書籍で用いるパッケージのインストールの説明
#### Anacondaでは足りないパッケージのインストールの説明
#### ただし，本サポートページが扱う複数の書籍全てに渡っているので，必要なものだけをインストールしてください。

インストールの途中で Proceed ([y]/n) ? と聞かれたら ‘y’を入力します。

なお，“>” は<strong>プロンプト</strong>を表します。
Windowsの場合は，管理者権限で行えるようにしてください。

インストールの仕方は主に**conda**を使用します（Anacondaインストールを前提としているため）。

しかし，**pip**でインストールする場合もあります。
この際，幾つかのパッケージが次のようにpipのアップグレードを要求されることがあります。
```
>python -m pip install --upgrade pip
```
または
```
>pip install --upgrade pip
```
（今後，この表現を用います）

この要求が出た場合，上記のとおりにpipのアップグレードを行った後にパッケージのインストールを行ってください。

---------------------------------------------------------------------------

## パッケージの紹介
アルファベット順

---------------------------------------------------------------------------
##### Axelrod：エージェントベースモデル
囚人のジレンマのモデルを提供し，様々なジレンマの戦略を定義できる。

HP: https://pypi.org/project/Axelrod/
```
> pip install axelrod
```


##### Cartopy：地球の地理空間データの提供，投影法や線・ポリゴンなどのプロット
HP: https://scitools.org.uk/cartopy/
```
> conda install -c conda-forge cartopy
```

##### DEAP：遺伝的アルゴリズム
HP: https://deap.readthedocs.io/
```
> pip install deap
```


##### japanize-matplotlib：matplotlibの日本語表示化
matplotlibの日本語表示が必要な場合にインストールしてください。

HP: https://github.com/uehara1414/japanize-matplotlib
```
> pip install japanize-matplotlib
```



##### MeCab：形態素解析エンジン
HP: http://taku910.github.io/mecab/
```
> pip install mecab-python3
```
MeCapと共に次の形態素解析器MeCab用の解析用辞書の軽量版も一緒にインストールして使っています。

**UniDic** HP: https://unidic.ninjal.ac.jp/about_unidic
```
> pip install unidic-lite
```


##### mlxtend：パターン認識などに適する見た目の良いプロット
HP: http://rasbt.github.io/mlxtend/
```
> conda install mlxtend
```

pipを用いたインストールは次です。
```
pip install mlxtend 
```


##### mplfinance: ローソク足チャートのプロット　（旧 mpl_finance, 付録に備考あり）
HP: https://github.com/matplotlib/mplfinance
```
> pip install --upgrade mplfinance
```

##### NetworkX：グラフ理論で用いるノードとエッジで表現されるグラフの作成とプロット
HP:http://networkx.github.io/

HPは次のインストールを示しています。
```
> pip install networkx
```

condaを用いたインストールは次です。

```
> conda install -c anaconda networkx
```



##### OpenCV: 画像処理，認識
HP: https://opencv.org/

参照:https://anaconda.org/conda-forge/opencv

```
> conda install -c conda-forge opencv
```
もし，Solving environment failedが生じたら次を実行してください。
```
> conda update --all
```

インストール成功の確認は，次のように表示されることです。（バージョンは現時点のもの） 
    
```
> python
>>> import cv2
>>> print(cv2.__version__)
4.2.0
```

##### PuLP: 線形計画法
HP: https://pypi.org/project/PuLP/

HPは次のインストールを示しています。
```
> pip install PuLP
```
condaを用いたインストールは次です。
```
> conda install --channel https://conda.anaconda.org/conda-forge pulp
```


##### pyaudio: 音声ファイルの入出力，処理 （付録に備考あり）
HP: https://pypi.org/project/PyAudio/
```
> conda install --channel https://conda.anaconda.org/anaconda pyaudio
```
または，次に従い，https://people.csail.mit.edu/hubert/pyaudio/　
```
> pip install pyaudio
```


##### PyMC3: 確率的プログラミング
HP: https://docs.pymc.io/
```
> conda install -c conda-forge pymc3

```
または
```
> pip install pymc3
```
ただし，PyMC3はC/C++コンパイラ（64ビット）を使うため，次の実行を行い
```
import pymc3

sorry, unimplemented: 64-bit mode not compiled in
```
このエラーが生じたならば，次を参照してください &rarr; [InstallPyMC3](./InstallPyMC3.md)

また，pymc3.traceplot()でエラーが生じたら，[Tips/NoteErrors/NotePackages.md](../NoteErrors/NotePackages.md)を参照してください。

##### rpy2: Rのデータセットにアクセスするインタフェース （付録に備考あり）
```
> conda install rpy2
> conda install tzlocal
```


##### SimPy：離散事象シミュレータ
HP: https://simpy.readthedocs.io/en/latest/

HPは次のインストールを示しています。
```
> pip install simpy
```

pipは最新バージョンをインストールします。
（ver.4.0.1 - 2020/04/01）

condaを用いたインストールを行いたい場合，多少古いバージョン（ver.3.0.10, 2020/09/05）でも良ければ，次で複数該当サイトを見つけられます。
```
> anaconda search -t conda simpy
```



##### VPython：3Dグラフィックパッケージ，Jupyter, GPU対応
HP: https://vpython.org/

ANACONDA CLOUD: https://anaconda.org/vpython/vpython
```
> conda install -c vpython vpython
```



##### xlrd: Microsoft Excelファイルからデータの抽出
HP: https://anaconda.org/anaconda/xlrd/

```
> conda install -c anaconda xlrd
```




----------------------------------------------------------------------------------------
# 付録

この付録は，記録程度に留めるためだけで，現在は用いることができないものもあります（結果の評価ができないため）。



#### rpy2：Rとpandasのインタフェース
2018年11月現在。
pandas　0.19.0までは、次のインストールで関係するパッケージを全てインストールできた。
```
>conda install rpy2
```

しかし、0.23.4では、https://pandas.pydata.org/pandas-docs/stable/r_interface.html
```
from rpy2.robjects import pandas2ri
pandas2ri.activate()
```
の実行で、なぜか、txlocalをインポートできないというエラーが生じる。
そのため、次のインストールを実施している。
```
>conda install txlocal
```

#### pyaudio：オーディオの入出力機能
2018年後期より、Python3.6 ー＞Python3.7が提供された。これに伴い、

Python 3.6の場合は次でインストールできた。
```
> pip install pyaudio
```

しかし、Python 3.7の場合は、上記のインストールではエラーが生じる。
そこで、次でpyaudioを検索
```
> anaconda search -t conda pyaudio
```
この結果から複数のダウンロード先のチャネル候補が出力されるので、ここでは、チャネルを次に選び、インストール法を次より得た。
```
>anaconda show anaconda/pyaudio
```

2020年9月現在，どちらの方法でできるかは確認していないが，conda, pipの両方を試されたい。


#### mpl_finance ：ローソク足チャート
　matplotlib v.2.1.2 までは，matplotlib.financeの中のmpl_financeにローソク足チャートを描くcandlestick_ohlcがあった。v.2.2.2からは，matplotlibからfinanceそのものが無くなった。この説明は次にある：https://matplotlib.org/api/finance_api.html
 github のリポジトリからpipを用いてインストールする方法は
```
> pip install git+url
```

であるが，mpl_financeのアップの仕方が不十分であるため，示した方法は，ZIPファイルを直接指定して，pip機能でダウンロード，解凍，インストールを行うものである。ゆくゆくは，本来のインストール方法になるものと期待される。

**参考：**
pip install :https://pip.pypa.io/en/stable/reference/pip_install/ 

**注意:**

2020年より，新たなmplfinanceパッケージが次から提供されている。
https://github.com/matplotlib/mplfinance
インストールもこのURLに書かれている。これをインストールした場合，関数の呼び方（引数の与え方含めて，APIと称している）が異なる。
現在，提供しているTSA_StockPrices_mplfinance.ipynbは，新しいAPIに書き換えている。




##### Seaborn：比較的綺麗なグラフ（ヒートマップ）表現
HP: https://seaborn.pydata.org/

2017年よりAnacondaに標準的に含まれるようになった。


以上

