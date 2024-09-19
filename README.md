<!-- title: jsstrip Read Me -->
<!-- $Id: README.md,v 1.13 2024-09-19 09:11:29-04 ron Exp $ -->

# jsstrip

jsstrip is a Python script that removes whitespace and comments from
a JavaScript source code file. It writes its output to standard output.
jsstrip often reduces the size of its input by 30-40%, reducing script
download time by the same amount. jsstrip requires Python 3.6 or later.

jsstrip can be convenient if you wish to distribute an HTML file with its
JavaScript source code within it on one or two lines surrounded by
<br>`<script>`<br>`</script>`

With no flags jsstrip will convert a JavaScript file into two lines:
one (or more) will be a comment block started on the first line
of the JavaScript file; the other line will be the entire JavaScript file
without comments and unneeded whitespace.

## Installation

Put jsstrip in your executable search path and change its mode to execute:
`chmod 755 jsstrip`. If you are using a system that won't run
a script whose first line is `#!/usr/bin/python3`, change the name
from `jsstrip` to `jsstrip.py`.
Then run it as `python3 jsstrip.py [args]` or perhaps
`py jsstrip.py [args]`.

## Help

```text
$ jsstrip --help
Usage: jsstrip [flags] [infile] [> outfile]

jsstrip removes white space and comments from a javascript file.

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

```bash
$ jsstrip myfile.js > myfileCompressed.js

$ jsstrip -dn myfile.js
```

```
c:\>python3 jsstrip.py myfile.js > myfileCompressed.js

c:\>python3 jsstrip.py -dn myfile.js
```

Ron Charlton
