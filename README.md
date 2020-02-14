# 個股期貨短線交易策略：
挑選日振幅大、且成交量別太低的個股期貨，依據日振幅`滿足前的`順勢`交易v.s.滿足後的`逆勢`交易

預期日振幅會朝月均日振幅`均值回歸`，即某股票若早盤強勢於大盤、且當下振幅未達月均日振幅時，就做多；若已超過振幅平均門檻、且過了午盤之後仍未創當日新高，亦即動能衰退，就逆勢做空，預期該標的會回落。
- - -
### 流程大綱：
1. [群益API開通](https://www.capital.com.tw/Service2/download/api.asp)才能取得免費且不怕被鎖網路IP的股價資訊。
>1. 使用群益的疑難問題，可參考[群益api in python 取得歷史報價](https://easontseng.blogspot.com/2017/08/api-in-python.html)
>2. 亦可使用[twstock](https://github.com/mlouielu/twstock)套件替代群益API，唯此套件抓資料過於頻繁時會鎖網路IP

2. 設計函式：振幅趨勢是看中期方向的，故用日k為單位，算的是`振幅`

3. 擬定`股票清單`，去除掉成交量太差且股性太沉悶的股票期貨，本篇以成交量為例，挑出日均量100之上的股期，再依月均日振幅3.5%為界，區分高振幅v.s.低振幅，畢竟仍然是肉眼盯盤，盤中注意力優先關注高動波的標的。

4. 振幅群組圖像化
>1. 全丟進去算，但只顯示高於門檻的標的，定義該群組為高波動
>2. 剩下沒被選出的那就是低波動了
>* 可看振幅近3個月的趨勢，判斷近期市場氛圍是動盪還沉悶
>* 可再對感興趣的個股畫小提琴圖，觀察振幅的`眾數`vs`極端值`的分佈，適時排除股性太過詭異、振幅分佈過於厚尾的標的
 
5. 結論：策略有其對應適合的情行／像2019年死多頭振幅小，盤中不能多空兩頭賺，只好研究`創短期新高(新低)佐以優質k棒`的選股策略，將另篇討論。
    
6. 參考資料：

感謝以下社群的版主與熱情網友幫忙回帖
>* 臉書社群[Fintech.py](https://www.facebook.com/groups/1805224676441902/)
>* 臉書社群[Finlab - Python選股](https://www.facebook.com/groups/1851056405186661/)
>* 部落格[Eason's 記事本](https://easontseng.blogspot.com/)
- - - 
