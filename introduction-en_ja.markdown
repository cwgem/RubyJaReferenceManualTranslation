Introduction
============

Ruby is an easy to use object oriented interpreted scripting language. It has a wealth of features for text processing and systems administration, much like Perl. 

Rubyは手軽なオブジェクト指向プログラミングのためのインタプリタ言語です。 Rubyは(Perlのような)テキスト処理やシステム管理のための豊富な機能を持っています。 また、Rubyは単純で、分かりやすく、簡単に拡張できます。

もし、簡単なオブジェクト指向のための言語を求めていたり、 Perlは見にくいと感じていたり、 Lispの考え方は好きだがあの括弧の多さには困ると感じているなら、 Rubyはまさにぴったりです。

Rubyの特長は次の通りです。

Interpreted インタプリタ
------
Since Ruby is an interpreted language, there is no need for compilation to run a program.

Rubyはインタプリタ言語ですので プログラムを実行するためにコンパイルする必要はありません。

Dynamically Typed Variables 変数に型が無い (動的型付け)
---------------
Variables in Ruby can store any type of data, so there is no need to worry about a variable's data type. On the other hand, compile time checking becomes less effective.

Rubyの変数はどのような型のデータも格納する事ができますので、 変数の型について心配する必要はありません。 半面、コンパイル時のチェックは弱くなります。

Variable Declaration is Unnecessary 変数宣言が不要
-------
Variables in Ruby can be used without having to declare them. The actually type of variable(local, global, instance) can be determined from the variable name.

Rubyでは変数を宣言無しで使う事ができます。 変数の種類(ローカル変数、グローバル変数、インスタンス変数など)は 変数名から知る事ができます。

Simple Grammar 単純な文法
--------------
Ruby has a simple grammar is slightly influenced by Eiffel.
Rubyの文法はEiffelからわずかに影響を受けた単純なものです。

No User-Based Memory Management ユーザによるメモリ管理が不要
--------------
Ruby handles memory management automatically. Objects that are no longer accessed are collected by a garbage collector built into the interpreter.
Rubyはメモリ管理を自動的に行います。 どこからもアクセスされなくなったオブジェクトは インタプリタに組み込みのガーベージコレクタによって回収されます。

Everything is an Object 全てがオブジェクト
---------
Ruby was designed form the start to be a very simplistic object oriented language. 

Rubyははじめから純粋なオブジェクト指向言語として設計されています。 整数のような基本的なデータ型をはじめとして、 全てのデータをオブジェクトとして統一的に取り扱えます。

Classes, Inheritance, Methods クラス、継承、メソッド
-----------
Ruby contains basic object oriented language features such as classes, inheritance, and methods.
Rubyは クラス、継承、メソッドのようなオブジェクト指向言語として基本的な機能は 当然持っています。

Singleton Methods 特異メソッド
------
ある特定のオブジェクトにメソッドを付加することができます。 たとえば、GUIのあるボタンを押された時の動作を メソッドとして記述するような使い方ができますし、 これを応用してプロトタイプベースの オブジェクト指向プログラミングも可能です(やりたければね)。

Mix-ins Through Modules モジュールによるMix-in
---------------
Rubyは多重継承は複雑さの源であるという見地から、 意図的に多重継承を持っていませんが、 モジュールを使ってクラス階層を横断して実装を共有できます。 この機能を"Mix-in"と呼びます。

Methods Can Utilize Blocks (Iterators) ブロック付きメソッド呼び出し(イテレータ)
---------------------
制御構造の抽象化を援助するブロック付きメソッド呼び出しという機能があります。

Closures クロージャ
-----
Procedures can be treated as objects. Treating these procedures as objects is known as closures. 

手続きをオブジェクトとして扱う機能があります。 このオブジェクト化された手続きのことをクロージャと呼びます。

Powerful String Manipulation/Regular Expressions 強力な文字列操作/正規表現
-------------
Using Perl as a model, Ruby contains powerful string manipulation and regular expression functionality.

Perlをお手本とした強力な文字列操作や正規表現検索の機能があります。

Bignum 多倍長整数
-----
There is builtin support for Bignum, so very large integer calculations can be achieved (as long as sufficient memory is available). For example, the factorial of 400 can easily be calculated.

組み込みの多倍長整数機能がありますので、 メモリが許す限り、非常に大きな整数の演算もできます。 たとえば、400の階乗なども簡単に計算できます。

Exception Handling 例外処理機能
------
Exception handlers can be easily written to handle exceptional program behavior.

例外処理機能は例外的な状況への対処が簡単に書けます。

Direct OS Access OSへの直接アクセス
----------
Ruby is able to make UNIX style system calls. This means that system programming can be done using Ruby alone.

Rubyは(UNIXの)ほとんどのシステムコールの呼び出し機能を持っています。 Rubyだけでシステムプログラミングも可能です。

Dynamic Loading ダイナミックローディング
------------
The loading of shared object files is supported if the OS allows for it.

OSが許せば、オブジェクトファイルを実行時に読み込む機能が提供されます。