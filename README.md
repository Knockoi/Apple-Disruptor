# 更改至EvilAppleJuice ESP32  還在修改更適合的功能

iPhone 上的垃圾 BLE 廣告！

|iPhone15s(最新)|舊款iPhone||iPhone15s(最新)|舊款iPhone||iPhone15s(最新)

通過隨機化優化，只需使用一個 ESP32，它就能讓 iPhone 幾乎毫無用處（只要關閉舊通知，就會出現新通知）。

已在以下設備上證實：
* iPhone 14 Pro（運行 iOS 16.6.1）
* iPhone 13 Pro（運行 iOS 系統，具體待定）
* iPhone 11（運行 iOS 16.6.1）
* iPhone X（運行 iOS 14.8 (18H17)）- 僅支持 "AppleTV 鍵盤"、"電視色彩平衡"、"AppleTV 設置"、"AppleTV Homekit 設置 "和 "AppleTV 新用戶"。

無法在以下設備上運行
* iPhone 4S（運行 iOS 10.3 (14E277)

其他觀察結果：
* 鍵盤打開/攝像頭打開時似乎不會產生通知

### 顯著差異

該實現做出了以下更改：

* 隨機源 MAC 地址（包括 `BLE_ADDR_TYPE_RANDOM`）。
* 隨機選擇 BLE 廣告類型（[這可能會導致更多成功](https://github.com/ECTO-1A/AppleJuice/pull/25)
* 從可能的設備中隨機選擇一個

每次運行時都會進行這些隨機選擇（默認每秒重新發布一次廣告）。

考慮到 29 種設備和 3 種廣告類型，總共有 87 種可能的廣告（忽略隨機源 MAC），其中每秒廣播一次。

### 使用方法

打開 scr裡面的ino 檔案後點擊項目，利用添加文件點選 scr裡面的 hpp 檔案，等一接上電源就可使用了！

