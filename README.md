# TIL (Today I Learned)

日々学んだことを短くメモしていくリポジトリ。長く書こうとすると続かないので、短く・素早く残すことを優先する。

## 書くタイミング

- Qiitaのコメントなどで新しいメソッド・テクニックを教わった時
- コードレビュー中に気になる実装（粗）を見つけた時
- 過去に書いたコードを読み返して理解し直した時
- AtCoderで新しい解法・テクニックを使った時

## エントリの書き方

1本あたり3〜10行程度。

- 学んだこと（1行）
- 最小限のコード例
- （あれば）出典リンク

新しいエントリを書いたら、下の一覧にも追記する。

## 一覧

<details>
<summary>rails</summary>

- [rails/price_before_type_cast.md](rails/price_before_type_cast.md) — `カラム名_before_type_cast` で型変換前の値が取れる
- [rails/boolean_column_query_method.md](rails/boolean_column_query_method.md) — boolean型のカラムには自動で `カラム名?` メソッドが定義される
- [rails/image_gem_selection.md](rails/image_gem_selection.md) — 画像加工・保存まわりのgem選定理由（vips / Active Storage）
- [rails/redirect_back_fallback_location.md](rails/redirect_back_fallback_location.md) — `redirect_back`は元の画面に戻る、`fallback_location:`はRefererがない時の保険
- [rails/password_reset_email_setup.md](rails/password_reset_email_setup.md) — パスワードリセットメールは開発:letter_opener_web／本番:Devise+ActionMailer+Resendで送る

</details>

<details>
<summary>render</summary>

- [render/cron_job_setup.md](render/cron_job_setup.md) — RenderでRailsの定期タスク（Cron Job）を設定する

</details>

<details>
<summary>paiza</summary>

- [paiza/gets_to_i_and_if_elsif_else.md](paiza/gets_to_i_and_if_elsif_else.md) — gets.to_iで標準入力を数値として受け取り、if/elsif/==で条件分岐する基本

</details>
