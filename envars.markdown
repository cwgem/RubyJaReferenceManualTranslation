Environment Variables
=====================

The Ruby interpreter references the environment variables listed below.

RUBYOPT
--------
Indicates the default options to pass to the Ruby interpreter.

sh Version

    RUBYOPT='-Ke -rkconv'
    export RUBYOPT

csh Version

    setenv RUBYOPT '-Ke -rkconv'

MS-DOS Version

    set RUBYOPT=-Ke -rkconv

RUBYPATH
---------
When the -S option is specified, the directories indicated by this environment variable are added to the list of locations in PATH referenced to when searching for scripts. These directories have higher precedence over the PATH variable. For a full list of startup options, please consult [Ruby Execution](http://doc.ruby-lang.org/ja/1.9.2/doc/spec=2frubycmd.html).

sh Version

    RUBYPATH=$HOME/ruby:/opt/ruby
    export RUBYPATH

csh Version

    setenv RUBYPATH $HOME/ruby:/opt/ruby

MS-DOS Version

    set RUBYPATH=%HOME%\ruby:\opt\ruby

RUBYLIB
--------
The value of this environment variable is prepended to Ruby's default library search path, [$:](http://doc.ruby-lang.org/ja/1.9.2/method/Kernel/v/=3a.html).

sh Version

    RUBYLIB=$HOME/ruby/lib:/opt/ruby/lib
    export RUBYLIB

csh Version

    setenv RUBYLIB $HOME/ruby/lib:/opt/ruby/lib

MS-DOS Version

    set RUBYLIB=%HOME%\ruby\lib:\opt\ruby\lib

RUBYLIB_PREFIX
--------------
This is specific to the [DJGPP](http://doc.ruby-lang.org/ja/1.9.2/doc/platform=2fDJGPP.html), [Cygwin](http://doc.ruby-lang.org/ja/1.9.2/doc/platform=2fCygwin.html), [mswin32](http://doc.ruby-lang.org/ja/1.9.2/doc/platform=2fmswin32.html), and [mingw32](http://doc.ruby-lang.org/ja/1.9.2/doc/platform=2fmingw32.html) versions of Ruby.

The syntax for the value of this variable is `path1;path2` or `path1 path2`. When Ruby is searching the default library search path, [$:](http://doc.ruby-lang.org/ja/1.9.2/method/Kernel/v/=3a.html), it will replace paths whose prefix matches `path1` with `path2`. Note that it is unnecessary to set this variable when the prefix of the library path is relative to `ruby.exe` and `ruby.dll`.

MS-DOS Version

    set RUBYLIB_PREFIX=/usr/local/lib/ruby;d:/ruby

RUBYSHELL
---------
This is specific to the [OS2](http://doc.ruby-lang.org/ja/1.9.2/doc/platform=2fOS2.html), [mswin32](http://doc.ruby-lang.org/ja/1.9.2/doc/platform=2fmswin32.html), and [mingw32](http://doc.ruby-lang.org/ja/1.9.2/doc/platform=2fmingw32.html) versions of Ruby.

The value indicates which shell is to be used when running commands through the [Kernel.#system](http://doc.ruby-lang.org/ja/1.9.2/method/Kernel/m/system.html) method. If not set, the default is the value of `COMSPEC`.

PATH
----
Indicates the search path for commands called through the [Kernel.#system](http://doc.ruby-lang.org/ja/1.9.2/method/Kernel/m/system.html)  method. If not set (nil value), the default search path is `/usr/local/bin:/usr/ucb:/usr/bin:/bin:.`.