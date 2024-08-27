# Code 說明

🔸引用 CNN Model 是修改自 [https://github.com/dragen1860/MAML-Pytorch](https://github.com/dragen1860/MAML-Pytorch)


    1. 修改dataset.py  model的input改为 7个Vehicle parameter, output为0或1(代表 normal/abnormal) 
    
    2. cite meta.py/learner.py 引用模型的訓練方式和模型架構
    

## 跑 FL

1. 啟動 CAV Device (連接到IoTtalk中)
    1. `FL/CAV Device/client.py` 自動生成 CAV 裝置並連接到 IoTtalk GUI 中
    2. 需要幾個 CAV 裝置就啟動幾個 Client.py(Client1, Client2...)
        
        ```bash
        python3 Client1.py
        ```
        
2. 啟動 FMLtalk Device
   1. 先啟動 `ModelManager.py` 啟動 GUI，並上傳模型檔案
      
   3. `FL/FMLtalk Device/server.py` 進行 FL training
    
       ```bash
       python3 server.py
       ```
        

## 跑 FML

1. 啟動 CAV 裝置（連接到 IoTtalk 中）
    1. `FML/CAV Device/client.py` 自動生成 CAV 裝置並連接到 IoTtalk GUI 中
    2. 需要幾個 CAV 裝置就啟動幾個 Client.py(Client1, Client2...)
        
        ```bash
        python3 Client1.py
        ```
        
2. 啟動 FMLtalk Device
   1. 先啟動 `ModelManager.py` 啟動GUI，並上傳模型檔案
   
   3. `FML/FMLtalk Device/server.py` 进行FML training
    
       ```bash
       python3 server.py
       ```
  
3. 啟動 TAV Device

   
   1. 啟動`FML/TAV Device/vehicle.py`，生成 TAV 裝置，並連接到 IoTtalk 
      

      ```bash
       python3 vehicle.py
      ```

## Carla

1. carla啟動:[https://carla.readthedocs.io/en/latest/start_quickstart/#running-carla](https://carla.readthedocs.io/en/latest/start_quickstart/#running-carla)
      
      ```bash
       ./CarlaUE4.sh -quality-level=Low
      ```
