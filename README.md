## ロボットシステム学2021課題
## DC モータ用フルブリッジドライバ　TA7291Pの制御
Raspberry Pi 3 Model Bでモータードライバ（TA7291P）を制御し、DCモータの正転・逆転・ストップをコントロールした. 
### 動作環境 
| OS | Ubuntu20.04 server |
|:-:|:-:|
| ハードウェア | Raspberry Pi 3 Model B |
| モータ | ＤＣモータ FA-130RA-2270L |

### 配線図
下の図のように配線しました.   
![robosys](https://user-images.githubusercontent.com/54020567/144742794-69617586-27d9-42d7-b9f7-e81eaae5dc4a.png)

### インストール方法
```
git clone https://github.com/RikuUchida/robosys_device_driver.git
cd robosys_device_driver
```
### ビルド方法
```
make
sudo insmod mymotor.ko
sudo chmod 666 /dev/mymotor0
```
### 実行方法
正転
```
echo w > /dev/mymotor0
```
逆転
```
echo s > /dev/mymotor0
```
ストップ
```
echo 0 > /dev/mymotor0
```
### ドライバのアンインストール
```
sudo rmmod mymotor
```
### 実行結果
以下のリンクからyoutubeの動画が見れます.   
https://www.youtube.com/watch?v=yDzHNiZYxjU
### 参考
以下のサイトを参照しました．  
TA7291P  
https://www.marutsu.co.jp/contents/shop/marutsu/datasheet/ta7291.pdf  
Raspberry Pi 3 Model B  
https://datasheets.raspberrypi.com/rpi3/raspberry-pi-3-b-reduced-schematics.pdf  
ＤＣモータ FA-130RA-2270L  
https://akizukidenshi.com/catalog/g/gP-09169/
