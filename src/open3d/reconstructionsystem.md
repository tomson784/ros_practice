# 自分で取得したデータでreconstructionsystemの実行

## 実行環境

   Ubuntu20.04(noetic)

## 注意

   この章を実行するには、realsense、anacondaを実装し、opencv,pyreslsense2のインストールをしておく必要があります。

   [realsenseの実装方法](https://github.com/tomson784/ros_practice/blob/main/src/realsense_ros/index.md)

   [anacondaの実装方法](https://www.pc-koubou.jp/magazine/38846)

   opencvのインストール　`$ pip install opencv-python`

   pyrealsense2のインストール　`$ pip install pyrealsense2`
## 実行方法

1. 取得した画像を保存するファイルを作成

   `examples/python/reconstruction_system/config`の中に画像を保存する新しいファイルを作成する。

2. コードを書き直す

   ソースコード内の`examples/python/reconstruction_system/config`の中にあるrealsense.jsonを開く

   3行目のpath_datasetはサンプルコードと同じように`config/{画像を保存するファイル名}`と書き直す

   4行目のpath_intrinsicは`config/realsense/camera_intrinsic.json`と書き直す

```
   {
       "name": "Realsense bag file",
       "path_dataset": "config/{画像を保存するファイル名}/",
       "path_intrinsic": "config/realsense/camera_intrinsic.json",
       "max_depth": 3.0,
       "voxel_size": 0.05,
       "max_depth_diff": 0.07,
       "preference_loop_closure_odometry": 0.1,
       "preference_loop_closure_registration": 5.0,
       "tsdf_cubic_size": 3.0,
       "icp_method": "color",
       "global_registration": "ransac",
       "python_multi_threading": true
   }
```
   次に、`examples/python/reconstruction_system/sensor`の中にあるrealsense_recorder.pyを開く

   71行目のdefaultを`../config/{画像を保存するファイル名}`に書き換える

3. realsenseで画像の取得　

   3Dモデル化したい物体の周囲をぐるぐる回って取得する。

   `$ python realsense_recorder.py --record_imgs`

4. reconstructionsystemの実行

   `$ python run_system.py config_file --make --register --refine --integrate`

   ※config_fileの部分は`config/realsense.json`に書き換える