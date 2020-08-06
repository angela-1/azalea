# azalea
人员管理系统

:::Note::: 

As the issue 652 of vite says, to make the vite app work, 
must modify vite dist file `client.js` in `node_modules/vite/dist/client/client.js` line 23

if the pr 677 merged, has config for socketPort, this can be ignore


```js
// const socketUrl = `${socketProtocol}://${location.hostname}:${__PORT__}`;
const socketUrl = `${socketProtocol}://${location.hostname}:10080`;
```