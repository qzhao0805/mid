#  使用Google Colaboratory跑深度學習
## 使用Colaboratory
點選進入Google雲端硬碟，如下介面 : 
![image](https://github.com/qzhao0805/mid/blob/main/eeb56691ae479699fdd58d060717be05.png)
然後點選新建–更多–Colaboratory,就會出現這個介面   
![image](https://github.com/qzhao0805/mid/blob/main/2.png)
紅框可以修改頁面名稱，點選藍框進行設定GPU運行  
![image](https://github.com/qzhao0805/mid/blob/main/3.png)
更改運行時的類型：
![image](https://github.com/qzhao0805/mid/blob/main/4.png)
設定為GPU:  
![image](https://github.com/qzhao0805/mid/blob/main/5.png)
驗證一下，輸入如下程式碼運行： 
import tensorflow as tf  
tf.test.gpu_device_name()  
出現如下結果則表示是GPU運作：  
可以使用以下指令查看cpu類型和CUDA 版本(方便安裝pytorch用)  














                            
