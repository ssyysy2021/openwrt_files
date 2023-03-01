# OpenWrt 独自ビルドファームウェア、パッチ

## 注意

* 広範囲なテストは行っていないので各自の責任でお使いください  
* 電波法上、無線アクセスポイント機能を有効にすることはおすすめしません
* OpenWrtで各機種が正式にサポートされると消えます...

## Buffalo WSR-3200AX4S

### パッチ  
&nbsp;&nbsp; https://github.com/ssyysy2021/openwrt_files/blob/main/patches/wsr-3200ax4s_snapshot.patch  
  
&nbsp;&nbsp;&nbsp; ※ このパッチは以下をもとに作成しました。ありがとうございます。  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; https://github.com/musashino-build/openwrt/tree/devadd/wsr-3200ax4s

### ビルド済みファームウェア
&nbsp;&nbsp;&nbsp; `https://github.com/ssyysy2021/openwrt_files/tree/main/bin/(version)`  
&nbsp;&nbsp;&nbsp;からインストール方法により選択

### インストール方法
   * その1
      * 純正ファームウェアのアップデート画面から _openwrt-mediatek-mt7622-buffalo_wsr-3200ax4s-squashfs-**factory**.bin_ を投入
      
   - その2
      * AOSSボタンでTFTPブートしその後sysupgradeでインストール
         - PC(など)でTFTPサーバー(192.168.11.2/24)を立ち上げ _openwrt-mediatek-mt7622-buffalo_wsr-3200ax4s-**initramfs-kernel**.bin_ を `/linux.trx-recovery` と
して置く
         - AOSSボタンを押しながら WSR-3200AX4S の電源を入れる(TFTPダウンロード後、最小構成のOpenWrtが起動)
         - PCを `192.168.1.x/24`(192.168.1.1以外) に変更してから、scpなどを使用して `root@192.168.1.1:/tmp` に _openwrt-mediatek-mt7622-buffalo_wsr-3200ax4s-squashfs-**sysupgrade**.bin_ を転送
         - ssh で `root@192.168.1.1` に接続
         - sysupgrade で `/tmp/openwrt-mediatek-mt7622-buffalo_wsr-3200ax4s-squashfs-sysupgrade.bin` を投入
