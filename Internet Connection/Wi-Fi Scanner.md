```C++
char *getAuthModeName(wifi_auth_mode_t wifi_auth_mode)
{
    switch (wifi_auth_mode)
    {
    case WIFI_AUTH_OPEN:
        return "WIFI_AUTH_OPEN";
    case WIFI_AUTH_WEP:
        return "WIFI_AUTH_WEP";
    case WIFI_AUTH_WPA_PSK:
        return "WIFI_AUTH_WPA_PSK";
    case WIFI_AUTH_WPA2_PSK:
        return "WIFI_AUTH_WPA2_PSK";
    case WIFI_AUTH_WPA_WPA2_PSK:
        return "WIFI_AUTH_WPA_WPA2_PSK";
    case WIFI_AUTH_WPA2_ENTERPRISE:
        return "WIFI_AUTH_WPA2_ENTERPRISE";
    case WIFI_AUTH_WPA3_PSK:
        return "WIFI_AUTH_WPA3_PSK";
    case WIFI_AUTH_WPA2_WPA3_PSK:
        return "WIFI_AUTH_WPA2_WPA3_PSK";
    case WIFI_AUTH_WAPI_PSK:
        return "WIFI_AUTH_WAPI_PSK";
    case WIFI_AUTH_OWE:
        return "WIFI_AUTH_OWE";
    case WIFI_AUTH_MAX:
        return "WIFI_AUTH_MAX";
    }
    return "UNKNOWN";
}

wifi_ap_record_t wifi_records[MAX_APs];

esp_wifi_scan_get_ap_records(&max_record, wifi_records);

wifi_scan_config_t wifi_scan_config = {
    .show_hidden = true,
    .channel = 13};
esp_wifi_scan_start(&wifi_scan_config, true);
```

![wifi channel](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/wifi%20channel.png)


# Words
- wharf 码头
- WPA（Wi-Fi Protected Access）是一种用于保护无线网络安全的安全协议。它是Wi-Fi网络中的一种加密标准，旨在代替WEP（Wired Equivalent Privacy）协议，因为WEP存在安全漏洞而不再安全。<br>

主要特点包括：<br>
1. **动态密钥：** WPA使用动态密钥的概念，即每个数据包都使用不同的加密密钥。这使得破解密钥变得更加困难，增加了网络的安全性。<br>
2. **消息完整性检查：** WPA支持消息完整性检查，可以检测到数据包是否被篡改，从而防止数据被恶意修改。<br>
3. **TKIP加密：** WPA使用TKIP（Temporal Key Integrity Protocol）加密算法，它是一种临时密钥完整性协议，可以增加密钥的复杂性，并提高安全性。<br>
4. **预共享密钥：** WPA支持预共享密钥（PSK）模式，允许用户使用预先共享的密钥进行认证，简化了网络配置过程。<br>



