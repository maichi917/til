# RenderでRailsの定期タスク（Cron Job）を設定する

Renderには「Cron Job」というサービス種別があり、指定したスケジュールでコマンドを1回実行してくれる。Webサービスとは別もの

## 設定するもの

- **Command**: 実際に実行するコマンド。例: `bundle exec rails guest:cleanup`
  - Webサービスの設定をコピーして作って起動コマンド（`bundle exec rails server`）のまま数日放置していたのでその間はcronは実行されていなかった。注意！
- **Schedule**: cron形式でスケジュールを指定。例: `0 23 * * *`（毎日23:00 UTC）
- **環境変数**: Webサービスとは別サービス扱いなので、`DATABASE_URL`や`RAILS_MASTER_KEY`など必要な環境変数はこちらにも個別に設定する（自動では引き継がれない）

## 動作確認

基本はスケジュール通り実行される
実行確認はRender管理画面の「Trigger Run」ボタンで手動実行し、ログを確認する

えらぶノート（issue #326）
