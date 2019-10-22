-期中作业
=========
# (数据选取为绵阳市某时段人流情况)
# 摘要
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
# 设置背景
MapBackground(lat,lng, destfile ="bckg",maptype ="terrain")
doubs.map <- ReadMapTile(destfile = "bckg")
# 绘制地图
# 绘制起点坐标点
PlotOnStaticMap(doubs.map,lat,lng,cex = 1.0,col = origdata.kmeans$cluster,pch = 19)
# PlotOnStaticMap(doubs.map,origdata.kmeans$centers[,2],add=TRUE,origdata.kmeans$centers[,1],cex=1.3,col="purple",pch="X")
# 绘制终点坐标
PlotOnStaticMap(doubs.map,lat_e,lng_e,cex = 1.0,add=TRUE,col = descdata.kmeans$cluster,pch = 19)
```
## 绘制起点聚类
![起点聚类.png](https://github.com/shengunxiansen/Test/raw/master/起点聚类.png)

## 绘制终点聚类
![终点聚类.png](https://github.com/shengunxiansen/Test/raw/master/终点聚类.png)

## OD线聚类
![OD线聚类.png](https://github.com/shengunxiansen/Test/raw/master/OD线聚类.png)

# 二、选取样方

# 三、计算
