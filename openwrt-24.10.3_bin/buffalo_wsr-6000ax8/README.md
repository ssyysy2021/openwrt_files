## ターゲット(ルーター)
Buffalo WSR-6000AX8/AX8P

## インストール方法
1. TFTPサーバーを立てる (192.168.11.2/24)
2. TFTPサーバーのトップディレクトリに `??-initramfs-kernel.bin` を `linux.ubi-recovery` として置く
3. AOSSボタンを押しながらルーターの電源を接続し、TFTPダウンロードが開始されるまで押したままにする
4. TFTPダウンロードが終了するとカーネルが起動するので 192.168.1.x/24 のマシンからSCPで `??-squashfs-sysupgrade.bin` をターゲット(root@192.168.1.1:/tmp)にコピーする
5. SSHで root@192.168.1.1 にログインする
6. `sysupgrade -n /tmp/??-squashfs-sysupgrade.bin` を実行する (自動で再起動する)

## メーカーファームウェアへの復元方法
* メーカーファームウェアを buffalo-enc で復号し `sysupgrade -F -n` で書き込む

## パッチ
* ([これ](https://github.com/openwrt/openwrt/commit/49b9b93b19fa4d4d8f27f4862b128f52cf4a5d28)と同じなので省略)

## 注意
* 本ファームウェアはご自身の責任でご使用ください

## 以前野良ビルドファームウェアを使用していた方向け
* MACアドレスの初期化方法を何回か変えたのでconfigを初期化した方が良いかもしれません  
   - `option macaddr` は不要 
