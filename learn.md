创建每个需要发送的消息对应的消息对象，其中包括 message id 等数据。在发送数据时将这些消息对象存到 ws2promise 数组中
在 onmessage 中，接收到数据就将对应的消息对象从 ws2promise 数组中清除。
然后在 close 事件中不对任何 WebSocket 传递的参数进行处理，只是单纯地将 ws2promise 全部执行每个消息对象的 reject 函数
