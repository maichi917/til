# 開発環境と本番環境のパスワードリセットメール送信方法の違い（開発:letter_opener_web／本番:Devise+ActionMailer+Resend）

- 開発環境 → `letter_opener_web`（送信せずブラウザでメール内容を確認できる）
- 本番環境 → DeviseのAction Mailerで、配信方法（delivery_method）に Resend gem を使う

Resend APIの使い方には2パターンある。

1. Resend gemをdelivery methodとして設定し、Action Mailerに任せる（今回のやり方）
2. 独自のMailerを用意し、HTTPクライアントでResend APIを直接呼ぶ

**私のアプリで使っているサービス**

| サービス | 役割 |
| --- | --- |
| お名前.com | ドメインを買う |
| Cloudflare | DNSを管理する |
| Resend | メールを送る |
| Render | Railsアプリを動かす |
| Rails | パスワードリセットメールを作る |

出典: https://qiita.com/ouga-engneering/items/1f378b56f0af7eb02efe
