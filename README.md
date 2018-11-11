# browser-sync
Node.js browser-syncのサンプル

# パッケージのインストール

## Gulpとbrowser-syncのインストール

GulpをCLIから使えるように、-gオプション付きでインストール

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

# 監視対象のファイルを準備

/htdocs/index.html

```
<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<title>shot timer result</title>
</head>
<body>

<style>
p{
    margin: 0 0 10px;
}
.textarea{
    padding: 0 0 10px;
}
.txtWrap{
    font-size: 10px;
}

.txt40{
    font-size: 40vw;
}
</style>

<div class="textarea">
    <p class="txt40">8.88</p>
</div>

</body>
</html>

```


# Gulp側の準備

gulpfile.js

```
var gulp = require('gulp');
var browserSync = require('browser-sync');
var reload = browserSync.reload;


gulp.task('default', ['browser-sync']);

gulp.task('browser-sync', function () {
  browserSync({
    notify: false,
    server: {
      baseDir: "htdocs"
    }
  });

gulp.watch('htdocs/index.html', reload);
});
```


# Gulpの起動

```
$ gulp
```
