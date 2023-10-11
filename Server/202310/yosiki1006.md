---

marp: true
theme: gradient

---

# ルーティングを守る防ぐ技術 
## RPKI / ROA と ROV について
### 林 良輝

---

# RPKI　/ ROAとは
## Resource Public Key Infrastructure / Route Origin Authorization

---

## 簡単に説明すると

> IPアドレス と AS が一致しているかどうかを検証する仕組み

---

## 検証方法
> Updateメッセージ、アテステーション(attestation) と呼ばれる署名付きの情報を含めめることで
> ASパスや経路情報てして使われるIPアドレスの正しさを検証できるによるにしている
> downstreamからupstreamにかけて隣接するasからの署名を発行する

[jpnicブログより]

---

## ROAとは

---

## ROA( Route Origin Authorization)
> 認証署名を作る仕組みのこと
> ASとIPが一致しているか署名を逐一作っていく

---

# ROVとは

---

## ROV( Route Origin Validation)
> ROAの作成: ネットワークオペレータは、RPKIを使用してAS番号とIPアドレスプレフィックスの組み合わせに対するROAを作成します。ROAにはデジタル署名が含まれます。

> ROAの配布: ROAはRPKIインフラストラクチャを介して配布され、インターネットのルートコントローラやRPKIリポジトリに保存されます。

> BGPルーターの設定: BGPルーターは、RPKIキャッシュを使用して受信したBGPアップデートに含まれるルートの正当性を確認します。BGPルーターは、ROAからのデジタル署名とAS番号とIPアドレスプレフィックスの組み合わせを検証します。

> 正当でないルートの拒否: ROVとRPKI/ROAが連携している場合、BGPルーターは正当でないルートオリジンからのルートを拒否し、信頼性のあるBGPルート情報のみを受け入れます。

---

# RPKI-RTRとは
## RPKI-to-Router Protocol `RPKIの基盤上で提供されるROA情報(の一部)をルータへ伝搬するためのプロトコルで、RFC6810にて定義されている`
> BGPルーターはRPKI-RTRを介して受信したROAデータを使用して、受信したBGPルートの正当性を確認します。BGPルーターは、ルートオリジン情報がROAに一致しない場合、そのルートを拒否する。

---

# 実運用はまだまだ進んでないらしい

---