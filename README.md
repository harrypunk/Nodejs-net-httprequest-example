# Http with Nodejs net
### How to send simple http header with nodejs socket

```js
const conn = new net.Socket()
conn.connect(80, '54.152.127.232', function () {
  console.log("connection created");
})
conn.on('data', function (data) {
  console.log('on data', data.toString());
})

conn.on('ready', function () {
  console.log('ready');
  conn.write('GET /ip HTTP/1.1\r\nUser-Agent:curl/7.35.0\r\nHost:httpbin.org\r\nAccept:*/*\r\n\r\n')
})
```
