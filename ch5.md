# UTP 纜線

## 1. Straight-Through Cable

+ Side A: 白橘、橘、白綠、藍、白藍、綠、白棕、棕

+ Side B: 白橘、橘、白綠、藍、白藍、綠、白棕、棕

+ 用途: Switch to Router, Switch to PC, Switch to Server

## 2. Crossover Cable

+ Side A: 白橘、橘、白綠、藍、白藍、綠、白棕、棕

+ Side B: 白綠、綠、白橘、藍、白藍、橘、白棕 (白橘、橘跟白綠、綠對換)

+ 用途: Switch to Switch, Router to Router, Router to PC, PC to PC

# 光纖

## 1. Color 顏色

+ 單模: 黃色

+ 多模: 橘色(OM2)或水綠色(OM3)

## 2. Connector 連接器

+ SC: 大方頭

+ ST: 大圓頭

+ LC: 小方頭

# MAC Address

+ 共 48 bits，前 24 bits 是 IEEE 分配的組織唯一識別碼 (Organizationally unique identifier)，後 24 bits 是網路設備商自行指定的唯一碼

+ MAC address 第一個 8 bits 的第一個 bit 為 0 表示是單播位址 (Individual address)，代表一個唯一的網路設備；若是 1 表示是群播位址 (Group address)，代表一群網路設備

+ MAC address 第一個 8 bits 的第二個 bit 為 0 表示是 0 表示是全球管理地址 (Globally administered address)，表示這是OUI發配的地址，若是 1 表示這是本地管理地址 (Locally administered address)，是設備商自行定義的地址

+ 交換機只會紀錄傳送**進來**的封包的 MAC address 到 MAC table

# Duplex 雙工

## 1. Half Duplex 半雙工

+ 單向資料流

+ 舊式的連接方式

+ 封包碰撞會是一個問題

## 2. Full Duplex 全雙工

+ 用於點對點之間

+ 需要連接到特定的交換機埠口

+ 兩點都需要支援全雙工

## 3. Attention 注意事項

+ 交換機雙工模式預設是 auto

+ 兩台交換之間的連線，如果一台是全雙工，一台是半雙工，則該連線不會啟用

+ 兩台交換之間的連線，如果一台是 100 Mb/s，一台是 10Mb/s，則該連線速度會降為 10Mb/s