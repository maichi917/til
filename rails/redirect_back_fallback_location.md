# `redirect_back` と `fallback_location:`

`redirect_back` は、直前にいた画面（HTTPの`Referer`ヘッダー）にそのまま戻るRailsの仕組み。
（`Referer`ヘッダーとは、ブラウザがリクエスト時に一緒に送る「どのページから来たか」を示す情報。URL直接入力やブックマークからのアクセスなど、送られてこないケースもある。）

`redirect_to items_path` のように行き先を固定すると、同じボタンを複数の画面に置いた時「一覧からでも詳細からでも一覧に飛ばされる」といったことが起きる。
`redirect_back` ならどこから来ても元の画面に戻れる。

`fallback_location:` はHTTPの`Referer`が取得できなかった場合の戻り先として指定する時に使う

```ruby
def destroy
  @item.destroy
  redirect_back fallback_location: items_path
end
```

- `redirect_back` → 直前の画面に戻る
- `fallback_location: items_path` → 戻り先が分からない時だけ一覧画面に戻す
