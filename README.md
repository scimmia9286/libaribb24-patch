# libaribb24-patch

## 概要
このリポジトリには2つのパッチをアップロードしました。
1. ffmpegのモジュールであるlibaribb24用
2. libaribb24の内部で使用されているarib-b24デコーダ用

## 改善内容
1. 字幕のdurationを*ほぼ*実用範囲の値で出力するため、ffmpegに-fix_sub_durationを指定しなくても良くなる
2. スタイル付きの字幕(ass/ssaなど)を出力した際のスタイル崩れを改善
3. 字幕の画面からのはみ出しを調整

## 動作検証バージョン
ffmpeg-4.3.2

## 備考
aribb24デコーダのパッチは字幕スタイルの調整を目的としたものです。
必要な場合はパッチを適用して見てください。

### 修正の概要
libaribb24が内部で利用している[aribb24](https://github.com/nkoriyama/aribb24)は[MSZ](Middle Size)文字
は通常文字の50%幅で処理しています。
これでは表示に違和感がったため80%に調整しました。
