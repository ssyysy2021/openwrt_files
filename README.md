## OpenWrt 非公式ビルドファームウェア、パッチ

## ◎ 注意

* 広範囲なテストは行っていませんので各人の責任でお使いください  
* 法律上、無線機能を有効にすることはおすすめしません
* OpenWrtで各機種が正式にサポートされると消えます

## ◎ 機種リスト


* 23.05.0-rc3
   - [Buffalo WSR-6000AX8](#-buffalo-wsr-6000ax8)
   - [ELECOM WRC-G01](#-elecom-wrc-g01)

&nbsp;&nbsp;(※) 公式のWSR-2533DHP**2** においてカーネルの6MB対応が行われそうなため、その派生形である WSR-3200AX4S, WSR-2533DHP3(WSR-A2533DHP3) の公開を取りやめました

<br>

## ◎ 各機種のパッチ

* WSR-6000AX8 は[こちら](https://github.com/openwrt/openwrt/commit/cec4e26bb2adad92cf028c8a77df38cd4e015486.diff)

* WRC-G01 は[この辺](./patch/)からどうぞ  

## ◎ Buffalo WSR-6000AX8

&nbsp;[ファームウェア、インストール手順など](./openwrt-23.05.0-rc3_bin/buffalo_wsr-6000ax8/)  

![](images/wsr-6000ax8.png)

<br>
<br>

## ◎ ELECOM WRC-G01

&nbsp;[ファームウェア、インストール手順など](./openwrt-23.05.0-rc3_bin/elecom_wrc-g01/)  

![](images/wrc-g01.png)

<br>
<br>