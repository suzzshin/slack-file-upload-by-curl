# Slack ファイルアップロードサンプルスクリプト

curl コマンドを使って Slack にファイルをアップロードする bash スクリプトのサンプル。

# 使い方

内部で curl, jq コマンドを使っているので、事前にインストールしておく。

Slack 権限は公式ドキュメント参照する。Bot であれば files:write のみで動作する。

```
# your_invoke_script.sh

source /path/to/this/script.sh

execute_file_upload "your_token" "your_channel_id" "your_file_path"
```

# 動作しないとき

アプリを対象チャンネルに追加していない場合 completeUploadExternal で以下のようなエラーが返る。chat:write.public 権限を持たせてもエラー。Slack の左下のアプリからアプリを選択してチャンネルに追加すること。

```
"error":"channel_not_found"
```

# リファレンス

- https://api.slack.com/methods/files.getUploadURLExternal
- https://api.slack.com/methods/files.completeUploadExternal
