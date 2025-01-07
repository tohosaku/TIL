"width not divisible by 2"

というエラーが出た。画像のピクセル数が奇数の場合に出る

以下のように `vf` オプションをつける必要がある。`r`は1秒あたりのコマ数

```
ffmpeg -i ./input.webm -r 8 -vf "scale=trunc(iw/2)*2:trunc(ih/2)*2" output.mp4
```
