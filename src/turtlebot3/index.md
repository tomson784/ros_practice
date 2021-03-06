# gazeboでの強化学習

   gazebo上でturtlebotを使って強化学習をすることができる

   [参考にしたコード](https://github.com/ROBOTIS-GIT/turtlebot3_machine_learning)

## 実行時の環境

   Ubuntu20.04

## 実行方法

1. githubからコードをクローンする

   `$ git clone https://github.com/ROBOTIS-GIT/turtlebot3_machine_learning`

2. コードの修正を行う

 ・nodes/turtlebot3_dqn_stage_1 ~ 4

   31~33行目（tensorflowを追加する）

   `from tensorflow.keras.models import Sequential, load_model`

   `from tensorflow.keras.optimizers import RMSprop`

   `from tensorflow.keras.layers import Dense, Dropout, Activation`

 ・nodes/turtlebot3_dqn_stage_1

   151行目

   `state_size = 362`

 ・nodes/turtlebot3_dqn_stage_2

   151行目

   `state_size = 364`

 ・nodes/turtlebot3_dqn_stage_3

    後に記述

 ・nodes/turtlebot3_dqn_stage_4

    151行目

   `state_size = 364`

 ・src/enviroment_stage_1 ~ 4

   29行目（src.turtlebot3_dqnを追加）

   `from src.turtlebot3_dqn.respawnGoal import Respawn`

3. 実行

 gazebo上に実行環境を表示

   `$ export TURTLEBOT3_MODEL=burger`

   `$ roslaunch turtlebot_gazebo turtlebot3_stage_1.lauch`

 新しいウィンドウのターミナルを開いて

   `$ roslaunch turtlebot3_dqn turtlebot3_dqn_stage_1.launch`
