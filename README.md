# データの出典
## 中野サンプラザ 3Dデータ
- ※ クリエイティブ・コモンズ・ライセンス 表示4.0国際（CC-BY4.0）
クリエイティブ・コモンズ・ライセンスの表記の一つ。原作者のクレジット（本データの場合、中野区）を表示すれば、
利用者が営利目的を含めて自由にデータを改変、複製、再配布することができます。  
https://www.city.tokyo-nakano.lg.jp/kanko/city-promotion/Sunplaza_3D.html

## 東京都オープンデータカタログサイト
- 下記のサイトで公開されている中野サンプラザ3Dデータのうち、「中野サンプラザ三次元点群データ（外観）」を使用しています。
https://catalog.data.metro.tokyo.lg.jp/dataset/t131148d0000000154

# データの加工方法
中野サンプラザ三次元点群データ（外観）の「Hovermap点群データ_外観.las」及び「航空レーザ点群データ_外観.las」について、
[PDAL](https://pdal.io/en/2.7.2/)及び[py3dtiles](https://pypi.org/project/py3dtiles/)を用いて、3D Tilesを生成しています。
- 
