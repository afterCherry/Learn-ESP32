```C++
// 计算机后端的啊
esp_http_client_config_t esp_http_client_config = {
    .url = "http://api.quotable.io/random",
    .method = HTTP_METHOD_GET,
    .event_handler = on_client_data};
esp_http_client_handle_t client = esp_http_client_init(&esp_http_client_config);
esp_http_client_set_header(client, "Content-Type", "application/json");
esp_err_t err = esp_http_client_perform(client);
```
![backend](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/totally%20backend.png)
![connect error](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/client%20connect%20error.png) <br>

