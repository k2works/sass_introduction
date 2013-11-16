Sass入門
=================

# 目的 #
Sassが使えるようになる

# 前提 #
| ソフトウェア   | バージョン   | 備考        |
|:---------------|:-------------|:------------|
| OS X           |10.8.5        |             |
| ruby           |2.0.0p0       |             |
| sass           |3.2.12        |             |

# 構成 #
+ [セットアップ](#cha1)
+ [Sassコマンドの使い方](#cha2)
+ [Sassの基本機能](#cha3)
+ [Sassの高度な機能](#cha4)
# 詳細 #

## <a name="cha1">セットアップ ##

    $ rvm use ruby-2.0.0-p0
    $ rvm gemset create sass
    $ rvm use ruby-2.0.0-p0@sass
    $ gem install sass

## <a name="cha2">Sassコマンドの使い方 ##
+ test.scss

        #main {
          width: 600px;
          p {
            margin: 0 0 1em;
            em {
              color: #f00;
            }
          }
          small {
            font-size: small;
          }    
        }

+ コンパイル

        $ sass test.scss:test.css        

+ アウトプットスタイルを指定する

        $ sass test.scss:test.css --style expanded
        $ sass test.scss:test.css --style nested
        $ sass test.scss:test.css --style expanded
        $ sass test.scss:test.css --style cmpact
        $ sass test.scss:test.css --style compressed

+ ファイルの更新を監視する

        $ sass --watch input.scss:output.css
        $ sass --watch input
        $ sass --watch .
        $ sass --watch input:css/output

## <a name="cha3">Sassの基本機能 ##

### ルールのネスト ###
+ ネストの基本
  chap3/01.scss

+ 子孫セレクタ以外のセレクタを使うには
  chap3/02.scss

+ @mediaのネスト
  chap3/03.scss

### 親セレクタの参照&(アンパサント） ###
+ &をつかった親セレクタの参照
  chap3/04.scss

### プロパティのネスト ###
+ プロパティのネスト
  chap3/05.scss

### Sassで使えるコメント ###
+ 一行コメント
  chap3/06.scss

+ 通常のコメント
  chap3/07.scss

### 変数(Variables) ###
+ 変数の基本
  chap3/08.scss

+ 変数名で使えない文字
  + 数字から始まっている
  + @など使えない記号
  + 連続したハイフンから始まっている
  
+ ルールセット内で変数を宣言する
  chap3/09.scss

+ 変数の参照範囲（スコープ）
  chap3/10.scss

+ 変数を参照できる場所
  chap3/11.scss

### 演算 ###
+ 演算の基本
  chap3/12.scss

+ 別々の単位で演算する
  chap3/13.scss

+ 変数と演算を同時に利用する
  chap3/14.scss

+ 色の演算
  chap3/15.scss

### Sassの@import ###
+ Sass独自の@import
  chap3/16.scss

+ インポートファイルの複数指定
  chap3/17.scss

+ @importのネスト

## <a name="cha4">Sassの高度な機能 ##

# 参照 #

[Web制作者のためのSassの教科書](http://book.scss.jp/)

[scss-mode.elを使う](http://qiita.com/sawamur@github/items/bb50d84af4d01a2eb5c2)
