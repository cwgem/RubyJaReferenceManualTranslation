# Ruby Command #

The following is the format for invoking the Ruby interpreter.

ruby [ option ...] [ -- ] [ programfile ] [ argument ...]

`option` indicates any of the after-mentioned available command line options. `--` is used to terminate the list of command line options. `programfile` is a file containing ruby script. If `-` is specified for the `programfile`, ruby script will be read from standard input instead.

A `programfile` that starts with `#!` (known as a shebang) has a special interpretation. Please refer to the section _Interpreter Line Explanation_ for more information. For shells that don't handle wildcards (Win32), Ruby handles the expansion behind the scenes before setting the Kernel::ARGV constant. In this case, the wildcards '\*', '?', '[]', and '\*\*/' can be used ('{..}' cannot be used due to conflicts with `Dir.glob`). If wildcard expansion is not desired, simply enclose the argument in single quotes('). 

Rubyインタプリタの起動は以下の書式のコマンドラインにより行います。

ruby [ option ...] [ -- ] [ programfile ] [ argument ...]
ここで、option は後述のコマンドラインオプション のいずれかを指定します。-- は、オプション列の終りを明示するため に使用できます。programfile は、Ruby スクリプトを記述したファイ ルです。これを省略したり`-' を指定した場合には標準入力を Ruby ス クリプトとみなします。

programfile が `#!' で始まるファイルである場合、特殊な解釈 が行われます。詳細は後述のインタプリタ行の解釈 を参照 してください

argument に指定した文字列は組み込み定数 Kernel::ARGV の初 期値として設定されます。標準のシェルがワイルドカードを展開しない環境 (Win32)では、Ruby インタプリタが自前でワイルドカードを展開して Kernel::ARGV に設定します。この場合ワイルドカードとして `*', `?', `[]', `**/' が使用できます (Dir.glob と異なり `{..}' は使えません)。Win32 環境で、 ワイルドカード展開を抑止したい場合は引数をシングルクォート(') で括りま す。

## Command Line Options コマンドラインオプション ##

The Ruby interpreter accepts the following command line options. Many of them are similar to those in Perl.

Rubyインタプリタは以下のコマンドラインオプションを受け付けま す。基本的にPerlのものと良く似ています。

### -0[Number] -0数字 ####

Specifies the record seperator($/) in octal format.

If no numeric value is specified the seperator will default to a null character ($/ = "\0"). Any command line switches after the numeric value will not have an effect on it.

`-00` enables paragraph mode ($/ = ""). If a numeric value is given that does not map to a character code, the file will be read all at once(the same as $/=nil).

入力レコードセパレータ($/)を8進数で指定します。

数字を指定しない場合はヌルキャラクタがセパレータになります ($/ = "\0" と同じ)。 数の後に他のスイッチがあっても構いません。

-00で, パラグラフモード($/=""と同じ), -0777で (そのコードを持つ文字は存在しないので)ファイルの内容を全部一度に読み 込むモード($/=nilと同じ)に設定できます。

### -a ###

Often used with the `-n` and `-p` switches, it enables auto split mode. Auto split mode results in the following logic, essentially splitting on `$;` (which is ' ' by default):

    $F = $_.split

Since this option depends on the loops provided by `-n` and `-p`, it's not very usefull without them.

`-n'や`-p'とともに用いて, オートスプリットモードをONにします。 オートスプリットモードでは各ループの先頭で,

    $F = $_.split
    
が実行されます。`-n'か`-p'オプションが同時に指定されない限り, このオプションは意味を持ちません。

### -C directory ####

Changes to the indicated directory before executing the script.

スクリプト実行前に指定されたディレクトリに移動します。

### -c ####

Compiles the script in order to check the syntax. If there are no errors, "Syntax OK" will be displayed.

スクリプトの内部形式へのコンパイルのみを行い, 実行しません。コンパイル終 了後, 文法エラーが無ければ, "Syntax OK"と出力します。

