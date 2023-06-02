---

marp: true
theme: gradient 

---

# Linux 名前解決の仕組み
## 林 良輝

---

# resolverとは
## `resolv.conf`


---

# nsswitch.conf(Name Service Switch)とHostsファイル

---

# 順序
リゾルバ(resolver)がnsswitch.confで名前解決の順序を確認
　　　　　　　　　　　　　↓
指定された順番通りにファイル/サーバの内容をチェックする


---

## /etc/hosts
```
127.0.0.1	localhost
255.255.255.255	broadcasthost
::1             localhost
```
### `http://[::1]/`