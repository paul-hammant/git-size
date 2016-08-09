# Git sub-command for calculating the size of a repo/clone (history, ignored, checkout, etc)

This is a Bash command that, if in your path, will be part of the git command ecosystem

# Installation

1. Copy `git-size` to `/usr/local/bin/`
2. make it executable 'chmod +x /usr/local/bin/git-slim', if it wasn't already.

OR [via the Mac's homebrew](https://github.com/paul-hammant/homebrew-tap)

# Using git size

```
$ git clone git@github.com:git/git.git
# [...]
$ cd git
$ git size
git size:
  .git folder: 6.7M
  checkout:  29M
  ignored: 0B
  everything:  36M
```

If you'd done the clone with --no-checkout, the 29MB would have been saved, and the 36M would be closer to 6.7M.

If you ran a build, 0B would be replaced with a few megabytes, as all that stuff isn't to be checked in (it is ignored).

## CSV output

```
$ git clone git@github.com:git/git.git
# [...]
$ cd git
$ git size --csv
/scm/oss/git, 6812, 30176, 0, 36988
$ git size --csv --csv-headers
directory_name, dot_git_folder_size, checkout_size, ignored_size, everything_size
/scm/oss/git, 6812, 30176, 0, 36988
```

## help

```
$ git size --help
Usage:
  git size --csv --csv-header --kilobytes DIRNAME
  DIRNAME is optional - defaults to current directory
  --csv or -c: output as csv format
  --csv-header or -H: header row for CSV output
  --kilobytes or -k: kilobyte blocks instead of human units (always for CSV)
```

# LICENSE

Copyright (c) 2016 Paul Hammant

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

# Contribtions

Contributions welcome!
