## 対応ルーター
Buffalo WSR-3200AX4S  
Buffalo WSR-2533DHP2  
Buffalo WSR-A2533DHP2  

## インストール方法

### TFTPサーバーから

1. TFTPサーバーを立てる (192.168.11.2/24)
2. TFTPサーバーのトップディレクトリに `??-initramfs-kernel.bin` を `linux.trx-recovery` として置く
3. AOSSボタンを押しながらルーターの電源を接続し、TFTPダウンロードが開始されるまで押したままにする
4. TFTPダウンロードが終了するとカーネルが起動するので 192.168.1.x/24 のマシンからSCPで `??-squashfs-sysupgrade.bin` をターゲット(root@192.168.1.1:/tmp)にコピーする
5. SSHで root@192.168.1.1 にログインする
6. `sysupgrade -n /tmp/??-squashfs-sysupgrade.bin` を実行する (自動で再起動する)

### ファームウェアアップグレード画面から

&nbsp;&nbsp;(省略)

## お約束
1. 無線機能の有効化は法律上オススメしません
2. 何らかの損害が発生しても責任は負いません
