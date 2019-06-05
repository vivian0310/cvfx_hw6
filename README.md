# Homework6-Match-Moving-SLAM

## Videos by ourselves

- Video1(桌上的飲料水壺):

https://drive.google.com/file/d/1x5UAiRz7GUrPjKulZweYzfIL6vKyGf77/view?usp=sharing

下圖為影片分解後的frames部分截圖(540*960像素，共324張frames)
![](https://i.imgur.com/ezNDeSw.png)

- Video2(擺動手臂+轉圈): 

https://drive.google.com/file/d/1VbNDgHrEGhrC16JWgsu6ss6tH2MNi568/view?usp=sharing

下圖為影片分解後的frames部分截圖(540*960像素，共288張frames)
![](https://i.imgur.com/Q5JbN8w.png)

## Visual effects with ORB-SLAM2
我們主要以Monocular Example來執行。經過TUM1、TUM2、TUM3等不同檔案測試兩部影片，發現TUM3.yaml的執行結果較其他兩者良好，因此下面兩張成果皆是使用TUM3.yaml檔案運行。
- Video1 result:
![](https://i.imgur.com/9V0cX2A.png)

- Video2 result:
![](https://i.imgur.com/nsmiCbZ.png)

### Analysis:
我們猜測可能是由於兩個影片的拍攝光線、地點、物件、拍攝速度等皆有很大的差異，如影片一是在光線明亮的室內拍攝，加上相機移動速度緩慢，因此整體畫面清晰明顯，電腦容易掌控物件的特徵與形體，進而追蹤的效果非常良好；而影片二在光線稍微陰暗的教室旁拍攝，解析度較低且拍攝時移動速度過快，整個畫面就十分模糊，因此呈現的結果差，電腦較無法進行追蹤。

另外，雖然我們已將ROS安裝完成，但最後run的時候卻沒有出現畫面(如下圖所示)，且因為沒有顯示error，以致於無法得知問題出在哪，所以我們最後並沒有採用它來做影片。
![](https://i.imgur.com/fqBYvM4.jpg)

## Visual effects with post-production software
以下為影片1的後製，運用Adobe After effects所製作的。主要的後製內容為透過track純喫茶的表面，再套入皮卡丘發大財的影片。 

https://www.youtube.com/watch?v=-AAoWLrkbqI

以下為影片2的後製，運用Adobe After effects所製作的。主要的後製內容為透過track人的手，在手上加上火焰，當手心打開時即有火焰產生，握緊手心火焰就會消失。 

https://www.youtube.com/watch?v=JytstWUFkW4&feature=youtu.be

## Comparison
 - 以拍攝桌上飲料的影片1來看，ORB-SLAM2執行的效果優良，不論主體或背景物皆很完整的detect到數個點，相機轉視角時也精確的detect到原本的位置。而Adobe After Effect在後製影片時，將track平面的四個點設置完畢，經過軟體自行track後，即便視角旋轉，四個點也都落在正確的地方。

 - 以人物旋轉的影片2來看，由於拍攝的影片不夠清楚等等的理由，導致ORB-SLAM2並沒有辦法detect到影片中的各個點；而我們用來後製的Adobe After Effect，若是將tracker放在人物的手掌後讓軟體自行track，雖然最後的結果顯示其無法全程準確得落在手掌，但也有很多段並不需要特別修正就能track到正確的位置。

## Insert a 3D model to the video

使用Adobe After Effect在原來有火焰特效的影片再加上了3D model(玫瑰花)：

https://youtu.be/1ENvuGTh6_8

