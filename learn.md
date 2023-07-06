创建每个需要发送的消息对应的消息对象，其中包括 message id 等数据。在发送数据时将这些消息对象存到 ws2promise 数组中
在 onmessage 中，接收到数据就将对应的消息对象从 ws2promise 数组中清除。
然后在 close 事件中不对任何 WebSocket 传递的参数进行处理，只是单纯地将 ws2promise 全部执行每个消息对象的 reject 函数

计时器时用 web worker 来实现的


断网逻辑：
断网之后执行一次 reconnect 就没有继续了，应该是要用户自己去实现这部分逻辑

合盖休眠逻辑：
也是 b 事没干，就抛出 close 事件错误