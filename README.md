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
+ [test.scss](chap2/test.scss)

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
+ [ネストの基本](chap3/01.scss)

+ [子孫セレクタ以外のセレクタを使うには](chap3/02.scss)

+ [@mediaのネスト](chap3/03.scss)

### 親セレクタの参照&(アンパサント） ###
+ [&をつかった親セレクタの参照](chap3/04.scss)

### プロパティのネスト ###
+ [プロパティのネスト](chap3/05.scss)

### Sassで使えるコメント ###
+ [一行コメント](chap3/06.scss)

+ [通常のコメント](chap3/07.scss)

### 変数(Variables) ###
+ [変数の基本](chap3/08.scss)

+ 変数名で使えない文字
  + 数字から始まっている
  + @など使えない記号
  + 連続したハイフンから始まっている
  
+ [ルールセット内で変数を宣言する](chap3/09.scss)

+ [変数の参照範囲（スコープ）](chap3/10.scss)

+ [変数を参照できる場所](chap3/11.scss)

### 演算 ###
+ [演算の基本](chap3/12.scss)

+ [別々の単位で演算する](chap3/13.scss)

+ [変数と演算を同時に利用する](chap3/14.scss)

+ [色の演算](chap3/15.scss)

### Sassの@import ###
+ [Sass独自の@import](chap3/16.scss)

+ [インポートファイルの複数指定](chap3/17.scss)

+ @importのネスト

## <a name="cha4">Sassの高度な機能 ##

### スタイルの継承ができる@extend ###
+ @extendの基本  
  [01.scss](chap4/01.scss)  
  [_extend.scss](chap4/_extend.scss)  
  [style.scss](chap4/style.scss)  

+ [同じルールセット内で、複数継承する](chap4/02.scss)
  
+ [@extendの連鎖](chap4/03.scss)
  
+ [@extendが使えるセレクタ使えないセレクタ](chap4/04.scss)
  

+ [@media内では@extendは使用できない](chap4/05.scss)
  
### 柔軟なスタイルの定義が可能なミックスイン(@mixin) ###
+ [ミックスインの基本](chap4/06.scss)
  
+ [引数を使ったミックスイン](chap4/07.scss)
  
+ [引数に初期値を定義する](chap4/08.scss)
  
+ [引数を複数定義する](chap4/09.scss)
  
+ [,（カンマ）を使うプロパティには可変長引数を利用する](chap4/10.scss)
  
+ [複数の引数があるミックスインを読み込む際に可変長引数を使う](chap4/11.scss)
  
+ [ミックスインのスコープを制限する](chap4/12.scss)
  
+ [ミックスインにコンテントブロックを渡す@content](chap4/13.scss)
  
+ [ミックスイン名で使える文字と使えない文字](chap4/14.scss)
  
### 制御構文で条件分岐や繰り返し処理を行う ###
+ @ifを使って条件分岐をする  
  [例１](chap4/15.scss)  
  [例２](chap4/16.scss)  

    + @ifで使える比較演算子
    
    | 演算子   | 説明             |
    |:---------|:-----------------|
    | A == B   | AとBは同じ       |
    | A > B    | AはBより大きい   |
    | A < B    | AはBより小さい   |
    | A >= B   | AはB以上         |
    | A <= B   | AはB以下         |
    | A != B   | AとBは等しくない |

    + @ifで使える論理演算子
    
    | 演算子   | 説明             |
    |:---------|:-----------------|
    | and      | かつ             |
    | or       | または           |
    | not      | 否定             |

+ @forで繰り返し処理を行う  
  [例１](chap4/17.scss)  
  [例２](chap4/18.scss)  

+ @whileでより柔軟な繰り返し処理を行う  
  [例１](chap4/19.scss)  
  [例２](chap4/20.scss)  

+ [@eachでリスト（配列）の要素に対して繰り返し処理を実行する](chap4/21.scss)
  
### 関数を使ってさまざまな処理を実行する ###

+ [数値の絶対値を取得するabs()](chap4/22.scss)
  
+ [数値の小数点以下を四捨五入するround()](chap4/23.scss)
  
+ [数値の小数点以下を切り上げるceil()と切り捨てるfloor()](chap4/24.scss)
 
+ [16進数のRGB値に透明度を指定して、RGBA形式に変換できるrgba()](chap4/25.scss)
  
+ [明るい色を簡単に作れるlighten()と暗い色を簡単に作れるdarken()](chap4/26.scss)
  
+ [２つのカラーコードの中間色を作れるmix()](chap4/27.scss)
  
+ [リストのN番目の値を取得できるnth()](chap4/28.scss)
  
### 自作関数を定義する@function ###
+ @functionとは

+ [オリジナル関数の例](chap4/29.scss)
  
+ [ネイティブ関数と組み合わせる](chap4/30.scss)
  
+ [値を変数に入れる](chap4/31.scss)
  
+ [引数に初期値を設定する](chap4/32.scss)
  
### テストやデバッグで使える@debugと@warn ###

+ [@debugで結果を確認する](chap4/33.scss)
  
+ [@warnで警告を表示する](chap4/34.scss)
  
### Sassのデータタイプについて ###

+ データタイプの種類
  + Number型(数値)
  + Color型(色)
  + String型(文字列)
  + Boolean型(真偽)
  + List型(リスト)
  + Null型(空の値)

+ データタイプを判別する  
  [例１](chap4/35.scss)  
  [例２](chap4/36.scss)  

### 使いどころに会わせて補完してくれる#{} ###
+ [インターポレーションとは](chap4/37.scss)
  
+ [演算しないようにする](chap4/38.scss)
  
+ [演算できない場所で演算する](chap4/39.scss)
  
+ [アンクォートもしてくれるインターポレーション](chap4/40.scss)
  
### 変数にデフォルト値を割り当てる!default ###
+ !defaultフラグとは  
  [例１](chap4/41.scss)  
  [例２](chap4/42.scss)  

# 参照 #

[Web制作者のためのSassの教科書](http://book.scss.jp/)

[scss-mode.elを使う](http://qiita.com/sawamur@github/items/bb50d84af4d01a2eb5c2)
