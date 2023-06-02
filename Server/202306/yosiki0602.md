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

# nsswitch.conf(Name Service Switch)

---

# 順序
`リゾルバ(resolver)がnsswitch.confで名前解決の順序を確認`
                    `↓`
`指定された順番通りにファイル/サーバの内容をチェックする`

---

## /etc/nsswitch.conf

```text
# /etc/nsswitch.conf
#
# Example configuration of GNU Name Service Switch functionality.
# If you have the `glibc-doc-reference' and `info' packages installed, try:
# `info libc "Name Service Switch"' for information about this file.

passwd:         files systemd
group:          files systemd
shadow:         files
gshadow:        files

hosts:          files mdns4_minimal [NOTFOUND=return] dns
networks:       files

protocols:      db files
services:       db files
ethers:         db files
rpc:            db files

netgroup:       nis
```

---

## /etc/hosts
```text
127.0.0.1	localhost
255.255.255.255	broadcasthost
::1             localhost
```
### `http://[::1]/`