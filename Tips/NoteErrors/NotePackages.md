# パッケージの注意事項

主に，パッケージのバージョンに起因する内容を記します。

### arma_generate_sample()を用いて、an unexpected keyword argument 'size'が表示される
statsmodels ver 0.11.1より、arma_generate_sample()の引数の使用方法が変わりました。

旧バージョンのsigmaがscaleに変更、また、distrvの関数の与え方も変わりました。
0.11.1からは、例えば次のように使用します。

dist = stats.norm(loc=0, scale=1.0).rvs <br>
y = arma_generate_sample(ar, ma, nsample=nobs, distrvs=dist, burnin=500)

注意：Colaboratoryでは，statsmodelsのバージョンは0.10.2（2021年5月8日現在，古いバージョンがディフォルトで使用される）のため，上記のスクリプト実行はエラーが生じます。<br>
この対処法は，スクリプト実行前に次のコマンドをColaboratory上で実行してください。
```
!pip install statsmodels==0.11.1
```


### Cartopyを用いて地球儀が表示されない
2020年９月現在，matplotlibのバージョンが3.3.1より低い場合には，このバージョンにアップグレードしてください。

### JupyterLabでアニメーションが表示されない
2020年９月現在，JupyterLabを起動して，Jupyter Notebookの中でmatplotlibやVPythonのアニメーションが表示されない場合，
いったんJupyterLabを終了して，改めてJupyter notebookを起動して，このもとでアニメーションを実行してください。

詳細な原因は不明ですが，JupyterLabはまだIPythonとのインタフェースが不十分な点があるようです。


### pymc3.traceplot()で"AttributinError" 'int' object has no attribute 'astype'　（2020/09/07）
これは，PyMC3がグラフィックで用いているarvizが，dtypeがfloat64ならば曲線，int64ならば棒グラフを描くはずが，int64に対応できていないためです。そのため，arivizのバージョンを0.9.0にアップデートしてください。

Anacondaでは，
```
> anaconda search -t conda arviz
```
この出力表からバージョン0.9.0のものを選びます。例えば,conda-forgeにあるとして
```
> anaconda show conda-forge/arviz
```
この表示にあるcondaを用いたインストール方法を実施してください。


### Connection Failed  (2020/09/07)
Jupyter Notebookで実行中に，connection failedのメッセージが出て実行できなくなることがあります。

主に，**PyMC3**で生じます。

対処法として，tornadoのダウングレードを試して見て下さい（100\%の保証はできません）。2020年9月現在　tornadoの最新バージョンは6.0.4です。

Anacondaを利用しているユーザは次でダウングレードします。
```
> conda install tornado==5.1.1
```
これ以外で，pipを利用する場合は次です。
```
> pip uninstall tornado
> pip install tornado==5.1.1
```
ダウングレード後にPCを再起動してください。

tornadoは，PythonのWebサーバの役割を担っており，その通信障害が生じることがあるようです。

参照
- Tronado: https://www.tornadoweb.org/en/stable/index.html
- What’s new in Tornado 6.0: https://www.tornadoweb.org/en/stable/releases/v6.0.0.html
- Jupyter notebookで遊んでいたら「Connecting kernel」のままkernelが起動しなかったので解決方法をメモ: https://qiita.com/Kit-Ok/items/077a4033057ba4aaf990
- jupyter notebokは開くが、カーネルを実行時に「Connection Failed」と表示される: https://qiita.com/NameBlack/items/0f41e006b493af079afc

### SciPy, solve_ivp
SciPy 1.3.1 で solve_ivpを使うと引数のargsでエラーが生じます。このとき，SciPyのバージョンを1.5.x以上にあげてください。

conda環境ならば
```
>conda install scipy==1.5.2
```
pipの場合は，次を参照：https://scipy.org/

### statsmodelsのバージョン
 statsmodelsのバージョンの違いにより，statsmodels.tsa.arima_process.arma_generate_sample()のAPIが異なるため，これに対処できるよう"ARMA_ParmeterEstimation.ipynb"を変更したので，DownloadページからNotebookを再度ダウンロードしてください。


### mpl_financeのバージョン
mpl_financeの使い方で，異なるパッケージmplfinanceもあり（2020年３月現在），この使用の注意は，"TSA_StockPrices.ipynb"に記述したので，DownloadページからNotebookを再度ダウンロードしてください。


### Microsoft Excelとpandas.read_excel()
Microsoft Excelをpandas.read_excel()で読込むとき、”ImportError: Install xlrd >= 1.0.0 for Excel support”というエラーが出るとき、xlrdをインポートしてください。

### matplotlibのバージョン
matplotlib 2.1.2で動く“matplotlib.finance”が，2.2.2で動かない。-> 上記の"パッケージのインストール”を参照してください。

### pandasと重回帰分析ols
pandas 0.22.0で，重回帰分析olsの返り値はpandas Series,  0.19.0はnumpy.ndata

### pandas on windows or mac
pandas,  windowsで動き，macで動かない事例がある。この例は，df[df['Item'] == '?' ].count()で，TypeError: Could not compare ['?'] with block valuesが生じる。macで，CSVファイルを読み込んだデータにおいて，数字と文字列の混在したものは，データタイプの混乱が生じていると推測，このため，pd.read_csv('filename', dtype=object)として解決しました。
なお，dtypeは次を参照：https://note.nkmk.me/python-pandas-dtype-astype/


### seabornのバージョン0.9.0
seabornのプロットは，バージョン0.9.0から，データセットの種類の数に対応する色数を明示的に用意することが求められる。例えば，"hue="の右辺です。
そうでないと，次のエラーが現れます "ValueError: color kwarg must have one color per dataset"。

### seaborn in Anaconda
Since version 4.3.0 dated 2017-01-31, Anaconda comes with seaborn installed by default.