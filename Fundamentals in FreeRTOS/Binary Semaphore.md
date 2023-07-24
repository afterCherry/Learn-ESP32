# Internet for Project
ESP32 talks to the Internet and act as a web server.
```C++
void listenForHTTP(void *params)
{
  while (true)
  {
    printf("received http message\n");
    xSemaphoreGive(binSemaphore);
  }
}

void task1(void *params)
{
  while (true)
  {
    xSemaphoreTake(binSemaphore, portMAX_DELAY);
  }
}
```


# Words
- HTTP Socket: 用于在计算机网络中进行HTTP通信的一种通信协议。在HTTP通信中，客户端（通常是Web浏览器）与服务器之间通过HTTP Socket建立连接，以便进行数据的传输和交换。<br>

HTTP Socket的工作流程如下：<br>
1. 客户端发起HTTP请求：客户端通过HTTP Socket向服务器发送HTTP请求，请求特定的资源或执行特定的操作。<br>
2. 服务器响应：服务器接收到客户端的请求后，通过HTTP Socket向客户端发送HTTP响应，包含请求的结果或所需的资源。<br>
3. 连接维持：在一次HTTP通信中，HTTP Socket会保持连接，以便在同一连接上进行多次请求和响应，从而提高通信的效率。<br>
4. 连接关闭：一旦HTTP通信完成或超时，HTTP Socket会关闭连接，释放相关资源。<br>
- semaphore 信号
