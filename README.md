## ロボットシステム学2021課題
## DC モータ用フルブリッジドライバ　TA7291Pの制御
Raspberry Pi 3 Model Bでモータードライバ（TA7291P）を制御し、DCモータの正転・逆転・ストップ・ブレーキをコントロールした. 
### 動作環境 
| OS | Ubuntu20.04 server |
|:-|:-|
| ハードウェア |Raspberry Pi Model3B+|
### インストール
```
git clone https://github.com/RikuUchida/robosys_device_driver.git
cd robosys_device_driver
```
### ビルド
```
make
sudo insmod myled.ko
sudo chmod 666 /dev/myled0
```
### 実行方法
正転
```
echo w > /dev/myled0
```
逆転
```
echo s > /dev/myled0
```
ストップ
```
echo 0 > /dev/myled0
```
### ドライバのアンインストール
```
sudo rhmod myled
```
