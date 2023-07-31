# http client
just to get a web page.
```C++
#include "protocol_examples_common.h"
#include "esp_http_client.h"

esp_err_t client_event(esp_http_client_event_t *evt)

esp_http_client_config_t esp_http_client_config = {
    .url = "https://google.com",
    .event_handler = client_event};
```

![sdk configuration](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/sdk%20configuration.png) <br>

connect to html successful.
![successful](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/connect%20to%20html%20successful.png)
