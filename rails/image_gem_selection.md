# 画像加工・保存まわりのgem選定理由（vips / Active Storage）

## 画像加工エンジン: MiniMagickではなくvipsを選定

スマホで画像を登録する想定があり、大きい画像の処理に強いvips（`ruby-vips`）を採用した。

```ruby
# config/application.rb
config.active_storage.variant_processor = :vips
```

## 画像保存: Shrine / CarrierWaveではなくActive Storageを選定

今回はアイテムに画像を1枚つける程度のシンプルな用途で、Rails標準のActive Storageで十分だった。表示用にリサイズする要件と `variant` 機能の相性も良かった。

- CarrierWave: 使ったことがあった
- Shrine: 興味はあったが、高機能・柔軟な分、自分でカスタマイズする必要がある場面が多そうだったので今回は見送り

```ruby
class Item < ApplicationRecord
  has_one_attached :image
end

item.image.variant(resize_to_limit: [600, 600])
```
