# browser-sync
Node.js browser-syncのサンプル

# 環境

## gulp

gulpをCLIから使えるように、-gオプション付きでインストール

```
npm install -g gulp-cli
```

権限のエラーが出た場合は、sudo付きで実行する

```
pi@raspi3-1:~/browser-sync $ npm install -g gulp-cli
npm WARN checkPermissions Missing write access to /usr/local/lib/node_modules
↑↑
Permissionのエラー


$ sudo npm install -g gulp-cli
↑↑
sudo を付けてやり直し
```



npmのアプリケーション内にgulpとbrowser-syncパッケージをインストール

```
cd (Nodeアプリのディレクトリ)
npm install --save gulp
npm install --save browser-sync
```


