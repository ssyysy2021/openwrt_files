## ターゲット(ルーター)
   * Buffalo WSR-2533DHP3
   * Buffalo WSR-A2533DHP3(Amazon専売モデル)

## インストール方法
### メーカーファームウェアアップデート画面がらアップデートする場合に使用するファイル
   * WSR-2533DHP3 : `*-squashfs-factory.bin`
   * WSR-A2533DHP3: `*-squashfs-factory-a2533dhp3.bin`

### TFTPブートしてアップデートする手順　
※ WSR-2533DHP3、WSR-A2533DHP3 とも同じファームウェアを使います（WSR-A2533DHP3に入れてもモデル名はWSR-2533DHP3になります）  

1. TFTPサーバーを立てる (192.168.11.2/24)
2. TFTPサーバーのトップディレクトリに `*-initramfs-kernel.bin` を `linux.trx-recovery` として置く
3. AOSSボタンを押しながらルーターの電源を接続し、TFTPダウンロードが開始されるまで押したままにする
4. TFTPダウンロードが終了するとカーネルが起動するので 192.168.1.x/24 のマシンから `http://192.168.1.1/` にログインする
5. LuCI(Web UI)の Flash new firmware image 画面で `*-squashfs-sysupgrade.bin` を指定しアップロードを実行する (自動で再起動する)

## パッチ
* [パッチ](../patch/)

## 注意
* 本ファームウェアはご自身の責任でご使用ください

## 以前野良ビルドファームウェアを使用していた方向け
* MACアドレスの初期化方法を何回か変えたのでconfigを初期化した方が良いかもしれません  
   - configを初期化したくない人向け: `/etc/config/network` の `option macaddr` は不要
