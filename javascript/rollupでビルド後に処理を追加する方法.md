プラグインを自作するほどでもない処理は、buildEnd hook に書くことができる。

plugins の配列の中に以下のように処理を書ける。

```
{
  name: "copy-files",
  buildEnd() {
    copyFileSync('./a.txt', './b.txt')
  }
}
```
