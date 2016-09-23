# 4d-component-geo-jp-b
国土交通省データ（2015年）に基づく位置情報データベース（市区町村レベル）

街区地番レベルのデータベースは[こちら](https://drive.google.com/drive/folders/0B_M-9bo2YDhdN0pUMXdsRUE2VXc?usp=sharing)にあります。

###インストール方法

http://doc.4d.com/4Dv15R5/4D/15-R5/Component-installation-and-compatibility.300-2964173.ja.html

###公開メソッド

* ADDRESS_Get_code

都道府県コードおよび市区町村コードを返します。

```
$c0:=ADDRESS_Get_code ("東京")
```

```js
{
	"found": true,
	"prefectureCode": "13",
	"prefectureName": "東京都"
}
```

```
$c1:=ADDRESS_Get_code ("東京都")
```

```js
{
	"found": true,
	"prefectureCode": "13",
	"prefectureName": "東京都"
}
```

```
$c2:=ADDRESS_Get_code ("東京都世田谷区")
```

```js
{
	"found": true,
	"cityCode": "13112",
	"cityName": "世田谷区",
	"prefectureCode": "13",
	"prefectureName": "東京都"
}
```

* GEO_Get_location

住所から位置情報を返します。


```
$p1:=GEO_Get_location ("東京都世田谷区新町1")
```

```js
{
	"found": true,
	"address": "東京都世田谷区新町一丁目",
	"lat": 35.627901,
	"lng": 139.650032,
	"prefectureCode": "13",
	"prefectureName": "東京都",
	"addressCode": "131120034001",
	"addressName": "新町一丁目",
	"cityCode": "13112",
	"cityName": "世田谷区"
}
```

---

###おまけ

* NUM_Half_width
 
全角の数字を半角に変換します。

```
$n1:=NUM_Half_width ("１３２３０２７０７")
```

```
132302707
```

* NUM_Kanji
 
数値を漢字表記に変換します。

```
$n2:=NUM_Kanji ("１３２３０２７０７")
```

```
一億三千二百三十万二千七百七
```

```
$n3:=NUM_Kanji ("18543703796709789900234578")
```

```
十八秭五千四百三十七垓三百七十九京六千七百九兆七千八百九十九億二十三万四千五百七十八
```

* ADDRESS_Transliterate
 
住所を番地表記に変換します。

```
$a1:=ADDRESS_Transliterate ("東京都世田谷区新町1-21-11")
```

```
東京都世田谷区新町一丁目
```

```
$a2:=ADDRESS_Transliterate ("東京都世田谷区新町1-21-11";True)
```

```
東京都世田谷区新町一丁目二十一番地十一号
```

###ウィジェット

Webエリア/Leafletを使用しています。バインド変数に住所を代入すると地図が表示されます。

<img width="652" alt="map" src="https://cloud.githubusercontent.com/assets/1725068/18536015/2b259a14-7b34-11e6-9b9a-933ae37311cb.png">



