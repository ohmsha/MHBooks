# オープンデータセット（Open Data Sets）

- オープンデータの定義: site:https://www.soumu.go.jp/menu_seisaku/ 内で"オープンデータの定義"を検索
    - 国、地方公共団体及び事業者が保有する官民データのうち、国民誰もがインターネット等を通じて容易に利用（加工、編集、再配布等）できるよう、次のいずれの項目にも該当する形で公開されたデータをオープンデータと定義する。
        1. 営利目的、非営利目的を問わず二次利用可能なルールが適用されたもの
        2. 機械判読に適したもの
        3. 無償で利用できるもの 

オープンデータを次の分類で掲載しています。この分類は，個人的な視点からであり，一般的なものではありません。
また，リンクなどが喪失などの責任を負わないことを予めご了承ください。

【分類1】Pythonプログラムから，ネット経由で直接読込めるデータセットを有するサイト

【分類2】オープンデータとして，CSVファイル，EXCELファイルを提供している

【分類3】オープンデータとして，画像データ（イメージデータ）を提供している。

【分類4】PDFなど，直接利用はできないが，オープンデータとして提供している。


[](コメントアウト-------------------------------------------------------------------------------)
## 【分類1】

### Kaggle   

The Home of Data Science & Machine Learning

世界最大のデータサイエンティストコミュニティを形成し、データ分析やモデル開発のコンペティション（賞金付きもある）を行うサイトである。Kaggle（米国）が運営。無料ユーザ登録よりデータを無料でダウンロードと使用ができる。また，ユーザ登録無しで利用する手段もある。

- https://www.kaggle.com/
- 一部を紹介する
- Titanic  (Amazon S3にある) 
    - titanic_url = "http://s3.amazonaws.com/assets.datacamp.com/course/Kaggle/train.csv"
    - data = pd.read_csv(titanic_url)
- MLB dataset 1870s-2016 https://www.kaggle.com/timschutzyang/dataset1
    - プログラムから直接は得られないので，上記のサイト -> [Data] に移り，[Download]をクリックすると，データやプログラムを一括ダウンロードできる。

### UC Irvine Machine Learning Repository

カリフォルニア大学アーバイン校(University of California, Irvine)が運営，機械学習やデータマイニングに関するデータの配布サイト

- http://archive.ics.uci.edu/ml/
日本語説明サイト：
- UCI 機械学習リポジトリのデータセット一覧（Google翻訳）https://www.trifields.jp/uci-machine-learning-repository-datasets-956
- [メモ] UCI Machine Learning Repository をマイニングする(Machine Learning Advent Calendar 12日目) 23:25　2013年12月12日　http://d.hatena.ne.jp/repose/20131212/1386858310

内容
- Iris  Rのデータセットで有名な Iris（アヤメ）のデータ
    - UCI  http://archive.ics.uci.edu/ml/datasets/Iris
- Wine Data Set, ワインの種類（イタリア）
    - https://archive.ics.uci.edu/ml/datasets/Wine
    - 13次元（説明変数が13個），クラス1,2,3（品種を表す）
    - df_wine_all=pd.read_csv('https://archive.ics.uci.edu/ml/machine-learning-databases/wine/wine.data', header=None)
- Wine Quality　ワイン品質（ポルトガル）
    - UCI http://archive.ics.uci.edu/ml/datasets/Wine+Quality
    - ワインの味（美味しさのグレード）は予測できるか？ http://sudillap.hatenablog.com/entry/2013/04/27/203200
    - Rで遊ぶ　～ワインの等級をrandomForestで予測～　https://qiita.com/Dixhom/items/7c33a1dc85144e1da822
- Wholesale_customers_data   ある卸売り業者の顧客データ
    - https://archive.ics.uci.edu/ml/datasets/wholesale+customers
- Automobile　1985年自動車に関する特性、危険度などのデータ
    - UCI https://archive.ics.uci.edu/ml/datasets/Automobile
