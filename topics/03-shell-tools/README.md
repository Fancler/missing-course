# Shell Tools

  - [MIT Page](https://missing.csail.mit.edu/2020/shell-tools/) (second half)
  - [GNU Parallel](https://www.gnu.org/software/parallel/)
  - [GNU Parallel Tutorial](https://www.usenix.org/system/files/login/articles/105438-Tange.pdf)

There exists a plethora of useful command line tools. We're going to take a look
at a few that are likely to be helpful as you work your way through school and
begin a career as a computer scientist or software developer.

## History

Remember that complicated command you used to do that complicated thing the
other day? Yeah, no one does. That's why we have `Ctrl-R`. This allows you to
easily find a command you've run in the past to (optionally) edit and run again.

  - [Example Video](https://youtu.be/Hj6Us07MTRM)

There is also a command called `history` that will simply print a list of your
past commands. This can be useful if you want to copy-paste commands into a
document or otherwise make use of your history in ways other than running a
single command.

## Navigate and Browse

  - [Tree](https://linux.die.net/man/1/tree)
  - [Autojump](https://github.com/wting/autojump)
  - [Fasd](https://github.com/clvv/fasd)

We already looked at `cd`, `ls`, and `pwd` for navigating the filesystem, but
there are a few other commands that can make life easier.

### Tree

This command, which will need to be installed on most systems (you can use
`brew install tree` on a Mac), prints a directory hierarchy as a pleasant ASCII
art diagram. For example, running it on this repository directory:

```
missing-course on  master [!]
➜ tree .
.
├── AUTHORS
├── LICENSE
├── Makefile
├── README.md
├── index.html
├── media
│   ├── header.html
│   ├── header.jpg
│   └── videos
│       └── ctrl-r-demo.mov
└── topics
    ├── 01-shell-overview
    │   ├── README.md
    │   └── index.html
    ├── 02-shell-scripting
    │   ├── README.md
    │   └── index.html
    ├── 03-shell-tools
    │   ├── README.md
    │   └── index.html
    ├── README.md
    └── index.html

6 directories, 16 files
```

### Stack Commands

The `pushd` and `popd` commands allow you to create a stack of directories so
that you can retrace your steps back to your starting position.

```
# Assume we start in the home directory
cd

# Time to work on some code
cd Code/awesome-project

# Go update the paper we're writing about this project
pushd ~/Documents/awesome-project-paper

# Jump back to the code without typing the directory again
popd
```

### Fasd and Autojump

## Grep and Friends

  - [The Silver Searcher](https://github.com/ggreer/the_silver_searcher)
  - [Ripgrep](https://github.com/BurntSushi/ripgrep)

Grep can find occurrences of a specific string or regular expression within
text files.

```
# Find "Missing" in the file README.md
grep Missing README.md`

# Find "command" in all files under the current directory, recursively
grep -r Missing .

# Only print filenames, not the line that matched
grep -lr command .

# Print some context around each match (2 lines)
grep -r -C2 command .

# Print filenames that did not match
grep -rL Missing .
```

### History Redux

Remember the `history` command? We can use a Unix pipe along with grep to find
all similar commands we've run in the past. For example, sometimes it is useful
to recall which packages have been installed through Homebrew. The following
command can find all invocations of `brew install`:

```
history | grep "brew install"
```

### Silver Searcher and Ripgrep

These tools act a lot like Grep, but provide better performance and other
features that make them more pleasant to use.

## Find



## Parallelize Commands


