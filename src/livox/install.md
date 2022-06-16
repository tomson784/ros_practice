# Livoxlidarパッケージのインストール方法

## 依存関係のインストール

livoxlidarのパッケージをインストールする前にROSとLivox-SDKをインストール

## ROSのインストール

ROSのインストールについては[こちら](/src/intro/environment.md)を確認してください。

## Livox-SDKのインストール

1. githubからパッケージをクローンする

    `$ git clone https://github.com/Livox-SDK/Livox-SDK`

2. 下記のコマンドを実行

    `$ cd Livox-SDK`

    `$ cd build && cmake ..`

    `$ make`

    `$ sudo make install`

ROSとLivox-SDKがインストールできたら、Livoxlidarのパッケージをインストール

## Livoxlidarのパッケージのインストール

1. githubからlivox_ros_driverをクローンする

    `$ git clone https://github.com/Livox-SDK/livox_ros_driver.git ws_livox/src`

2. 次のコマンドで、livox_ros_driverをビルドする。

    `$ cd ws_lidar`
    
    `$ catkin_make`

3. 次のコマンドで、現在のROSパッケージ環境を更新する。

    `source ./devel/seetup.bash`

すべて終わったら[実行](./how_to_use.md)する

より詳しい説明が見たい方は[こちらのサイト](https://github.com/Livox-SDK/livox_ros_driver)をご覧ください。