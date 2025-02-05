# 期中報告
* 主題：聚類演算法
* 班級：資工三
* 姓名：陳艾葳
* 學號：110810523
* 作品說明：非原創(參考資料文末附註)
# 聚類演算法

## 常用的聚類演算法
+ K-均值
+ K-中位數
+ EM 演算法
+ 分層聚類演算法

## 類型
+ 結構性
  
  結構性演算法：
  利用已成功使用過的聚類器進行分類。可以雙向進行計算。
  + 凝聚層次聚類：AGNES演算法(自底向上)
  將每個物件作為一個簇，然後合併這些原子簇為越來越大的簇，直到某個終結條件被滿足
  + 分裂層次聚類：DIANA演算法(自頂向下)
  將所有物件置於一個簇中，然後逐漸細分為越來越小的簇，直到達到了某個終結條件。
  

  
+ 分散性
  ```
  分散式聚類演算法，是一次性確定要產生的類別，這種演算法也已應用於從下至上聚類演算法。
  ```
## 結構性聚類
```
  在得到距離值之後，通過分離和融合可以構建一個結構。傳統上，表示的方法是樹形資料結構，再對該結構進行修剪。樹的根節點表示一個包含所有專案的類別，樹葉表示與個別的專案相關的類別。

  層次聚類演算法，要麼是由下而上聚集型的，即從葉子節點開始，最終匯聚到根節點；要麼是自頂向下分裂型的，即從根節點開始，遞迴的向下分裂。

  任意非負值的函式都可以用于衡量一對觀測值之間的相似度。決定一個類別是否分裂或者合併的是一個連動的標準，它是兩兩觀測值之間距離的函式。

  在一個指定高度上切割此樹，可以得到一個相應精度的分類。
  ```
### 聚集型層次聚類
![Raw data](https://github.com/laiy790/sa110a/blob/master/mid/photo/1.png)
### 層次聚類樹如下圖
![Traditional representatio](https://github.com/laiy790/sa110a/blob/master/mid/photo/2.png)




## 分散性聚類
### k-均值演算法
k-均值演算法表示以空間中k個點為中心進行聚類，對最靠近他們的物件歸類。

例如：資料集合為三維，聚類以兩點：X =(x1, x2, x3),Y =(y1, y2, y3)。中心點Z變為Z =(z1, z2, z3)，其中z1 = (x1 + y1)/2，z2 = (x2 + y2)/2，z3 = (x3 + y3)/2。

演算法流程:
演算法歸納為（J. MacQueen, 1967）：
```
+ 選擇聚類的個數k.
+ 任意產生k個聚類，然後確定聚類中心，或者直接生成k個中心。
+ 對每個點確定其聚類中心點。
+ 再計算其聚類新中心。
+ 重複以上步驟直到滿足收斂要求。（通常就是確定的中心點不再改變。）
```
![P](https://github.com/laiy790/sa110a/blob/master/mid/photo/3.png)
優點：

1.是解決聚類問題的一種經典演算法，簡單、快速

2.對處理大資料集，該演算法保持可伸縮性和高效率

3.當結果簇是密集的，它的效果較好

缺點

1.在簇的平均值可被定義的情況下才能使用，可能不適用於某些應用

2.必須事先給出k（要生成的簇的數目），而且對初值敏感，對於不同的初始值，可能會導致不同結果。

3.不適合於發現非凸形狀的簇或者大小差別很大的簇

4.對躁聲和孤立點資料敏感





## 參考資料
[Fitting-演算法筆記](http://web.ntnu.edu.tw/~algo/Fitting.html)

[維基百科](https://zh.wikipedia.org/wiki/%E8%81%9A%E7%B1%BB%E5%88%86%E6%9E%90#%E5%BA%94%E7%94%A8)

[ITRead](https://www.itread01.com/content/1547359213.html)