vim でgrepを実行すると、QuickFixというバッファに検索結果が出力される。
検索結果から不要な行を削除したくなることがある。

この場合、Quickfix のバッファに移動した後

```
:set modifiable
```

を実行すると、QuickFixのバッファから自由に行を削除できるようになる。
ただし、このままでは検索結果のジャンプで、削除した行の結果にも飛んでしまう。
ここで、

```
:cbuffer
```

を実行することで、QuickFixのバッファの結果がリセットされ、整理後の検索結果だけをジャンプして回ることができる。
なお、:cbuffer でQuickFixのバッファを再読み込みするためには、.vimrc に errorformat が設定されている必要がある。
grep の errorformat は、vimrc に以下のように設定する。

```
set errorformat=%f\|%l\ col\ %c\|\ %m
```

また、QuickFix のバッファで、:w を実行すれば結果をテキストファイルに保存できる。この結果は、

```
vim -q error.txt
```

で vim起動時に QuickFixに流しこむことができる。

vim起動後に既存のファイルをQuickFixに読みこむ場合

```
:cfile
```
を使用する。findコマンドの出力をそのまま使いたい場合

```
:set errorformat=%f
```

とした上で読みこむこと。
