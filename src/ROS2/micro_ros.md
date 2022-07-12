# micro_rosでarduinoを使う

ros2ではmicro_rosというパッケージを使ってマイコン側でもROS2ノードを立ち上げることができます．

使い方についてはこちらの記事（[[ROS2 foxy] ESP32を使ってmicro-ROS for Arduinoで遊ぼう](https://qiita.com/ousagi_sama/items/b4eb3d9c6b337cbe1b05)）を確認してみてください

## Arduino Dueで動かす．

[ESPDuino-32](https://www.amazon.co.jp/waves-ESP32-ESPDuino-32-ESP-WROOM-32-%E6%8A%80%E9%81%A9%E5%8F%96%E5%BE%97%E5%93%81/dp/B074PNFJGF)であれば先ほどの手順で難なく動かすことができますが，Arduino-Dueで動かすには他にも設定を行う必要があります．

[micro_ros_arduino](https://github.com/micro-ROS/micro_ros_arduino)のPatch SAMDに記載されている手順を踏む必要があります．
`/home/user/.arduino15/packages/arduino/hardware/sam/1.6.12/`のフォルダに`platform.txt`というファイルがあるのでそのファイルを削除，またはファイル名を変更する．
`curl https://raw.githubusercontent.com/micro-ROS/micro_ros_arduino/main/extras/patching_boards/platform_arduinocore_sam.txt > platform.txt`をすることで，ArduinoDueでも書き込めるようになっている．

## 参考

- [[ROS2 foxy] ESP32を使ってmicro-ROS for Arduinoで遊ぼう](https://qiita.com/ousagi_sama/items/b4eb3d9c6b337cbe1b05)
- [Micro ROS with Arduino (ROS2+Arduino)](https://soulful-magenta-dog-467.medium.com/micro-ros-with-arduino-ros2-arduino-7e754ba5210)
- [microROS-ArduinoのM5Atom用設定（ESP32・ROS2）](https://ar-ray.hatenablog.com/entry/2022/04/07/121653)