- Statlog (German Credit Data)　ドイツの信用貸付データセット、信用貸付の申請者1.000人の財務情報信用貸付の履歴，雇用状況および個人情報が含まれている。
    - ただし、申請者の信用リスクを表し， 700人の申請者が低リスクとして． 約300人が商リスクとして識別されている. 2015年3月現在, UCIMachineLearningRepositoryで公開されているファイルのデータが属性説明と一致せず，各データ項目に対応する属性名が不明なため． 同じデータのCSVファイSmT897D(URL:https://onlinecoursesscience.psu.e(111,stat857 ]lode/215)からダウンロードした　(Ref:Rで学ぶデータサイエンス，１９，経営と信用リスクのデータ分析）
    - UCI　 https://archive.ics.uci.edu/ml/datasets/Statlog+%28German+Credit+Data%29
    - Ref:Rで学ぶデータサイエンス，１９，経営と信用リスクのデータ分析
- 他に、認知心理実験、医学関連、Googleなどからのデータなどがある


### scikit-learn Datasets Package

scikit-learnには教師データとなるデータセットがサンプルで用意されている。

- http://scikit-learn.org/stable/datasets/index.html
- 日本語解説：https://pythondatascience.plavox.info/scikit-learn/scikit-learnに付属しているデータセット
scikit-learn comes with a few small standard datasets that do not require to download any file from some external website.

- [load_boston()](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_boston.html)
- [load_iris()](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_iris.html)
- [load_digits()](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_digits.html)
- [load_wine()](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_wine.html)


These datasets are useful to quickly illustrate the behavior of the various algorithms implemented in the scikit. They are however often too small to be representative of real world machine learning tasks.

使い方

　　from sklearn import datasets

　　iris = datasets.load_iris()　# サンプルデータ読み込み

### StatsModels Datasets Package
Python 統計解析パッケージStatsMoldelsが提供するデータセット。Rdatasetsプロジェクトが提供するデータセットを利用している。Titanic, アヤメの他に，フランスの道徳統計に関するエッセイなどがある。

- http://www.statsmodels.org/dev/datasets/index.html
- Rdatasets Project http://vincentarelbundock.github.io/Rdatasets/
- 例 :　次はフランスの道徳統計に関するエッセイ（"Essay on the Moral Statistics of France"）の統計データの取得

    import statsmodels.api as sm

    df = sm.datasets.get_rdataset("Guerry", "HistData").data

    この意味は，http://vincentarelbundock.github.io/Rdatasets/datasets.html　の中のPackage名が”HistData"，Item名が”Guerry"，データが”CSV”，説明が”DOC"にある。


### Seaborn data
Python Seabornのサンプルグラフ描くために用意されたサンプルデータセット（数はわずか），kaggleのTitanic，Rのアヤメ統計データ，お店の食事時間と会計総額とチップの関係のデータなどがある。

- http://seaborn.pydata.org/examples/index.html
- 使い方
    import seaborn as sns

    titanic = sns.load_dataset("titanic") 

    tips = sns.load_dataset("tips")

    iris = sns.load_dataset("iris")
    
### R（統計解析向けのフリーソフトウェア）のデータセット

- HP　https://www.rdocumentation.org/packages/datasets/
- The R Datasets Package http://stat.ethz.ch/R-manual/R-patched/library/datasets/html/00Index.html
- 日本語訳　http://www.okadajp.org/RWiki/?%E3%83%91%E3%83%83%E3%82%B1%E3%83%BC%E3%82%B8%20%27datasets%27%20%E3%81%AE%E6%83%85%E5%A0%B1
- 日本語の解説あり，http://d.hatena.ne.jp/hoxo_m/20120214/p1
- 日本語　解説　https://qiita.com/wakuteka/items/95ac758070f6f4d89a96

内容（一部）
- Titanic　タイタニックの乗客の生死のデータ
- UCBAdmissions　 1973年の，カリフォルニア大学バークレー校への入学志願者について，6つの学部別，性別の合否結果
- cars　車の速度と停止距離（1920年代のデータ）
- iris　 フィッシャーの（または，エドガー・アンダーソンの）として知られる，有名なアヤメのデータ
- mtcars  1974年の「Motor Trend」誌から抽出した32車種の，燃費の他，デザインなどの評価データ
- sunspot.month   1749〜1997年の月別太陽黒点数
他

### RのMASSパッケージ（サンプルデータ）
- 書籍　Modern Applied Statistics with S'' (4th edition, 2002)で用いられたデータセット
- 使用説明　https://cran.r-project.org/web/packages/MASS/MASS.pdf
- 有名な “Cars93”などがある。これは , 次のページの中の”93cars.dat.txt”にデータがある。これと、「Rで学ぶデータサイエンス１２、統計データの視覚化、共立出版、p.2, p.8」と上記のMASS.pdfを参照すると、データの中身が理解できる。
- https://ww2.amstat.org/publications/jse/v1n1/datasets.lock.html

### IPythonデータサイエンスクックブック　この本で用いられているデータセット
- https://github.com/ipython-books/cookbook-data
- テニス、タイタニック号の乗客など

[](コメントアウト-------------------------------------------------------------------------------)
## 【分類2】

### 総務省統計局 
- http://www.stat.go.jp/
- 労働力調査　長期時系列データ http://www.stat.go.jp/data/roudou/longtime/03roudou.htm
- 家計調査結果
    http://www.stat.go.jp/data/kakei/index.htm

他にも多種のデータがある


### 総務局統計局　なるほど統計学園　
子供向けであるが，データが豊富で使いやすい！　サッカーW杯もある
- http://www.stat.go.jp/naruhodo/

### 政府　e-Stat
日本の統計が閲覧できる政府統計ポータルサイト
- https://www.e-stat.go.jp/
- 社会・人口統計体系  https://www.e-stat.go.jp/stat-search/files?page=1&toukei=00200502&result_page=1

### 気象庁  国土交通省 
- http://www.jma.go.jp/jma/index.html
- 各種データ・資料　http://www.jma.go.jp/jma/menu/menureport.html
- 過去の気象データ・ダウンロード http://www.data.jma.go.jp/gmd/risk/obsdl/

### 富山県人口移動調査
富山県の人口・世帯数・人口密度・出生者数・死亡者数・老年人口割合・年少人口割合に関するデータ
- http://www.pref.toyama.jp/sections/1015/lib/jinko/
- 注意：ここにあるExcelデータを用いるとき，上記のURLに付け加える必要がある。
- 例えば，jinko_dat005.xlsにカーソルを当てると　--/jinko/_data_h29/jinko_dat005.xls　のURLが見える
- 参考までに，H28.10.1 - H29.9.30 調査の jinko_dat005.xlsを本ページアップした。
- TOYAMA OPEN DATA   http://opendata.pref.toyama.jp/


### DeepAnalytic  
我が国におけるデータサイエンスコンテストを民間企業が主催。
- https://deepanalytics.jp/

### 東京電力　過去の使用量
- http://www.tepco.co.jp/forecast/index-j.html



[](コメントアウト-------------------------------------------------------------------------------)
## 【分類3】

### The USC-SIPI Image Database  
南カリフォルニア大学（USC），信号・画像処理研究所（SIPI）が提供する画像データセット。この内容は，世界標準で扱われるTextures(テクスチャ）、Aerials（航空写真）、Miscellaneous（レナ、ヒヒなど）、Sequencs(顔や車の動きの連続写真)がある。
- http://sipi.usc.edu/database/

### ImageProcessingPlace.com  
有志の集まりによる運営で，上記の画像データセットに加えて，プログラムも提供する画像データセット。
- http://www.imageprocessingplace.com/root_files_V3/image_databases.htm

### USGS  Aerial Photography  
米国国歌機関であるEROS(The Center for Earth Resources Observation and Science)による，航空写真データセット
- https://eros.usgs.gov/aerial-photography

### 人文学オープンデータ共同利用センター（Center for Open Data in the Humanities / CODH）
イメージデータのみならず，テキストデータもある。IIIF (International Image Interoperability Framework)の使用を勧めている。日本古典籍，江戸料理レシピ，顔貌コレクション，くずし文字などがある。
- http://codh.rois.ac.jp/

### 上田市イメージデータベース  
上田市にある写真・映像・PDF資料を提供するサイト
- http://museum.umic.jp/imgdb/index.html

### 長崎大学電子化コレクション  
長崎大学が提供するサイト，幕末・明治期の日本の各種写真，ガラパゴス諸島画像データベース，などがある。
- http://www.lb.nagasaki-u.ac.jp/siryo-search/ecolle/



[](コメントアウト-------------------------------------------------------------------------------)
## 【分類4】

### データセット一覧 : DoDStat@d
- http://mo161.soci.ous.ac.jp/@d/DoDStat/indexj.html
- 新国民生活指標，農業経済データ，億万長者，出生率などがある。
- http://d.hatena.ne.jp/hoxo_m/20120214/p1


### 東京都オープンデータカタログサイト
東京都に関するデータ提供，および，アプリコンテストを行っている。
- http://opendata-portal.metro.tokyo.jp/


### 東京公共交通オープンデータチャレンジ
東京都の公共交通関連データ提供，および，アプリコンテストを行っている。
- https://tokyochallenge.odpt.org/

### JEITA　（一社）電子情報技術産業協会　電子工業生産実績，輸出入実績表
- http://www.jeita.or.jp/japanese/stat/electronic/2013/index.htm


### 財務省貿易統計　日本の輸入・輸出
- http://www.customs.go.jp/toukei/info/index.htm

### JETRO　日本貿易振興機構　統計ナビ
- http://www.jetro.go.jp/world/statistics/

### 世界の人口が多い都市ランキング、トップ10
- http://news.aol.jp/2017/05/20/look-inside-most-populated-cities-world/


### メッシュ農業気象データ　利用マニュアル
- http://adpmit.dc.affrc.go.jp/technical/files/rel67_1.pdf
- PythonとCSVファイルを用いている。ここと同じフォルダにPDFを貼り付け

### 国土数値情報　
- http://nlftp.mlit.go.jp/ksj/
- 国土交通省　国土計画局により、鉄道、河川、海岸線など国土の骨格に関するデータを提供。ファイルフォーマットは、JPGIS形式やシェープファイル形式である。これを読み込み表示するソフトウェアはこのWebページにある。

### みんなの地球地図　
- http://archive.fo/8wM3P
- http://www.globalmap.org:80/index.html


### 全国市区町村界データ
- https://www.esrij.com/products/japan-shp/
- esri ジャパンが提供　https://www.esrij.com/getting-started/learn-more/shapefile/
- シェープファイルフォーマットで提供、シェープファイル（Shapefile）とは、Esri 社の提唱したベクトル形式の業界標準フォーマット。Esri 製品はもちろん、多くの GIS ソフトウェアで利用が可能です。

### データで楽しむプロ野球
- http://baseballdata.jp/
^ 選手個人のデータ，例えば，カウント別のヒット率などを示されている。


### 2014年全6.6万打席の紹介｜プロ野球データでクロス集計　with Tableau　第1回 
- https://www.gixo.jp/blog/3972/amp/

以上
