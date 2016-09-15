# 4d-component-geo-jp-b
国土交通省データ（2015年）に基づく位置情報データベース（市区町村レベル）

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
