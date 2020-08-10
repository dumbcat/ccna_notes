# Network Characteristics 網路要注意的特性

+ Topology 拓樸主要探討的是拓樸的架構，與實體拓樸和邏輯拓樸

+ Bitrate or bandwidth 位元速率與頻寬用來量測資料在網路上傳輸的速度

+ Availability 可用性是量測網路在一定時間內可以使用的時間的百分比

+ Reliability 可靠性是量測網路在一定時間內故障的次數，來推論每兩次故障間隔的時間

+ Scalability 可擴展性是指網路要可以良好的容納更多的使用者或者資料傳輸的需求

+ Security 安全性是指資料在網路上傳輸的安全性

+ Quality of Service(QoS) 服務品質

+ Cost 成本包含了網路中的元件，與安裝、維護的成本

+ Virtualization 虛擬化

## 1. Availability Calculate 可用性計算

假設 Device_X 每小時重新開機一次，每次開機五分鐘

```
Availability = ( total uptime in a day in minutes / total minutes in a day ) * 100
             = ( 24 * 55 / 24 * 60 ) * 100
             = 91.67%
```
## 2. Reliability Calculate 可靠性計算

假設 Device_X 每小時重新開機一次，每次開機五分鐘

```
Reliability = total minutes in a day / number of failures in a day
            = 24 * 60 / 24
            = 60 minutes
```

## 3. Physical and Logical Topologies 實體與邏輯拓樸

+ Physical Topology:

  用來說明網路上的工作站主機與網路線間的佈線關係，以及其他網路元件的位置

  主要的有匯流排拓樸、環狀拓樸、星狀拓樸、網狀(mesh)拓樸

+ Logical Topology:

  用來定義資訊如何在網路中進行傳輸

  例如電腦與伺服器之間雖然只隔著一台交換機，但是資料可能是經過交換機之後，先送到路由器或防火牆之後才再送回交換機，再傳送到伺服器

# Impact of User Application on the Network 使用者應用程式對網路的影響

## 1. 依照資料類型

+ Data

  + Smooth / Bursty: 傳輸的資料量可能是平順的，也有可能有突然爆發式的大量資料

  + Benign / Greedy: 可能與其他應用程式和善的使用頻寬，也有可能貪婪的搶奪頻寬

  + Drop-Insensitive: 對封包遺失不敏感

  + Delay-Insensitive: 對延遲不敏感

+ Voice

  + Smooth: 傳輸的資料量可能是平順的

  + Benign: 與其他應用程式和善的使用頻寬

  + Drop-Sensitive: 對封包遺失敏感

  + Delay-Sensitive: 對延遲敏感

  + One-Way Requirements 單向要求

    + Latency(延遲) <= 150 ms 

    + Loss(封包遺失率) <= 1% 

    + Bandwidth(頻寬) (30-128Kbps)

+ Video

  + Bursty: 有突然爆發式的大量資料

  + Greedy: 與其他應用程式貪婪的搶奪頻寬

  + Drop-Sensitive: 對封包遺失敏感

  + Delay-Sensitive: 對延遲敏感

  + One-Way Requirements 單向要求

    + Latency(延遲) <= 150 ms

    + Loss(封包遺失率) <= 0.1-1%

    + Bandwidth(頻寬) (384Kbps-20+Mbps)

## 2. 依照應用程式種類

+ Batch Application 批次應用程式

  + 例如伺服器之間排程的資料交換，過程中沒有直接與人互動

  + 頻寬重要但是不緊急(cirtical)

+ Interactive Appication 互動應用程式

  + 例如資料庫查詢，屬於人與機器之間的互動

  + 回應時間與頻寬重要但是不緊急(cirtical)

+ Real-Time Application 即時應用程式

  + 例如視訊通話，屬於人與人之間的互動

  + 終端到終端的延遲很緊急(cirtical)
