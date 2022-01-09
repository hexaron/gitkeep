# Gitkeep

Gitkeep is a tool for tracking empty directories with git.

It adds .gitkeep files to empty directories, which results in the directory
no longer being empty.
Note that .gitkeep is not special in the way .gitignore is.
The only thing that is important is that the directory contains _any_ file.

Gitkeep also removes unnecessary .gitkeep files, when there are other files
witnessing that the directory is indeed not empty.

## Usage

Running
```
path/to/gitkeep
```
adds and removes .gitkeep files in the current working directory according to
the above description.

The general usage (assuming gitkeep is in `$PATH`) is
```
 $ gitkeep --help

Automatically add and remove .gitkeep files for tracking empty directories with
git.

Usage: gitkeep [OPTIONS] [DIRECTORY]

Notes:
By default DIRECTORY is the current working directory.
Directories ignored by git wont be checked. In particular ".gitkeep" files in
ignored directories wont be deleted. (The only exception is, when DIRECTORY is
explicitly set to be an ignored directory containing an unnecessary ".gitkeep"
file.)

Options:
  --debug      Print python stack trace on error.
  -d, --dry    Run in dry mode, i.e. only print the changes instead of
               performing them.
  -f, --force  Run the script even on possibly large directories.
  -h, --help   Display this help message.
```
