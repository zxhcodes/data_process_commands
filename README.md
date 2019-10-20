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
