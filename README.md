# xx笔记

## 直接获取base64字符串

```
xx.QRCode = function (options) {
    var api = {};
    var Default = {
        width: 300,
        height: 300
    }
    Object.assign(Default, options || {});
    var qrcode = new QRCode(document.createElement('div'), Default);
    //默认支持DataURI(修复源代码检测延DataURI迟问题)
    qrcode._oDrawing._bSupportDataURI = true;
    function code(text) {
        qrcode.makeCode(text);
        return qrcode._oDrawing._elImage.src;
    }
    api.code = code;
    return api;
}
```

# QRCode.js
QRCode.js is javascript library for making QRCode. QRCode.js supports Cross-browser with HTML5 Canvas and table tag in DOM.
QRCode.js has no dependencies.

## Basic Usages
```
<div id="qrcode"></div>
<script type="text/javascript">
new QRCode(document.getElementById("qrcode"), "http://jindo.dev.naver.com/collie");
</script>
```

or with some options

```
<div id="qrcode"></div>
<script type="text/javascript">
var qrcode = new QRCode(document.getElementById("qrcode"), {
	text: "http://jindo.dev.naver.com/collie",
	width: 128,
	height: 128,
	colorDark : "#000000",
	colorLight : "#ffffff",
	correctLevel : QRCode.CorrectLevel.H
});
</script>
```

and you can use some methods

```
qrcode.clear(); // clear the code.
qrcode.makeCode("http://naver.com"); // make another code.
```

## Browser Compatibility
IE6~10, Chrome, Firefox, Safari, Opera, Mobile Safari, Android, Windows Mobile, ETC.

## License
MIT License

## Contact
twitter @davidshimjs

[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/davidshimjs/qrcodejs/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

