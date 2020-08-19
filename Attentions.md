# ch 5.

+ 交換機雙工模式預設是 auto

+ 兩台交換之間的連線，如果一台是全雙工，一台是半雙工，則該連線不會啟用

+ 兩台交換之間的連線，如果一台是 100 Mb/s，一台是 10Mb/s，則該連線速度會降為 10Mb/s

# ch 6.

+ interface up, line protocol up: 運作正常
    
+ interface up, line protocol down: 資料鏈結層的問題，通常是設定問題，例如兩個埠口之間的協定不相同

+ interface down, line protocol down: 實體層的問題，例如線路異常

+ interface administratively down, line protocol down: 埠口被禁用

# ch 7.

+ 切割子網的算法

+ 子網多切了 1 個 bit，表示可切出 2^1 = 2 個子網，每個子網有 2^(8 - 1) - 2 = 126 個主機位址

+ 子網多切了 5 個子網 bit，表示可切出 2^5 = 32 個子網，每個子網有 2^(8 - 5) - 2 = 6 個主機位址

+ borrowing bits 的最後一位在 IP 的第幾個區段的第 N 個 bit(最右邊是第 1 個 bit)，也就是每 2^N 切出一個網段(第 1 個 bit 是 2^0 = 1)

# ch 8.

+ `Router(config-if)# ip helper-address {dhcp-server-ip}`

    DHCP 是靠廣播 (Broadcast) 傳送的，但是廣播封包無法通過路由器，如果 DHCP Server 與 DHCP Client 在不同一個網段，Client 就無法配發到 IP 了，這時候可以使用 DHCP Relay (或稱為 IP Helper)，轉送 DHCP Client 的廣播到 DHCP Server 以能將 IP 發到 Client

+ 設定 Router 為 DHCP Server

    ```
    Router(config)# ip dhcp excluded-address {排除的 IP}
    Router(config)# ip dhcp pool {pool-name}
    Router(dhcp-config)# network {發配的網段}
    Router(dhcp-config)# default-router {發配的 Default Gateway}
    Router(dhcp-config)# dns-server {發配的 DNS}
    Router(dhcp-config)# domain-name {發配的 Domain-name}
    Router(dhcp-config)# lease 0 12
    Router(dhcp-config)# exit
    ```

# ch 9.

+ 路由表主要架構: 目的網段 + 下一個路由介面 + 自己要送出的介面

# ch 10.

+ `show cdp neighbors` 查 CDP 表

# ch 11.

+ `show ip arp` 或 `show arp` 查 ARP 表