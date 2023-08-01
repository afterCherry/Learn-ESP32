# init
## main.c
```C++
nvs_flash_init();
wifi_connect_init();

// ESP as a station
esp_err_t err = wifi_connect_sta("POCO", "password", 10000);
```

## wifi_connect.h
```C++
#ifndef WIFI_CONNECT_H
#define WIFI_CONNECT_H

void wifi_connect_init(void);

#endif
```

## wifi_connect.c
```C++
void wifi_connect_init(void)
{
    ESP_ERROR_CHECK(esp_netif_init());
    ESP_ERROR_CHECK(esp_event_loop_create_default());
    wifi_init_config_t wifi_init_config = WIFI_INIT_CONFIG_DEFAULT();
    ESP_ERROR_CHECK(esp_wifi_init(&wifi_init_config));
    ESP_ERROR_CHECK(esp_event_handler_register(WIFI_EVENT, ESP_EVENT_ANY_ID, event_handler, NULL));
    ESP_ERROR_CHECK(esp_event_handler_register(IP_EVENT, IP_EVENT_STA_GOT_IP, event_handler, NULL));
    ESP_ERROR_CHECK(esp_wifi_set_storage(WIFI_STORAGE_RAM));
}
```

# Station
```C++
esp_err_t wifi_connect_sta(char *ssid, char *pass, int timeout)
{
    wifi_events = xEventGroupCreate();
    esp_netif = esp_netif_create_default_wifi_sta();
    ESP_ERROR_CHECK(esp_wifi_set_mode(WIFI_MODE_STA));

    // for static ip...
    // ESP_ERROR_CHECK(esp_netif_dhcpc_stop(esp_netif));
    // esp_netif_ip_info_t ip_info;
    // ip_info.ip.addr = ipaddr_addr("192.168.43.150");
    // ip_info.gw.addr = ipaddr_addr("192.168.43.1");
    // ip_info.netmask.addr = ipaddr_addr("255.255.255.0");
    // ESP_ERROR_CHECK(esp_netif_set_ip_info(esp_netif, &ip_info));

    wifi_config_t wifi_config = {};
    strncpy((char *)wifi_config.sta.ssid, ssid, sizeof(wifi_config.sta.ssid) - 1);
    strncpy((char *)wifi_config.sta.password, pass, sizeof(wifi_config.sta.password) - 1);
    ESP_ERROR_CHECK(esp_wifi_set_config(WIFI_IF_STA, &wifi_config));
    ESP_ERROR_CHECK(esp_wifi_start());

    EventBits_t result = xEventGroupWaitBits(wifi_events, CONNECTED | DISCONNECTED, true, false, pdMS_TO_TICKS(timeout));
    if (result == CONNECTED)
        return ESP_OK;
    return ESP_FAIL;
}
```

# Error

# AP
```C++
wifi_config_t wifi_config = {};
strncpy((char *)wifi_config.sta.ssid, ssid, sizeof(wifi_config.sta.ssid) - 1);
strncpy((char *)wifi_config.sta.password, pass, sizeof(wifi_config.sta.password) - 1);
ESP_ERROR_CHECK(esp_wifi_set_config(WIFI_IF_STA, &wifi_config));
ESP_ERROR_CHECK(esp_wifi_start());

```

# Disconnection
refer to the source code
![source code](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/source%20code.png) <br>
![connect successfully](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/connect%20successful.png)


# Words
- WPA（Wi-Fi Protected Access）和WPA2（Wi-Fi Protected Access 2）：两种不同的无线网络安全协议，它们在加密算法和安全性方面有一些不同之处。下面是它们之间的主要区别：<br>

1. **加密算法：**<br>
WPA：WPA使用TKIP（Temporal Key Integrity Protocol）作为其主要加密算法。TKIP是一种较早的加密算法，用于替代WEP（Wired Equivalent Privacy）并增强网络的安全性。<br>
WPA2：WPA2使用更高级的加密算法，如CCMP（Counter Mode with Cipher Block Chaining Message Authentication Code Protocol），它基于AES（Advanced Encryption Standard）。AES是一种更强大的加密算法，被认为是目前最安全的对称加密算法之一。<br>

2. **安全性：** <br>
WPA：由于WPA使用较旧的TKIP算法，它相对于WPA2来说较不安全。虽然WPA相对于WEP有了显著的改进，但仍然存在一些安全漏洞，可能会受到一些攻击方法的影响。<br>
WPA2：WPA2在安全性方面较为强大，其使用的CCMP/AES加密算法提供了更高级的数据保护，对于常见的攻击方法有更好的防御能力。<br>

3. **支持情况：** <br>
WPA：WPA是WPA2之前的版本，较新的设备通常也支持WPA。 <br>
WPA2：WPA2是WPA的后继版本，现代无线设备普遍支持WPA2。<br>
