Introduction
------------
This project is meant to provide a translation of the original Japanese Ruby Reference Manual. As Ruby is a programming language of Japanese origin, a good amount of authoritative material on the language is present in Japanese form. My hope is that by translating the documentation to English, it will help provide even more resources to the English speaking Ruby community.

Format
------

This project uses [Asciidoc](http://www.methods.co.nz/asciidoc/) and source highlighted is handled by the [Pygments](http://pygments.org/) backend. [Pygments' installation instructions](http://pygments.org/download/) contain information about how to obtain it. Once both Pygments and Asciidoc are installed, files can be output to HTML using the following command:

``asciidoc -a pygments= -b xhtml11 -o out/file.html file.txt``

Bugs
----

If you find issues with the translation, please file a bug at the [GitHub Issue Tracker](https://github.com/cwgem/RubyJaReferenceManualTranslation/issues  "GitHub Issue Tracker"). Alternatively you may fork the project and issue a pull request. Email is also an option (address listed below), but I prefer the previously mentioned methods to keep work centralized.

For the format of providing a fix, please use the files marked en/ja. They contain both the English translation and the original Japanese version. This allows me to see both side by side, so I can understand what the issue with the translation was.

License
--------

The contents are licensed under the same Creative Commons Attribution 3.0 Unported license that the original version was licensed under. Please see LICENSE for more detailed information.

Attribution
-----------

* Ruby Official Site http://www.ruby-lang.org/ja/
* Original Author: Yukihiro Matsumoto
* Translator: Chris White <cwprogram@live.com>
* Latest Version of Original Japanese Documentation: http://www.ruby-lang.org/ja/documentation/
