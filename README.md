# Stock

TW Stock analysis use "linear regression" & "Fourier Transform"

股市的分析, 是一套永久的謎底??

技術分析 : 是指單從線圖出找出關係來預測未來的股價!!

這裡使用離散傅立葉分析(Discrete Fourier Transform), 將一個訊號拆解成多個不同"頻率"(頻率倍數1.2.3...)的諧和波(不同相位的正弦餘弦波)組合, 並選用"震幅"排序比較大的幾組波形來組合成主要波形, 配合模擬市場的主要波動值(例如季節性的影響, 一個禮拜的影響之類!!), 同時傅立葉在工程上最重要的應用, 過濾掉不需要的頻率波形(雜訊), 進而預測接下來的走勢!!

可是光使用傅立葉分析, 會出現的問題就是, 之後的預測只是原資料的延伸(或前半段), 例如使用100天預測 10天, 預測的那 10天只是最早 100天的前 10天數值!!, 這是因為我們假設拆解的波形都會持續地發生的緣故(這不是一個完美的假設), 加上 線性迴歸(linear regression), 讓整體預測有更合理的情況!!

試想一段持續上升的波形, 預測卻是跌回第一天情況!! 明顯會發生不合理的情況~ 這裡將這條持續上升的波形使用線性迴歸整平, 在家整平的線路使用傅立葉分析拆解成波形!!

另外, 選用平方平均數來表示預測的表現, 並且配合不同的公司, 需要將股價做一次正規化(平均值 = 0, val = "n", n倍標準差)讓不同價位有比較基準!!

