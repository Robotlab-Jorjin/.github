# Jorjin

## Repo介紹

- [MainApp](https://github.com/Robotlab-Jorjin/MainApp): 最終App的Build的Source Code
- [VirtualRoomServer](https://github.com/Robotlab-Jorjin/VirtualRoomServer): 通訊系統背後的Server
- [Networking](https://github.com/Robotlab-Jorjin/Networking): 運作Network的範例

## Scenario

Download the files from [here](https://github.com/Robotlab-Jorjin/VirtualRoomServer)
1. 啟動VirtualRoomServer/VirtualRoomServer.exe  
2. 啟動VirtualRoomServer/Admin/run.bat  
3. 啟動MainApp

第一個加入房間的玩家為Host，後續為一般玩家Player，Host需要維護其他資訊以同步其他使用者。

## Building Enviroment
### Android

- UnityEditor: 2021.3.35 (or above)

2022以上的版本Jorjin API會有釋放記憶體的問題，只能在2021的版本跑

- Minimum API: 28
- Target API: 28
  
Jorjin Glass最高只支援到API level 28，允許最低為27

- Scripting Backend: Mono
- Target Architectures: Armv7
  
SLAM只支援Armv7下的設備，此外MediapipeUnityPlugin的Prebuild Package支援Armv7最高到v0.14.1，若要升級版本需要自己去Github抓下來自己Build

## 可能遇到問題
- Multiple Precompile DLL Error: 把刪掉多的Google Protobuf，把JMSDK的Pakage下的Protobuf取代Mediapipe protobuf的，[Protobuf載點]()
- 無法連線到VirtualRoomServer: 有很多原因會導致連線失誤，若是第一次把Repo拉下來打開專案時失誤，可能PlayerVRC被重製了，將場景中PlayerVRC刪掉重拉Prefab
