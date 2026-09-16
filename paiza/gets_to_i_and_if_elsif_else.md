# 標準入力の受け取り（gets.to_i）と条件分岐（if/elsif/==）の基本

<!-- paiza復習メモ -->

- `gets`メソッド → ユーザーが入力した文字列を取得する。
- `.to_i`をつけると数値に変換できる。

比較演算子:

```ruby
a == b   # 等しい
a != b   # 等しくない
a > b    # より大きい
a < b    # より小さい
a >= b   # 以上
a <= b   # 以下
```

論理演算子:

```ruby
a && b   # かつ（AND）
a || b   # または（OR）
!a       # 否定（NOT）
```

```ruby
n = gets.to_i

if n > 10
  puts "10より大きい"
elsif n == 10
  puts "10と等しい"
else
  puts "10より小さい"
end

# 実行例（入力: 15）
# $ ruby sample.rb
# 15
# 10より大きい
```

出典: paiza復習
