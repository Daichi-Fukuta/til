php-simple-html-dom-parserというライブラリを使う。
[https://sourceforge.net/projects/simplehtmldom/files/:embed:cite]


↑からライブラリをダウンロードしてプログラムを書くファイルと同じディレクトリに保存する。

```php
<?php
// simple_html_dom.phpの読み込み
require_once "simple_html_dom.php";

// スクレイピングしたいサイトのURL
$url = "https://www.example.com";

// $urlからオブジェクトを生成
$html = file_get_html($url);

// 上記URLのページの1つ目のpタグを取得して出力。
// 1つ目のパラメータでタグを指定、2つ目のパラメーターで何番目かを指定
print_r($html->find("p", 0)->plaintext);
```