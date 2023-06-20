---

marp: true

---

# VRRP

---

## 目次

- VRRPとは
- マスタールータが停止した場合
- HSRPとVRRPの違い

---

## VRRPとは

**Virtual Router Redundancy Protocol**はルータを２台以上同じセグメントに併設し、それぞれ異なるIPアドレスを設定し、それを１つのつのVIPアドレスをでグループ化することで、デフォルトゲートウェイを冗長化するためのプロトコルです。

---

![vrrp](./img/basic_vrrp01_prob01.drawio.svg)

---

## マスタールータが停止した場合

バックアップルータが制御パケットを一定時間受信出来なくなるとバックアップルータがマスタールータに変化します。

<!--
    - VRRP Advertisementとは　VRID、優先度、仮想IPアドレス、VRRP Advertisementの送信間隔などが入っている
-->

---

## HSRPとVRRPとの違い

- 通信効率が良い
- セキュリティが高い

---

# ご清聴ありがとうござました