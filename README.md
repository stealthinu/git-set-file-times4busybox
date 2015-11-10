# git-set-file-times for busybox

git clone等で取得したファイルのタイムスタンプが、gitコマンドを発行した日時になってしまうため、それをcommitした日時になおすためのスクリプトです。

これはgitのwikiにperlスクリプトで書かれているものがあります。

https://git.wiki.kernel.org/index.php/ExampleScripts#Setting_the_timestamps_of_the_files_to_the_commit_timestamp_of_the_commit_which_last_touched_them

これと同様のことをshellスクリプトで行うものが下記サイトにあります。

コミット日付をタイムスタンプに復元したい
http://www.shigemk2.com/entry/git.timestamp

しかし、このままではMobaXTermの標準環境で使われているbusyboxだと動かなかったため、一部を修正したものがこのshellスクリプトです。

busyboxのdateコマンドでは「+0900」という書式でのTZ指定はエラーになってしまうため「+09:00」という形に置き換えるようになっています。
