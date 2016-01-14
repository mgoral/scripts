When in git repository, call the given command ($@) from git's root directory. Otherwise call it
unmodified.

It's not to be run. Instead it should be added as a custom function e.g. to your .bashrc, .zshrc,
.bash-aliases or whatever. Simply do "cat ./atgit >> ~/.bashrc". This is preferred way because it
allows us to source files as well.

Usage examples:

    $ atgit make && atgit make install
    $ atgit source env*
    $ atgit "mkdir build && cd build && cmake .. && make -j2"

Changing directories is disabled by design as it's more unintuitive than actually useful. Use cd for
that!
