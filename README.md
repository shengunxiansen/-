-期中作业
=========
  (数据选取为绵阳市某时段人流情况)
# 一、数据处理
```
library(RgoogleMaps)
library(googleVis)
library(ggplot2)
library(maptools)
library(maps)
library(mapproj)
library(mapdata)
library(RColorBrewer)
# 导入数据
mydata<-read.table(header=T,file="df3.csv",sep=",")
# 获取起点坐标
origdata<-mydata[,5:6]
# k-means算法聚类
origdata.kmeans<-kmeans(origdata,3)
lng <- mydata[,5]
lat <- mydata[,6]
# 获取终点坐标
descdata<-mydata[,7,8]
descdata.kmeans<-kmeans(descdata,3)
lng_e<-mydata[,7]
lat_e<-mydata[,8]
```
## 绘制起点聚类
![](https://github.com/shengunxiansen/Test/raw/起点聚类.png)
