## C and C++

### Code Format and Style

Generally, the source code should obey the style documented
by [the configuration for clang-format](c-clang-format.yml).
It's aimed to follow [NetBSD KNF](http://cvsweb.netbsd.org/bsdweb.cgi/src/share/misc/style?rev=HEAD&content-type=text/x-cvsweb-markup) loosely.

However, there are a few exceptions.

* We don't change the style of the imported code.
  We try to keep local changes minimum.
  Ideally, no local changes.

* Notably, code imported from NuttX should obeys
  [NuttX Coding Standard](https://cwiki.apache.org/confluence/display/NUTTX/Coding+Standard).

### Tools

The `clang-format` tool from LLVM 13 with the above mentioned configuration
can be used to check and/or fix the style.

#### NuttX Coding Standard

The [nxstyle](https://github.com/apache/incubator-nuttx/blob/master/tools/nxstyle.c)
tool can be used to check the style.
