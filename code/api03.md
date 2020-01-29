# Step 3. API にリクエストする準備

index.html

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8" />
<title>地図を表示する - API Tutorial</title>
<meta name="viewport" content="initial-scale=1,maximum-scale=1,user-scalable=no" />
<!-- ここに Mapbox の JavascriptAPI と css を読み込むコードを書きます -->
<script src="https://api.mapbox.com/mapbox-gl-js/v1.6.1/mapbox-gl.js"></script>
<link href="https://api.mapbox.com/mapbox-gl-js/v1.6.1/mapbox-gl.css" rel="stylesheet" />
<style>
/* ここにCSSを書きます */
body { margin: 0; padding: 0; display: flex; flex-flow: column; min-height: 100vh;}
#map { flex: 1; }
#button { height: 100px; }
</style>
</head>

<body>
<!-- ここにhtmlとjavascript書いていきます -->
<div id="map"></div>
<input id="button" type="button" value="Exec" onclick="OnButtonClick();"/>
<script>
// mapbox の accessToken を設定
mapboxgl.accessToken = '取得したaccessTokenを書いてね';
// 紀尾井町周辺の地図を表示させる
var map = new mapboxgl.Map({
    container: 'map',
    style: 'mapbox://styles/mapbox/outdoors-v11',
    center: [139.736897, 35.679584],
    zoom: 15
});

// ボタンが押された時の挙動をここに記載する
function OnButtonClick() {

}
</script>
</body>
</html>
```

Next: [api04.md](./api04.md)
