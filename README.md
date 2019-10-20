#### 设置nodata
```
gdal_translate -a_nodata xxx src_file dst_file
```

#### 按行读取并自动按指定分割符号分割字段
```
while IFS=, read -r x y z; do echo ${x}; done < data.csv
```

#### 将一个文件的部分内容按行传递给脚本进行处理
```
sed -n '41,80p' files.txt | xargs -I % sh compress.sh %
```

#### shp文件转geojson
```
ogr2ogr -f geojson out.json src.shp
```
结果如下：
```
{
	"type": "FeatureCollection",
	"name": "ces",
	"crs": {
		"type": "name",
		"properties": {
			"name": "urn:ogc:def:crs:OGC:1.3:CRS84"
		}
	},
	"features": [{
		"type": "Feature",
		"properties": {
			"id": 1
		},
		"geometry": {
			"type": "Polygon",
			"coordinates": [
				[
					[131.416861513495235, 49.435160322257502],
					[131.697141071119859, 48.853295791069385],
					[131.697141071119859, 48.853295791069385],
					[132.596860865915858, 49.259179681265707],
					[132.656912617776555, 48.942387283839714],
					[131.838371507643473, 48.424414150293522],
					[131.008657231856347, 48.762618338008153],
					[131.416861513495235, 49.435160322257502]
				]
			]
		}
	}]
}
```
