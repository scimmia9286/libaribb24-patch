# libaribb24-patch

## 概要
FFmpegでARIB STD-B24字幕をデコードすると、字幕の文字サイズや色がおかしくなったり画面からはみ出したりするなど、少し不満がありました。
これを少しでも改善しようと色々と試行錯誤した結果をパッチとして公開します。

## 修正内容
1. FFmpegのARIB STD-B24字幕デコード処理の不具合修正
2. ASSヘッダーのfontname, outline, shadowの設定を変更
3. 字幕の表示位置を再現

## FFmpeg実行時の注意点
FFmpegを用いてARIB字幕を扱う場合は必ず **-fix_sub_duration** オプションを指定してください

## 動作検証バージョン
- ffmpeg-4.3.2
- ffmpeg-4.4
