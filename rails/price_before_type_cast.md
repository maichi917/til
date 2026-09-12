# `カラム名_before_type_cast` で型変換前の値が取れる

ActiveRecordは各カラムの値について、型キャストされた値だけでなく「代入されたそのままの値」も保持している。`属性名_before_type_cast` で取り出せる。

全角数字の文字列をinteger属性に代入すると `to_i` で `0` になってしまうが、`before_validation` の中で変換前の生の文字列を取り出せば、そこから正規化できる。

```ruby
before_validation :normalize_price

def normalize_price
  self.price = price_before_type_cast.to_s.tr("０-９．", "0-9.")
end
```

出典: Qiita記事へのコメント
