# azalea
人员管理系统


This project is developed on a guest debian inside a virtual machine with docker container.

The `app` project port forward is: 10080(host)  -> 8080(guest) -> 3000(docker container), and `server` is the same.


**Note**

As the issue 652 of vite says, to make the vite app work, 
must modify vite dist file `client.js` in `node_modules/vite/dist/client/client.js` line 23

if the pr 677 merged, has config for socketPort, this can be ignore


```js
// before
// const socketUrl = `${socketProtocol}://${location.hostname}:${__PORT__}`;

// after
// modify the port you expose from docker
const socketUrl = `${socketProtocol}://${location.hostname}:10080`;
```