## ターゲット(ルーター)
Buffalo WSR-6000AX8

## インストール方法
1. TFTPサーバーを立てる (192.168.11.2/24)
2. TFTPサーバーのトップディレクトリに `??-initramfs-kernel.bin` を `linux.ubi-recovery` として置く
3. AOSSボタンを押しながらルーターの電源を接続し、TFTPダウンロードが開始されるまで押したままにする
4. TFTPダウンロードが終了するとカーネルが起動するので 192.168.1.x/24 のマシンからSCPで `??-squashfs-sysupgrade.bin` をターゲット(root@192.168.1.1:/tmp)にコピーする
5. SSHで root@192.168.1.1 にログインする
6. `sysupgrade -n /tmp/??-squashfs-sysupgrade.bin` を実行する (自動で再起動する)

## メーカーファームウェアへの復元方法
* メーカーファームウェアを buffalo-enc で復号し `sysupgrade -F -n` で書き込む

## 注意
1. 無線機能の使用はおすすめしない
2. 何らかの損害が発生しても自己責任

## 以前ここの 23.05.0-rc? ファームウェアを使用していた人向け
* MACアドレスの初期化方法を変えたので、sysupgradeでconfigを残したままアップグレードした場合には、`/etc/config/network` に次の設定を追加する（または、LuCI上で lan1, lan2, lan3, eth1 のMACアドレスに筐体のMACアドレスを入力でも可）

```
config device
        option name 'lan1'
        option macaddr '68:e1:dc:11:22:33'  # 筐体のMACアドレス

config device
        option name 'lan2'
        option macaddr '68:e1:dc:11:22:33'

config device
        option name 'lan3'
        option macaddr '68:e1:dc:11:22:33'

    ::
    ::

config device
        option name 'eth1'
        option macaddr '68:e1:dc:11:22:33'
```