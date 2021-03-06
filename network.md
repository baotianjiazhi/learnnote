# HTTP

## HTTP中主要的头字段

<img src="C:\Users\bao\AppData\Roaming\Typora\typora-user-images\image-20201203221854622.png" alt="image-20201203221854622" style="zoom:80%;" />

​                                      <img src="C:\Users\bao\AppData\Roaming\Typora\typora-user-images\image-20201203221915563.png" alt="image-20201203221915563" style="zoom:80%;" />

![image-20201203221957799](C:\Users\bao\AppData\Roaming\Typora\typora-user-images\image-20201203221957799.png)

![image-20201203222020729](C:\Users\bao\AppData\Roaming\Typora\typora-user-images\image-20201203222020729.png)

## DNS

缓存的执行顺序：浏览器DNS缓存>操作系统DNS缓存>HOST文件

### 递归查询

![递归查询](F:\学习笔记\network\递归查询.jpg)

### 迭代查询

![迭代查询](F:\学习笔记\network\迭代查询.jpg)

# WebSocket

> WebSocket 是一种网络传输协议，可在单个 TCP 连接上进行全双工通信，位于 OSI 模型的应用层。 WebSocket 协议在 2011 年由 IETF 标准化为 RFC 6455，后由 RFC 7936 补充规范。Web IDL 中的 WebSocket API 由 W3C 标准化。
>
> WebSocket 使得客户端和服务器之间的数据交换变得更加简单，允许服务端主动向客户端推送数据。在 WebSocket API 中，浏览器和服务器只需要完成一次握手，两者之间就可以创建持久性的连接，并进行双向数据传输。

WebSocket的优点:

- 较少的控制开销。在连接创建后，服务器和客户端之间交换数据时，用于协议控制的数据包头部相对较小。在不包含扩展的情况下，对于服务器到客户端的内容，此头部大小只有 2 至 10 字节（和数据包长度有关）；对于客户端到服务器的内容，此头部还需要加上额外的 4 字节的掩码。相对于 HTTP 请求每次都要携带完整的头部，此项开销显著减少了。
- 更强的实时性。由于协议是全双工的，所以服务器可以随时主动给客户端下发数据。相对于 HTTP 请求需要等待客户端发起请求服务端才能响应，延迟明显更少；即使是和 Comet 等类似的长轮询比较，其也能在短时间内更多次地传递数据。
- 保持连接状态。Websocket 是一种有状态的协议，通信前需要先创建连接，之后的通信就可以省略部分状态信息了。而 HTTP 请求可能需要在每个请求都携带状态信息（如身份认证等）。
- 更好的二进制支持。Websocket 定义了二进制帧，相对 HTTP，可以更轻松地处理二进制内容。
- 可以支持扩展。Websocket 定义了扩展，用户可以扩展协议、实现部分自定义的子协议。如部分浏览器支持压缩等。
- 更好的压缩效果。相对于 HTTP 压缩，Websocket 在适当的扩展支持下，可以沿用之前内容的上下文，在传递类似的数据时，可以显著地提高压缩率。

## 面试问题集合

1. 向 DNS 服务器发送请求消息的程序叫什么？

解析器

2. 下面两个网址有什么不同？

  a. http://www.nikkeibp.co.jp/sample

  b. http://www.nikkeibp.co.jp/sample/

a中的sample代表文件名，b中的sample代表目录名

