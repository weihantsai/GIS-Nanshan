# 測試調查工具QField之實用度

QField為安裝於手機/平板上的移動式GIS app，方便應用於戶外調查採集，使用方式需先在電腦的QGIS設計屬性表單及匯入所需圖層，再透過QField cloud傳至移動裝置的app中，蒐集完資料後再回傳至QGIS。

```{tip}
1. 手機下載app：QField
2. Qgis套件安裝(plugins) 搜尋：QField Sync 
3. 註冊 [QFieldCloud](https://qfield.cloud/)
 <br>參考教學：[QGIS in the Field (QField Tutorials)](https://youtube.com/playlist?list=PLANnPKXgp4nN8z5-mDHCBYqhtXgD5pxPh&feature=shared)
 <br>[QField](https://docs.qfield.org/get-started/) 
 <br>[QGIS 3 30 QField 功能介紹](https://youtu.be/w0HqlmB3R6A?feature=shared)
 <br>！ 上傳或下載時，需注意勾選本地端或雲端方向，以免造成收集資料被覆蓋遺失
 <br>！ 目前僅提供免費用戶100MB容量
```
## 使用步驟
1. 在新建專案中，新增一個Geopackage，再新建所需表格以及表格欄位。
```{image} ./images/geo1.png
:alt:
:class: bg-primary mb-1
:width: 600px
:align: center
```
```{image} ./images/geo3.png
:alt:
:class: bg-primary mb-1
:width: 600px
:align: center
```

2. 新增其他表格

```{image} ./images/圖層1.png
:alt: 圖層1
:class: bg-primary mb-1
:width: 600px
:align: center
```
<br>

```{image} ./images/圖層2.png
:alt:
:class: bg-primary mb-1
:width: 600px
:align: center
```
```{image} ./images/圖層3.png
:alt:
:class: bg-primary mb-1
:width: 600px
:align: center
```

<br>

3. 加入所需圖層

```{tip}
1. 下載中研院提供WMTS服務： http://gis.rchss.sinica.edu.tw/qgis/WMTS_List.xml
2. QGis選取Add Layer → Add WMS/WMTS Layer → 載入所下載的xml檔
```
<br>

4. 透過共同欄位location_id 連結各表格關聯
```{image} ./images/關聯1.png
:alt: 新坪範圍
:class: bg-primary mb-1
:width: 600px
:align: center
```
<br>

```{image} ./images/關聯2.png
:alt: 新坪範圍
:class: bg-primary mb-1
:width: 600px
:align: center
```
<br>

5. 設計屬性表單

點選Location中Attributes → Form Drag and drop designer → 新增Label(地點、照片、基礎資料) → 更改欄位的別名、類型等，另存qgz/qgs檔或儲存到gpkg
```{image} ./images/設計1.png
:alt: 圖層1
:class: bg-primary mb-1
:width: 600px
:align: center
```
<br>

```{image} ./images/設計2.png
:alt:
:class: bg-primary mb-1
:width: 600px
:align: center
```
```{image} ./images/設計3.png
:alt:
:class: bg-primary mb-1
:width: 600px
:align: center
```

* 編號的type選擇Uuid
```{image} ./images/編號.png
:alt: 
:class: bg-primary mb-1
:width: 600px
:align: center
```
* 日期時間選擇ISO Date Time。Default value選擇now()，會自動填入當前日期時間
```{image} ./images/日期時間.png
:alt: 
:class: bg-primary mb-1
:width: 600px
:align: center
```
* 照片選擇Attachment
```{image} ./images/照片.png
:alt: 
:class: bg-primary mb-1
:width: 600px
:align: center
```
* 西元年選擇Date/Time，再自訂只留下年份yyyy，以便於後續資料可進行年份的時序動畫
```{image} ./images/西元年.png
:alt: 
:class: bg-primary mb-1
:width: 600px
:align: center
```
* 部份欄位可選擇value map，以勾選取代文字輸入
```{image} ./images/valuemap.png
:alt: 
:class: bg-primary mb-1
:width: 600px
:align: center
```
6. 上傳QField cloud
```{image} ./images/上傳1.png
:alt: 
:class: bg-primary mb-1
:width: 600px
:align: center
```
```{image} ./images/上傳2.png
:alt: 
:class: bg-primary mb-1
:width: 600px
:align: center
```

```{tip}
[完成檔參考資料](https://data.depositar.io/dataset/200e112b-8b49-4486-8763-95392a4ea184/resource/17ee6622-28b0-407e-97a1-21a9800da683/download/nanshan%20QField.zip)

使用者下載完壓縮檔後，再使用QGIS開啟專案，透過QField Cloud傳至QField，即可進行調查。
```

## 調查表欄位
本次使用表單的屬性資料為過去所設計紙本調查表的格式，分為以下數項：

:::{table} 屬性資料 
:align: center
:widths: grid

|編號|緯度|經度|橫額|正文|墓主姓名|立碑年代|重修|
|---|---|---|---|---|---|---|---|
|   |   |   |   |   |   |明代<br>清代<br>日治<br>民國<br>待考證|明代<br>清代<br>日治<br>民國<br>無|
|墓葬方式|二次葬|遷葬|墓塚形制|建材施作|特殊裝飾|備註|	
|單人葬<br>夫妻合葬<br>親屬附葬<br>家族合葬|是/否|是/否|漢式<br>日式<br>漢日混合<br>創新形式<br>其他|灰作<br>水泥<br>洗石子|   |   |
:::

```{tip}
備註欄可填入**其他**的補充說明，如描述無法分類的墓塚形制
```
## 實地測試結果

* 2023/08/05於南山公墓三處墓塚進行測試，分別為西式基督教墓、傳統漢式墓及小型嬰孩墓，測試結果手機定位點與實際站位點相差約2-3公尺，該距離間可能差距1-2個墓塚以上，但透過高解析度影像可進行點位校正。
```{image} ./images/巴克禮位置.jpg
:alt: 
:class: bg-primary mb-1
:align: center
```
```{image} ./images/曾振暘位置.jpg
:alt: 
:class: bg-primary mb-1
:align: center
```

* 手機操作頁面
```{image} ./images/IMG_4140.PNG
:alt: 
:class: bg-primary mb-1
:width: 200px
:align: center
```
```{image} ./images/IMG_4179.PNG
:alt: 
:class: bg-primary mb-1
:width: 200px
:align: center
```
