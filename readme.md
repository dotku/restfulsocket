# RESTfulSocket

https://stackoverflow.com/questions/31089221/what-is-the-difference-between-put-post-and-patch

```js
function RestfulSocket(url) {
 this.webSocket = new WebSocket(url);
 this.send = (path, data) => {
  retrun new Promise(resolve, reject) {
    data ? this.wetSocket.send(`${command} ${data}`) : this.webSocket.send(path);
    this.webSocket.onMessage = (msg) => {
      let data = JSON.parse(msg.data);
      if (data.command === command) {
        resolve(data);
      }
    }
    this.webSocket.onClose = () => {
      reject(new Error('web socket disconnected'));
    }
    setTimeout(() => {reject(new Error('timeout')},3000);
  }
 }
}
```
