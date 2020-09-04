# パッケージの注意事項

主に，パッケージのバージョンに起因する内容


##### SciPy, solve_ivp
SciPy 1.3.1 で solve_ivpを使うと引数のargsでエラーが生じる。このとき，SciPyのバージョンを1.5.x以上にあげること。

conda環境ならば
```
>conda install scipy==1.5.2
```
pipの場合は，次を参照：https://scipy.org/

##### statsmodelsのバージョン
 statsmodelsのバージョンの違いにより，statsmodels.tsa.arima_process.arma_generate_sample()のAPIが異なるため，これに対処できるよう"ARMA_ParmeterEstimation.ipynb"を変更したので，DownloadページからNotebookを再度ダウンロードされたい。


##### mpl_financeのバージョン
mpl_financeの使い方で，異なるパッケージmplfinanceもあり（2020年３月現在），この使用の注意は，"TSA_StockPrices.ipynb"に記述したので，DownloadページからNotebookを再度ダウンロードされたい。


##### Microsoft Excelとpandas.read_excel()
Microsoft Excelをpandas.read_excel()で読込むとき、”ImportError: Install xlrd >= 1.0.0 for Excel support”というエラーが出るとき、xlrdをインポートすること。

##### matplotlibのバージョン
matplotlib 2.1.2で動く“matplotlib.finance”が，2.2.2で動かない。-> 上記の"パッケージのインストール”を参照されたい。

##### pandasと重回帰分析ols
pandas 0.22.0で，重回帰分析olsの返り値はpandas Series,  0.19.0はnumpy.ndata

##### pandas on windows or mac
pandas,  windowsで動き，macで動かない事例がある。この例は，df[df['Item'] == '?' ].count()で，TypeError: Could not compare ['?'] with block valuesが生じる。macで，CSVファイルを読み込んだデータにおいて，数字と文字列の混在したものは，データタイプの混乱が生じていると推測，このため，pd.read_csv('filename', dtype=object)として解決した。なお，dtypeは次を参照：https://note.nkmk.me/python-pandas-dtype-astype/


##### seabornのバージョン0.9.0
seabornのプロットは，バージョン0.9.0から，データセットの種類の数に対応する色数を明示的に用意することが求められる。例えば，"hue="の右辺である。そうでないと，次のエラーが現れる "ValueError: color kwarg must have one color per dataset"。

##### seaborn in Anaconda
Since version 4.3.0 dated 2017-01-31, Anaconda comes with seaborn installed by default.