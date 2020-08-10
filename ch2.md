# Benefits of Using a Communications Model 使用通訊模型的好處

+ Manage complexity 管理複雜性 (?

+ Define and specify communication task 定義與指定通訊任務

+ Facilitates modular engineering 促進模組化工程

+ Contain changes 包含改變 (?

+ Accelerate evolution 加速演化

+ Facilitate teaching and learning 促進教學

# ISO OSI Reference Model OSI模型

+ Application(應用層): Network Process to Application

  + 為應用程序提供網路服務(例如電子郵件、檔案傳輸、與虛擬終端機(terminal emulation))

  + 提供使用者認證

+ Persentation(表現層): Data Representation

  + 確保資料在接收的系統是可讀的

  + 格式化資料

  + 結構化資料

  + 協商應用層的資料傳輸語法(syntax)

  + 提供加密

+ Session(會議層): Interhost Communication

  + 建立、管理、與終止應用程式間的會話(sessions)

+ Transport(傳輸層): End-to-End Connections

  + 處理主機間傳輸的問題

  + 確保數據傳輸的可靠性(reliability)

  + 建立，維護和終止[虛擬電路](https://zh.wikipedia.org/wiki/%E8%99%9B%E6%93%AC%E9%9B%BB%E8%B7%AF)(virtual citcuits)

  + 透過故障檢測與復原，以及資訊流量控制提供可靠性

+ Network(網路層): Data Delivery

  + 路由資料封包

  + 選擇傳遞資料的最佳路徑

  + 提供邏輯定址(logical addressing)與路徑選擇

+ Data Link(資料鏈結層): Access to Media

  + 定義如何格式化(formatted)數據以進行傳輸，以及如何控制對網路的存取

  + 提供錯誤檢測

+ Physical(實體層): Binary Transmission

  + 定義用於啟用、維護、停用實體鏈路的電氣(electrical)、機械(mechanical)、過程(procedural)、和功能(functional )的規範

  # TCP/IP Protocol Suite

  + Application(應用層) - 對應OSI Application, Presentation, Session層

    + 向使用者展示資料，以及編碼和對話框(dialogue)控制

  + Transport(傳輸層) - 對應OSI Transport層

    + 支援跨各種網路的終端設備之間的通訊

  + Internet(網路互連層) - 對應OSI Network層

    + 提供邏輯定址與決定通過網路的最佳路徑

  + Link(Netork Access)(鏈結(網路存取)層) - 對應OSI Data Link, Physical層

    + 控制構成網路的硬體設備與媒介

# PDU(Protocol Data Unit) 協定資料單元

+ Application層的PDU是指data

+ Transport層的PDU是指segment，是由data加上segment header包裝而成

+ Internet層的PDU是指packet，是由segment加上packet header包裝而成

+ Link(Netork Access)層的PDU是指frame，是由packet加上frame header包裝而成

+ 數據的傳送將data是由上層(Application)包裝到下層(Link)，PDU由data包裝為frame；接收是將frame由下層拆解到上層，PDU由frame拆解為data