# 書籍で用いるパッケージのインストールの説明
#### Anacondaでは足りないパッケージのインストールの説明

全般的に，途中で Proceed ([y]/n) ? と聞かれたら ‘y’を入力します。

なお，“>” は<strong>管理者権限のプロンプト</strong>を表す。

また，幾つかのパッケージが次のようにpipのアップグレードを要求されることがあります。
```
>python -m pip install --upgrade pip
```
または
```
>pip install --upgrade pip
```
（今後，この表現を用います）

この要求が出た場合，上記のとおりにpipのアップグレードを行った後にパッケージのインストールを行ってください。

--------------------------------------

##### Seaborn：比較的綺麗なグラフ（ヒートマップ）表現https://seaborn.pydata.org/
```
> conda install seaborn
```
または
```
> pip install seaborn
```
##### mlxtend：パターン認識などで結果のプロットを簡単に行う
```
> conda install --channel https://conda.anaconda.org/conda-forge mlxtend
```

##### OpenCV: 画像処理，認識

非公式のパッケージopencv-pythonを利用する。　https://pypi.python.org/pypi/opencv-python

インストールは次のように行う。
```
> pip install opencv-python
Collecting opencv-python
<途中省略>
Installing collected packages: opencv-python
Successfully installed opencv-python-3.4.3.18
```

インストール成功の確認は，次のように表示されることである。（バージョンは現時点のもの） 
    
```
C:> python
>>> import cv2
>>> print(cv2.__version__)
3.4.3
```

##### PuLP: 線形計画法
```
> conda install --channel https://conda.anaconda.org/conda-forge pulp
```
または，https://pypi.org/project/PuLP/　に従い
```
> pip install pulp
```

##### pyaudio: 音声ファイルの入出力，処理 （付録に備考あり）
```
> conda install --channel https://conda.anaconda.org/anaconda pyaudio
```
または，次に従い，https://people.csail.mit.edu/hubert/pyaudio/　
```
> pip install pyaudio
```

##### mpl_finance: ローソク足チャートのプロット　（付録に備考あり）
```
> pip install https://github.com/matplotlib/mpl_finance/archive/master.zip
```

##### rpy2: Rのデータセットにアクセスするインタフェース （付録に備考あり）
```
> conda install rpy2
> conda install tzlocal
```

# 付録

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
　matplotlib v.2.1.2 までは，matplotlib.financeの中にローソク足チャートを描くcandlestick_ohlcがあった。v.2.2.2からは，matplotlibからは無くなり，上記のパッケージに移行，これをインストールして使用するようになった。移行の説明は次にある：https://matplotlib.org/api/finance_api.html
 github のリポジトリからpipを用いてインストールする方法は
```
> pip install git+url
```

であるが，mpl_financeのアップの仕方が不十分であるため，示した方法は，ZIPファイルを直接指定して，pip機能でダウンロード，解凍，インストールを行うものである。ゆくゆくは，本来のインストール方法になるものと期待される。

**参考：**
pip install :https://pip.pypa.io/en/stable/reference/pip_install/ 

以上

