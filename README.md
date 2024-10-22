#  使用Google Colaboratory跑深度學習
南華大學 跨領域-人工智慧期中報告  
11024201 趙青益  
11024114 翁莊堡  
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

驗證一下，輸入如下程式碼運行:  
```
import tensorflow as tf  
tf.test.gpu_device_name()  
```
出現如下結果則表示是GPU運作：  
![image](https://github.com/qzhao0805/mid/blob/main/6.png)  

可以使用以下指令查看cpu類型和CUDA 版本(方便安裝pytorch用)  
```
!/opt/bin/nvidia-smi
```
![image](https://github.com/qzhao0805/mid/blob/main/7.png)  

## 安裝Miniconda3  
這裡提前說一下在Colaboratory的問題：
  
就是在這個類似命令列的頁面端無法進行conda虛擬環境的創建，只能使用base，而且需要特殊的方式來使用conda。
先使用命令列下載Miniconda3的sh安裝包：  
```
!wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
```
安裝權限配置：  
```
!chmod +x Miniconda3-latest-Linux-x86_64.sh
```
安裝到指定位置，這裡建議安裝在/root/  
```
!bash ./Miniconda3-latest-Linux-x86_64.sh -b -f /root/
```
激活conda:  
```
!source /root/miniconda3/bin/activate
```
使用命令將conda配置成預設的命令列使用  
```
!conda init
```
## 安装PyTorch  
這裡試過進行env的創建，但是創建成功之後無法進行命令列的切換，因此這裡就直接在base上進行了。  
安裝pytorch，這裡去pytorch官網選擇對應的版本進行安裝：  
```
![image](https://github.com/qzhao0805/mid/blob/main/8.png)  
!conda install pytorch torchvision cudatoolkit=10.1 -c pytorch
```
使用指令查看conda env： 
```
!conda info --env
```

![image](https://github.com/qzhao0805/mid/blob/main/9.png)  
## 驗證pytorch是否能夠使用  
首先直接編寫程式碼進行驗證能否直接使用自己安裝的conda python:  
```
import torch  
print(torch.version)
```

## 安裝MMDetection  
**安裝mmcv**  
```
!git clone https://github.com/open-mmlab/mmcv.git  
!cd mmcv  
!pip install -U openmim
!mim install mmcv
```

**安装cpython等需求包**  
```
!https://gitee.com/zyp521/upload_image/raw/master/cGUR6D.png
```

**安裝mmdetection**  
官方文件的安裝方法：
```
!git clone https://github.com/open-mmlab/mmdetection.git  
!cd mmdetection  
!pip install -r requirements/build.txt  
!pip install "git+https://github.com/cocodataset/cocoapi.git#subdirectory=PythonAPI"  
!pip install -v -e . # or "python setup.py develop"
```
我們使用:
```
!cp /content/mmcv/mmcv/version.py /content/mmcv
!python /content/mmcv/setup.py install
```
  
到此，我們就完成了mmdetection及其依賴函式庫的安裝。  
有一個比較大的缺陷需要聲明一下，就是如果你超過12小時不登入Colaboratory的話，google會自動將你的伺服器重置分配給別人，你的資料和程式碼都被自動清楚了。  




















































                            
