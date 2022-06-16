# Livoxlidarの使い方

LivaoLidarの説明書をよく読み、Livoxlidarとパソコン、外部電源の接続を行う。

## Livoxoxlidarの起動方法

正しく接続することができたら、次のコマンドでLivoxlidarを起動する。
1. livoxlidarの起動

    `$ roslaunch livox_ros_driver livox_lidar_rviz.launch`

このコマンドで起動することで、Livoxlidarデバイスに接続され、rvizにpointcloud2形式のデータが出力される。

※他にも起動ファイルがあるので、それぞれの用途に応じて使い分ける。他の起動ファイルと説明は[こちら](https://github.com/Livox-SDK/livox_ros_driver)

2. 電源を入れる

先程接続した外部電源に電源を入れて、livoxlidarに電源を入れる。
電圧と電流のつまみをそれぞれ回し、説明書に書いてある許容電圧になるように調整する。
※電圧が許容範囲になっても、電流が弱いとlidarに電源が入らないため注意する。

より詳しい説明が見たい方は[こちらのサイト](https://github.com/Livox-SDK/livox_ros_driver)をご覧ください。
