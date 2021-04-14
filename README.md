# libaribb24-patch

## 概要
このリポジトリには2つのパッチをアップロードしました。
1. ffmpegのモジュールである[FFmpeg/libavcodec/libaribb24.c](https://github.com/FFmpeg/FFmpeg/blob/master/libavcodec/libaribb24.c)用のパッチ
2. libaribb24の内部で使用されているデコーダ[aribb24/src/decoder.c](https://github.com/nkoriyama/aribb24/blob/master/src/decoder.c)用のパッチ

## 改善内容
1. 字幕のdurationを*ほぼ*実用範囲の値で出力するため、ffmpegに-fix_sub_durationを指定しなくても良くなる
2. スタイル付きの字幕(ass/ssaなど)を出力した際のスタイル崩れを改善
3. 字幕の画面からのはみ出しを調整

## 動作検証バージョン
ffmpeg-4.3.2

## 備考
aribb24デコーダのパッチは字幕スタイルの調整を目的としたものです。
必要な場合はパッチを適用して見てください。

### aribb24の修正概要
aribb２４デコーダはarib-b24仕様で定義されている<MSZ>(Middle Size)文字を通常文字の50%幅で処理しています。
これでは表示に違和感があったため80%幅に調整しました。
