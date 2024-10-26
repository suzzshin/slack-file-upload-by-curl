# Slack ファイルアップロードサンプルスクリプト

curl コマンドを使って Slack にファイルをアップロードする bash スクリプトのサンプル。

# 使い方

内部で jq コマンドを使っているので、事前にインストールしておく。
Slack 権限は公式ドキュメント参照する。Bot であれば files:write のみで動作する。

# 動作しないとき

アプリを対象チャンネルに追加していない場合 completeUploadExternal で以下のようなエラーが返る。chat:write.public 権限を持たせてもエラー。Slack の左下のアプリからアプリを選択してチャンネルに追加すること。

```
"error":"channel_not_found"
```

# リファレンス

- https://api.slack.com/methods/files.getUploadURLExternal
- https://api.slack.com/methods/files.completeUploadExternal
