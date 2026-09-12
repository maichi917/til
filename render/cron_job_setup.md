# RenderでRailsの定期タスク（Cron Job）を設定する

Renderには「Cron Job」というサービス種別があり、指定したスケジュールでコマンドを1回実行してくれる。Webサービスとは別サービスとして作る。

## 設定するもの

- **Command**: 実際に実行するコマンド。例: `bundle exec rails guest:cleanup`
  - Webサービスの設定をコピーして作ると、起動コマンド（`bundle exec rails server`など）のまま残ってしまうので要注意。ここが一番のハマりどころ。
- **Schedule**: cron形式でスケジュールを指定。例: `0 23 * * *`（毎日23:00 UTC）
- **環境変数**: Webサービスとは別サービス扱いなので、`DATABASE_URL`や`RAILS_MASTER_KEY`など必要な環境変数はこちらにも個別に設定する（自動では引き継がれない）

## 動作確認

保存しただけではスケジュールが来るまで動かないので、Render管理画面の「Trigger Run」ボタンで手動実行し、ログを見て正しく動くか確認してから運用に入る。

出典: 自分のアプリの運用（issue #326）
