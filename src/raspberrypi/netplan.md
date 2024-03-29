# ラズパイでのネットワークの設定方法
本稿では，ラズベリーパイでnetplanを用いたネットワークの設定方法を紹介する。<br>
基本的には以下のURLを参考にしている．<br>
[ラズパイ3にUbuntu20.04LTSをインストール](https://takaken.tokyo/dev/raspberrypi/raspi_ubuntu_setup2004/)
<br>
[ゆっくりラズパイ活用講座](http://7th-chord.jp/sara_tsukiyono/index.php?cl=rp&rp=191028)
<br>


## 実施環境
- ラズパイ3 
- 16GB MicroSDカード

## netplanの設定
無線LAN接続に必要となるパッケージをインストール<br>
`sudo apt-get install network-manager`<br>
`sudo apt-get install wireless-tools`<br>

ネットワーク設定用サービスが有効になっているか確認<br>
`systemctl is-enabled systemd-networkd`<br>
enabled<br>
`systemctl is-enabled network-manager`<br>
enabled<br>

systemd-networkd はネットワーク設定を管理するシステムデーモン。<br>
NetworkManager はネットワークの検知と設定を自動で行いネットワークに接続する機能を有し、無線・有線両方のネットワークに使うことができる。<br>
NetworkManagerが起動していない場合は起動する。<br>
`systemctl start NetworkManager`<br>
`systemctl enable NetworkManager`<br>

次に、無線LANのアクセスポイントをスキャンして、接続するブロードバンドルーターのSSIDを確認する。<br>
`sudo iwlist wlan0 scan | grep ESSID`<br>

システムが作成しているファイル(50-cloud-init.yaml)を直接編集するのはリスクがあるので、ファイルを複製してファイル名の頭数字を50よりも大きい数字にする。(99-とか)<br>
そうすることでシステムが50〜を読み込んだあとに99〜を読み込んでくれる。<br>
```
cd /etc/netplan/

sudo cp 50-cloud-init.yaml 99-cloud-init.yaml

sudo vim 99-cloud-init.yaml
```
cloud-initファイルの中身
```
network:
    ethernets:
        eth0:
            dhcp4: true
            optional: true
    version: 2
```

ここにWi-Fi用の項目、固定IPアドレス等を追加
```
network:
    renderer: NetworkManager
    ethernets:
        eth0:
            dhcp4: true
            optional: true
    version: 2
    wifis:
        wlan0:
            dhcp4: no
            dhcp6: no
            access-points:
                "Wi-FiのSSID":
                    password: "xxxxxxxxxxxxx"
            addresses: [固定IPアドレス]
            gateway4: xxx.xxx.xx.x
            nameservers:
                    addresses: [xxx.xxx.xx.xx,xxx.xxx.xx.x]
```

設定を反映させる。
```
sudo netplan apply

sudo ip link set wlan0 up
```

Wi-Fiのインターフェース名を確認<br>
`iwconfig`<br>

IPアドレスを確認<br>
`ip addr`<br>


最後にアップデートコマンドを実行してネットワークにつながることを確認

```
sudo apt update

sudo apt upgrade
```

## 編集者
村山
