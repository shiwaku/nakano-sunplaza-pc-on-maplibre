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
- [PDAL](https://pdal.io/en/2.7.2/)及び[py3dtiles](https://pypi.org/project/py3dtiles/)を用いて、点群データから3D Tilesを生成しています。
- LASのX座標とY座標を入れ替え（平面直角座標系から地心直交座標系に変更）
xy_switch_pipeline.json
```json:xy_switch_pipeline.json
[
  {
    "type": "readers.las",
    "filename": "航空レーザ点群データ_外観.las",
    "spatialreference": "EPSG:6677"
  },
  {
    "type": "filters.reprojection",
    "in_srs": "EPSG:6677",
    "out_srs": "EPSG:6677",
    "in_axis_ordering": "2, 1"
  },
  {
    "type": "writers.las",
    "filename": "航空レーザ点群データ_外観_swaped.las",
    "forward": "header,scale,vlr",
    "offset_x": "auto",
    "offset_y": "auto",
    "offset_z": "auto"
  }
]
```
```
# X座標とY座標を入れ替え
pdal pipeline xy_switch_pipeline.json
```
