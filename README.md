<!-- title: jsstrip Read Me -->
<!-- $Id: README.md,v 1.7 2024-08-30 19:22:32-04 ron Exp $ -->

# jsstrip

jsstrip is a Python program that removes whitespace and comments from
a JavaScript source code file. It writes its output to standard output.
jsstrip often saves 30-40% of space in its input. jsstrip requires
Python 3.6 or later.

jsstrip can be convenient if you wish to distribute an HTML file with its
JavaScript source code in it on one or two lines surrounded by
\<script\>\</script\>.

With no flags jsstrip will convert a JavaScript file into two+ lines:
one+ will be a comment started on the first line; the other line will be
the entire JavaScript file minus unneeded whitespace and comments.

## Installation

Put jsstrip in your executable search path and change its mode to execute:
`chmod 755 jsstrip`. If you are using a system that doesn't understand
a script whose first line is
`#!/usr/bin/python3` then change the name from `jsstrip` to `jsstrip.py`.
Then execute it as `python3 jsstrip.py [args]`
or perhaps `py jsstrip.py [args]`.

## Help

```text
$ jsstrip --help
Usage: jsstrip [flags] [infile] [> outfile]

jsstrip removes white space and comments from javascript files.

IT ASSUMES LINES END WITH ";".  Use jslint (JavaScript Lint) to make sure.

With no 'infile' jsstrip reads from stdin.

By default, the first comment block is saved since it normally contains
author, copyright or licensing information.  Using "-f" overrides this.

jsstrip replaces each linefeed character in backtick-quoted strings with
a literal \n.

Flags:

  -h -? --help    Show this page
  -v --version    Show version/date/author/license info
  -c --copyright  Show jsstrip's copyright
  -f --first      Do not save first comment
  -w --white      Do not strip white space
  -s --single     Do not strip single line comments //
  -m --multi      Do not strip multi line comments /* ... */
  -q --quiet      Do not print statistics at end of run
  -d --debug      Print debugging messages
  -n --nop        Do not print/save result
```

## Examples

```sh
$ jsstrip myfile.js > myfileCompressed.js

$ jsstrip -dn myfile.js

c:\>python3 jsstrip.py myfile.js > myfileCompressed.js

c:\>python3 jsstrip.py -dn myfile.js
```

Ron Charlton