### --copyright ###

Displays copyright information.

著作権表示をします。

### -d ###
### --debug ###

Runs the script in debug mode. This will set the global $DEBUG variable to true.

デバッグモードでスクリプトを実行します。$DEBUG を true にします。

### -E ex[:in] ###
### --encoding ex[:in] ###

Sets the default external and internal encoding using a colon deliminated string. External encoding indicates what encoding to expect from external sources such as STDIN, pipes, and files. Internal encoding is that which ruby uses to handle internal values such as strings. If an internal encoding is not specified, the value of `Encoding.default_internal` is set to nil. When the external encoding is ommitted by using `:encoding`, the external encoding value defaults to the value set for the internal encoding.

デフォルトの外部エンコーディングと内部エンコーディングを:区切りで指定 します。内部エンコーディングを省略した場合は Encoding.default_internal は nil になります。また、:エンコーディ ング のように外部エンコーディングを省略した場合は内部エンコーディング のみを変更します。

### -e script ###

Runs script from the comman line, indicated by the argument value. When the `-e` option is used, the script file name will not be accessible from the arguments.

When `-e` is set multiple times, a newline will be inserted between each script before being interpreted.

    The following are equivalent
    ruby -e "5.times do |i|" -e "puts i" -e "end"

    ruby -e "5.times do |i|
      puts i
    end"

    ruby -e "5.times do |i|; puts i; end"    

コマンドラインからスクリプトを指定します。-eオ プションを付けた時には引数からスクリプトファイル名を取りませ ん。

-e オプションを複数指定した場合、各スクリプトの間に改行を 挟んで解釈します。

    以下は等価です。
    ruby -e "5.times do |i|" -e "puts i" -e "end"

    ruby -e "5.times do |i|
      puts i
    end"

    ruby -e "5.times do |i|; puts i; end"

### -Fregexp ###

