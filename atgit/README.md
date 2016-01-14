When in git repository, call the given command from git's root directory. Otherwise call it
unmodified.

## Why?

I often find myself browsing and changing some source code and then going back to Git top level
directory just to compile/run modified program. It's tedious and silly and should be made easier.
That's why I created this small script - it saves me the hassle of going back and forth in
directories tree.

## How?

You shouldn't run `atgit` file (it isn't even executable). Instead it should be added as a custom
function e.g. to your .bashrc, .zshrc, .bash-aliases or whatever is sourced by your shell. Simply do
something like `cat ./atgit >> ~/.bashrc`. This is preferred way because it exposes `atgit` as a
part of environment which in turn allows us to e.g. source files as well.

Usage examples:

    $ atgit make && atgit make install
    $ atgit source env*
    $ atgit "mkdir build && cd build && cmake .. && make -j2"
    $ VERBOSE=1 atgit g++ main.cpp -o hello-world

Changing directories is disabled by design as it's more unintuitive than actually useful. Use cd for
that!

Some basic autocompletion for commands (sudo style) can be found in `compl` directory.
