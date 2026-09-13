# boolean型のカラムには自動で `カラム名?` メソッドが定義される

boolean型（true/false の2値だけを持つデータ型）のカラムには、ActiveRecordが自動的に `カラム名?` という確認用メソッドを定義してくれる。`in_stock` カラム（在庫の有無、true/false）なら `item.in_stock?` がそのまま使える。

これまでは「`stock_quantity` が0より多いか」を判定するために `stock_available?` / `out_of_stock?` をそれぞれ用意していたが、在庫数そのものは問わないことにしたのでこれらは削除し、`in_stock` カラム（boolean）に置き換えて自動生成の `in_stock?` を使うことにした。

```ruby
class Item < ApplicationRecord
end

item.in_stock? # => true / false
```
