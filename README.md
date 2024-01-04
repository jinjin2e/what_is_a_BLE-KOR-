# BLE
BLE, Bluetooth Low Energy 블루투스 4.0을 사용하는 저전력 디바이스를 말한다.  
저전력 디바이스인 만큼 고속통신에 단점이 있음. 대신 Coin Cell 하나만으로 1년정도 동작 할 정도로 배터리 소모량이 적다.   
***


## 동작 방식 구분 
> ### Advertise Mode 
> 전원인가 후 주변의 모든 장치에 일방적으로 신호를 보내는 장치로 통신과는 무관한 비콘같은 장치. 2.4GHz 주파수 대역에서 Advertising Channel (37, 38, 39 채널)에서만 동작  
> 보내야 하는 데이터의 크기가 작고, 다수의 디바이스에 전송을 해야 하는 경우에 Advertising Mode를 활용  
>
>
> ### Connection Mode
> Advertising 패킷 전달 후 장치간의 연결의 과정이 필요한 동작 방식. 연결이 되면 Advertiser와 Observer는 서로 1:1 동작으로 Frequency Hopping 방식으로 동작한다.   
> 양방향으로 데이터를 주고받아야 하거나, 많은 양의 데이터를 주고받는 경우  
> ```
> Advertiser : Signal을 주기적으로 보내는 디바이스
> Observer : Signal을 주기적으로 Scan 하는 디바이스 (Signal에 귀 기울이고 있는 디바이스)
> ```   
> ![image](https://github.com/jinjin2e/BLE/assets/93366905/3c8892d4-79ac-4272-980d-dcaa302761a6)
***
## 스택 
![images_zhemdrawer_post_d2802fee-27b3-4abb-9003-47365ed4052b_BLE_Layer_model](https://github.com/jinjin2e/BLE/assets/93366905/f174f189-e532-4321-b6a4-758e93ca6afd)
- Physical: 2.4 GHz ISM 대역에서 1 Mbps의 속도로 패킷 송수신 역할 (실제 Bluetooth Analog Signal과 통신할 수 있는 회로가 구성되어 있음)

- LL (Link Layer): 5가지의 RF 상태 제어 (standby, advertising, scanning, initiating, connected) 및 디바이스의 Role 정의

- HCI (Host Controller Interface): Host 영역과 Controller 영역의 Interface 역할

 

- L2CAP (Logical Link Control and Adaptation Protocol): 데이터 encapulation service 제공

- SM (Security Manager): paring and key distributuiion 방법 정의 및 인증과 보안에 사용

- ATT (Attribute Protocol): 다른 기기로 'attribute'라는 데이터 노출 및 데이터 교환을 위한 클라이언트, 서버 프로토콜 정의

- GAP (Generic Access Protocl): 장치 간의 paring과 bonding 사용을 통해 장치 간 인터페이스 역할

- GATT (Generic Attribute Profile): ATT를 이용하는 sub-procedure를 정의하는 프레임워크, ATT 영역에서 읽어 들인 서비스의 기능 수행

 
