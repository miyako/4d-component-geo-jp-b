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
