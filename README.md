# 將傳統電器轉換為 IoT 裝置以智能控制

在當今的智能家居時代，越來越多的家庭開始尋求將傳統家電轉換為智能裝置，以實現遠程控制、自動化操作等功能。本文將介紹如何使用米家繼電器模塊將傳統電器的按鈕轉換為 IoT 裝置，從而實現對傳統家電的智能控制。

# 米家繼電器模塊簡介

米家繼電器模塊是一款可以通過藍芽連接到智能家居系統的設備。它允許用戶通過米家APP或語音助手遠程控制連接到模塊的電器。繼電器模塊的核心功能是能夠控制(短路, 通路)電路的開關，從而實現對電器的遠程控制。以此模塊為例有四個型號，至多可以控制4路，也就是四個按鈕。
並且體積非常的小，可以在不破壞電器外觀的狀況下將繼電器模塊塞到電器內部。

![image](https://github.com/ForisC/IoT-Traditional-Devices/assets/52095287/257547e3-4a55-40df-8f13-15b6e196c84d)


# 原理解釋

傳統電器的按鈕通常是通過微動開關來實現控制的。當按鈕被按下時，微動開關會短路，從而讓電流流通並啟動電器。

![image](https://github.com/ForisC/IoT-Traditional-Devices/assets/52095287/76e314c8-41ab-49a4-bc52-99c311b28148)


以上圖為例，pin 1 等於 pin 3，pin 2 等於 pin 4，當按下按鈕時，pin 1,3 與 pin 2,4 將會接通 (短路)

米家繼電器模塊可以模擬這個短路過程，從而實現對電器的遠程控制。當繼電器接收到開啟或關閉的指令時，它會相應地連接或斷開電路，從而模擬按鈕的按下或釋放。


# 配置智能家居系統

在開始改裝電器之前，先確認繼電器模塊功能正常並能夠APP正常操作。

此模塊支援 5V USB typc-C 供電或是 5~30V 供電。當使用 USB 供電時，請使用 5V 1A 的變壓器，不支援PD變壓器。

1. 打開米家APP (限定登入為 CN 帳號，台灣帳號找不到此裝置) 
2. 在米家應用程式中添加繼電器模塊。
3. 將開關設置成點動模式。

    ![image](https://github.com/ForisC/IoT-Traditional-Devices/assets/52095287/7e6b7d47-d856-40f6-bf70-99688e59b9df)
    ![image](https://github.com/ForisC/IoT-Traditional-Devices/assets/52095287/831466d8-19cf-4ec1-97d2-69a2fc765ed4)
    ![image](https://github.com/ForisC/IoT-Traditional-Devices/assets/52095287/55c2ecd3-908b-4e79-bc40-9222f367d64c)



   * 普通模式開關：click -> on -> click -> off -> click -> on
   * 靈動開關模式: always on -> click -> off -> resume to on 
   * 點動開關模式: always on or off -> click -> switch -> sleep -> resume to original state





# 實施步驟

1. 在此我要改裝的電器是 NICONICO 的捕蚊燈。

    ![image](https://github.com/ForisC/IoT-Traditional-Devices/assets/52095287/5c886075-3ff8-4281-9b50-3ba7b645ff70)


3. 拆開外殼，確保你要控制的電器使用的是微動開關按鈕。此捕蚊燈有兩個按鈕，我的目標是左邊的電源按鈕。

    ![image](https://github.com/ForisC/IoT-Traditional-Devices/assets/52095287/51a64600-20c4-4a4d-b2f0-a44362847af0)

4. 尋找供電，在此我找到一個 JST 2mm 2pin cable 是此電路板的供電，其電壓是 6.5V，剛好符合繼電器模塊的工作電壓。

    ![image](https://github.com/ForisC/IoT-Traditional-Devices/assets/52095287/d4aac8ac-71c5-4c58-8712-ca52dcad6bfc)

5. 由於不想破壞原本的線路，我製作了一條 1 to 2 的 cable，來為原本的電路板與繼電器供電。
    ![image](https://github.com/ForisC/IoT-Traditional-Devices/assets/52095287/18a0f21c-e67b-42dd-b434-eaea6712d0fb)

6. 斷開電器的電源。
7. 將繼電器模塊的兩根控制線分別連接到微動開關的兩個接點上。並接上繼電器模塊電源。圖中我已經用絕緣膠帶將繼電器模塊包住。

    ![image](https://github.com/ForisC/IoT-Traditional-Devices/assets/52095287/9ba48144-a64b-4615-8d2c-965bc986235e)

7. Enjoy it
   
    ![2024_0218_151-ezgif com-resize](https://github.com/ForisC/IoT-Traditional-Devices/assets/52095287/7136032e-30d3-45a7-b21f-1e6b3541019e)


