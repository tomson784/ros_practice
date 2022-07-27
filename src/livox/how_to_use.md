# Livoxlidarの使い方

LivaoLidarの説明書をよく読み、Livoxlidarとパソコン、外部電源の接続を行う。

## Livoxoxlidarの起動方法

正しく接続することができたら、次のコマンドでLivoxlidarを起動する。
1. livoxlidarの起動

    `$ roslaunch livox_ros_driver livox_lidar_rviz.launch`

このコマンドで起動することで、Livoxlidarデバイスに接続され、rvizにpointcloud2形式のデータが出力される。

これで動かない場合は，LANのIPアドレスを固定してないことが原因かもしれない．
[ここ](https://www.h.chiba-u.jp/lab/gmet/media/Livox_SLAM%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB.pdf)にLivoxでSLAMをするための一連の環境構築について書かれている．
Livoxに接続した有線LANの設定からIP4を手動にし，アドレス:`192.168.1.xx`，ネットマスク：`255.255.255.0`，ゲートウェイ：`192.168.1.1`，としてそれぞれ設定する．
アドレス:`192.168.1.xx`の`xx`は使っていないアドレスであれば問題なさそう．（私は`xx`を`2`，`50`で試したがどちらでもデータが取得できた）

※他にも起動ファイルがあるので、それぞれの用途に応じて使い分ける。他の起動ファイルと説明は[こちら](https://github.com/Livox-SDK/livox_ros_driver)

2. 電源を入れる

先程接続した外部電源に電源を入れて、livoxlidarに電源を入れる。
電圧と電流のつまみをそれぞれ回し、説明書に書いてある許容電圧になるように調整する。
※電圧が許容範囲になっても、電流が弱いとlidarに電源が入らないため注意する。

より詳しい説明が見たい方は[こちらのサイト](https://github.com/Livox-SDK/livox_ros_driver)をご覧ください。
