# ROS PlotJugglerの使い方

PlotJugglerとは<br>
+rosbag中のtopicの値を横軸時間, 縦軸topic値のグラフとして可視化することができる。<br>
+複数トピックを重ねてプロットすることができる。<br>
+topicをRvizに飛ばし，視覚化ができる。<br>
+ドラッグ＆ドロップで直感的に操作が可能。<br>

必要なこと  
1. PlotJugglerをインストール

## インストールと実行方法

以下のコマンドでplotjugglerをインストールします。ROS Pluginも同時にインストールされます。
```
$ sudo apt install ros-${ROS_DISTRO}-plotjuggler-ros
```
以下のコマンドで実行できます。
```
$ rosrun plotjuggler plotjuggler
```
<br>

## 基本的な使い方
+rosbagデータの選択<br>
左側のパネルから，File>Load Dataと選択し, 解析したいrosbagデータを選択するとrosbag中のTopic一覧が表示されるので, 可視化したいTopicを選択する。<br>
+Topicの可視化<br>
可視化したいTopicをプロットエリアにドラッグ＆ドロップする。<br>
複数のTopicを選択したい場合は，Ctrlキーを押したまま選択する。<br>
+Rvizでの可視化<br>
左側のパネルから，Publishers>ROS Topic Re-Publisherにチェックをいれる。<br>
Rvizで可視化したいTopicを選ぶ。<br>
<br>

## 詳しい使い方
+「XYプロット」で2つの時系列を組み合わせる<br>
Ctrlキーを押したまま2つの時系列を選択する。<br>
右マウスを使用してプロットエリアにドラッグ＆ドロップする。<br>
+レイアウトの保存<br>
レイアウトファイルを保存することで，現在の状態の保存ができる。<br>
左側のパネルから，File>Layoutからxmlファイルを保存する。<br>
このとき，使用したrosbagデータも一緒に保存できる。
<br>

## 参考
[1] [PlotJuggler:learn the basics](https://slides.com/davidefaconti/introduction-to-plotjuggler) <br>
[2] [PlotJuggler:data sources](https://slides.com/davidefaconti/plotjuggler-data) <br>
[3] [PlotJuggler:custom plots,filters and transformations](https://slides.com/davidefaconti/plotjuggler-transforms)<br>
[4] [PlotJugglerでrosbagのトピックを可視化する](https://qiita.com/Decwest/items/23c24f80c39b71619b32)

## 編集者
村山<br>
使い方を勉強中なので，できることが増え次第追加していきます。