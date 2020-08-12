# Router 路由器

+ 利用路由表在網路之間路由，可以訪問不在區域網路中的主機

+ 主要功能:

  + 決定路徑

  + 封包轉送

# 路由表

+ 在 Privileged EXEC Mode 輸入 show ip route 可以看到路由表

  ```
  C 10.0.0.0/16 is directly connected, GigabitEthernet0/0/0
  L 10.0.0.2/32 is directly connected, GigabitEthernet0/0/0
  O 172.16.1.0/24 [110/2] via 192.168.10.2, 00:03:23, GigabitEthernet0/0/1
  ```
  直接連線路由表分成三個部分
  
  |Route Source|Destination Network|Administrative Distance|Metric|Next-hop|Route Timestamp|Outgoing Interface|
  |---|---|---|---|---|---|---|
  | C | 10.0.0.0/16 is directly connected, |||||GigabitEthernet0/0/0 |
  | L | 10.0.0.2/32 is directly connected, |||||GigabitEthernet0/0/0 |
  | O | 172.16.1.0/24 |[110/|2]|via 192.168.10.2,|00:03:23,|GigabitEthernet0/0/0 |

  + Route Source: 路由器本身的介面會顯示 directly connected，直接連線的路由中 C 表示一個網段，L 表示一個分配給路由器介面的 IPv4 位址
    
    其他的還有 O 表示 OSPF 路由，R 表示 RIP 路由，S 表示靜態路由，S* 表示預設路由，D 表示 EIGRP 路由等。

  + Destination Network: 目標網段

  + Administrative Distance: 不同的 Route Protocol 有不同的 AD 值，數值越低優先權越高，在 Cisco 中 直接連線的 AD 是 0，靜態路由是 1，EIGRP 是 90，OSPF 是 110

  + Metric: 在相同路由協定下比較 Metric 值，數值越低表示優先權越高

  + Next-hop: 該路由下一個目的地，也就是下一個路由器的介面 IP 位址

  + Route Timestamp: 該路由已經發現了多久，只會出現在動態路由中

  + Outgoing Interface: 要去目標網段的話要由該路由器的哪個介面出去

  + 封包在經過 AD 值比較之後，會尋找相同 AD 值中 網址最符合的路徑前往，例如目標是 192.168.10.0/24，在相同 AD 值中有 192.168.0.0/16 與 192.168.10.0/20，路由器會選擇最符合也就是 Prefix 最長的 192.168.10.0/20 的路徑