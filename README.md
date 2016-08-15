# Git sub-command for calculating the size of a repo/clone (history, ignored, checkout, etc)

This is a Bash command that, if in your path, will be part of the git command ecosystem

# Installation

Mac and Linux compatible.

1. Copy `git-size` to `/usr/local/bin/` or `/usr/bin/` as applicable
2. make it executable 'chmod +x /usr/local/bin/git-slim', if it wasn't already.

OR [via the Mac's homebrew](https://github.com/paul-hammant/homebrew-tap)

# Using git size

```
$ git clone git@github.com:git/git.git
# [...]
$ cd git
$ git size
/scm/oss/git: git size:
  .git folder: 6.7M
  checkout: 29.4M
  ignored: 0K
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
directory_name,dot_git_folder_size,checkout_size,ignored_size,everything_size
/scm/oss/git,6812,30176,0,36988
```

## help

```
$ git size --help
Usage (v1.0.6):
  git size --csv --csv-headers --kilobytes DIRNAME
  DIRNAME is optional - defaults to current directory
  --csv or -c: output as csv format (optional)
  --csv-headers or -H: header row for CSV output (optional)
  --sunburst or -s: generate hyperlink for sunburst visual (optional)
  --sunburst-html or -sh: generate HTML for sunburst visual (optional)
  --absolute-paths or -ap: show absolute paths rather than relative (optional)
  --recursive or -r: recurse looking for git clones/repos (always set for CSV output, optional)
  --kilobytes or -k: kilobyte blocks instead of human units (always set for CSV output, optional)
```

# LICENSE

Copyright (c) 2016 Paul Hammant

Also simplified BSD 2-clause licensed (see LICENSE)

# Contribtions

Contributions welcome via pull-request.
