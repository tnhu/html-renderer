## html-renderer

Render HTML content using [Virtual DOM](http://npmjs.org/virtual-dom). This project uses code from [virtual-html](https://github.com/azer/virtual-html) and [html-patcher](https://github.com/azer/html-patcher).

## Build

```bash
$ browserify index.js > html-renderer.js
```

## Usage

```html
<script src="html-renderer.js"></script>
```

Sample:

```js
var counter = 0;
var homeRenderer = htmlRenderer(document.body, renderHome());
var timeRenderer = htmlRenderer(document.getElementById('time'), renderTime());

setInterval(function () {
  homeRenderer(renderHome());
  timeRenderer(renderTime());
}, 1000);

function renderHome() {
	counter++;
  return '<div id="home"><h1>Counter:' + counter + '</h1><div id="time"></div></div>';
}

function renderInbox() {
  return '<h1>The time now is:<span>' + new Date().toGMTString() + '</span></h1>';
}
```

## License

MIT
