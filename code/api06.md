# Step 6. API の返答を処理する準備

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
    // XMLHttpRequestインスタンスの作成
    var request = new XMLHttpRequest();
    // URLを開く（紀尾井町500m圏内で面白そうな写真）
    request.open('GET', 'https://api.flickr.com/services/rest/?method=flickr.photos.search&api_key=取得したappid&lat=35.679584&lon=139.736897&extras=geo,url_t&format=json&nojsoncallback=1&per_page=30&radius=0.5&sort=interestingness-asc', true);
    // リクエストをURLに送信
    request.send();
    // レスポンスが返ってきた時の処理を記述
    request.onload = function () {

    }
}
</script>
</body>
</html>
```

Next: [api07.md](./api07.md)