Sets the input field seperator($;, used by String#split) to `regex`.

入力フィールドセパレータ($;)に regexp をセットします。

### -h ###
### --help ###

Displays help for the command line options.

コマンドラインオプションの概要を表示します。

### -i[extension] ###

Modifies the contents of the file indicated in the arguments(in-place edit). The original file will be backed up using the suffix indicated by extension, unless no extension is specified.

Example:

    % echo matz > /tmp/junk
    % cat /tmp/junk
    matz
    % ruby -p -i.bak -e '$_.upcase!' /tmp/junk
    % cat /tmp/junk
    MATZ
    % cat /tmp/junk.bak
    matz

引数で指定されたファイルの内容を置き換える(in-place edit)こ とを指定します。元のファイルは拡張子をつけた形で保存されます。 拡張子がなければ、バックアップは行われず、変更されたファイル だけが残ります。

例:

    % echo matz > /tmp/junk
    % cat /tmp/junk
    matz
    % ruby -p -i.bak -e '$_.upcase!' /tmp/junk
    % cat /tmp/junk
    MATZ
    % cat /tmp/junk.bak
    matz

### -I directory ###

Updates the file load path to include `directory`. This value will added to the $: array variable.

ファイルをロードするパスを指定(追加)します。指定されたディレ クトリはRubyの配列変数($:)に追加されます。

### -l ###
行末の自動処理を行います。まず、$\ を $/ と同じ値に設定し, printでの出力 時に改行を付加するようにします。それから, -n フラグまたは-pフラグが指定されていると gets で読み込まれた各行の最後に対して String#chop!を行います。

### -n ###
このフラグがセットされるとプログラム全体が sed -nやawk のように

    while gets
     ...
    end
で囲まれているように動作します.

### -p ###
-nフラグとほぼ同じですが, 各ループの最後に変数 $_ の値を出力するようになります。

例:

    % echo matz | ruby -p -e '$_.tr! "a-z", "A-Z"'
    MATZ

### -r feature ###
スクリプト実行前に feature で指定されるライブラリを Kernel.#require します。 `-n'オプション、`-p'オプションとともに使う時に特に有効です。

### -s ###
スクリプト名に続く, `-'で始まる引数を解釈して, 同名のグローバル変数に値 を設定します。`--'なる引数以降は解釈を行ないません。該当する引数は Kernel::ARGV から取り除かれます。

例:

    #! /usr/local/bin/ruby -s
    # prints "true" if invoked with `-xyz' switch.
    print "true\n" if $xyz

### -S ###
スクリプト名が`/'で始まっていない場合, 環境変数 PATHの値を使ってスクリプトを探すことを指定しま す。 これは、#!をサポートしていないマシンで、 #! による実行をエミュレートするために、以下の ようにして使うことができます:

    #!/bin/sh
    exec ruby -S -x $0 "$@"
    #! ruby
システムは最初の行により、スクリプトを/bin/sh に渡します。/bin/shは2行目を実行しRubyインタプリタを起動します。 Rubyインタプリタは-x オプションにより`#!'で始まり, "ruby"という文字列を含む行までを 読み飛ばします。

システムによっては $0は必ずしもフルパスを含まな いので、`-S'を用いてRubyに必要に応じてスクリプトを探すように 指示する必要があります。

### -T[level] ###
不純度チェックを行います。level を指定すると安全度レベルをその レベルに設定します。level 省略時は 1 を指定したのと同じです。 CGIプログラムなどでは-T1 程度を指定しておく方が良いでしょう。 $SAFE に指定したレベルがセットされます。

### -v ###
### --verbose ###
冗長モード。起動時にバージョンの表示を行い, 組み込み変数 $VERBOSEをtrueにセットします。この変数がtrueで ある時, いくつかのメソッドは実行時に冗長なメッセージを出力し ます。`-v'オプションが指定されて, それ以外の引数がない時には バージョンを表示した後, 実行を終了します(標準入力からのスク リプトを待たない).

### --version ###
Rubyのバージョンを表示します。

### -w ###
バージョンの表示を行う事無く冗長モードになります。

### -W[level] ###
冗長モードを三段階のレベルで指定します。それぞれ以下の通りです。

     * -W0: 警告を出力しない
     * -W1: 重要な警告のみ出力(デフォルト)
     * -W2 or -W: すべての警告を出力する
組み込み変数 $VERBOSE はそれぞれ nil, false, true に設定されます。

### -x[directory] ###
メッセージ中のスクリプトを取り出して実行します。スクリプトを 読み込む時に、`#!'で始まり, "ruby"という文字列を含む行までを 読み飛ばします。スクリプトの終りはEOF(ファイル の終り), ^D(コントロールD), ^Z(コ ントロールZ)または予約語__END__で指定されます。

ディレクトリ名を指定すると、スクリプト実行前に指定されたディ レクトリに移動します。

### -y ###
### --yydebug ###
コンパイラデバッグモード。スクリプトを内部表現にコンパイルす る時の構文解析の過程を表示します。この表示は非常に冗長なので, コンパイラそのものをデバッグする人以外には必要ないと思います。

## インタプリタ行の解釈 ##

コマンドラインに指定したスクリプトが `#!' で始まるファイルで、そ の行に `ruby' という文字列を含まない場合、OSに代わって `#!' に続く文字列をコマンドラインとみなしてそのインタプリタを起 動します。このときコマンドラインで指定した引数はそのインタプリタに渡さ れます。

例えば、以下のシェルスクリプトを ruby で実行すると sh を起動します。

    #!/bin/sh -vx
    echo "$@"

この行に `ruby' という文字列が含まれる場合は、その文字列よ り左側は無視され、右側に `-'で始まる語があればオプションとして解 釈します。

ここで指定したオプションは、コマンドラインでの指定に追加されます。これ はそのスクリプトで指定すべきオプションを埋め込むために使います。例えば 以下の行で始まるスクリプトはコマンドラインに -Ke オプションを指 定したのと同じ効果になります。

    #! ruby -Ke
