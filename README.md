Sass入門
=================

# 目的 #
Sassが使えるようになる

# 前提 #
| ソフトウェア   | バージョン   | 備考        |
|:---------------|:-------------|:------------|
| OS X           |10.8.5        |             |
| ruby           |2.0.0p0       |             |
| sass           |3.2.0         |             |

# 構成 #
+ セットアップ
+ Sassコマンドの使い方
+ Sassの基本機能
    
# 詳細 #

## セットアップ ##

    $ rvm use ruby-2.0.0-p0
    $ rvm gemset create sass
    $ rvm use ruby-2.0.0-p0@sass
    $ gem install sass

## Sassコマンドの使い方 ##
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

## Sassの基本機能 ##

# 参照 #

[Web制作者のためのSassの教科書](http://book.scss.jp/)

[scss-mode.elを使う](http://qiita.com/sawamur@github/items/bb50d84af4d01a2eb5c2)
