# Files

Makefile.copyme - a makefile template to act as a "git pull" wrapper, such that
                  "make" is equivalent to "git pull && make".
bin/            - directory full of utilities which are useful for my workflow
bin/current-git-dir
                - Prints the full path to the current top of the repository
bin/current-git-branch
                - Quick and dirty current-branch printer
bin/pushto      - Use for maintaining multiple working directories, eg. code,
                  dev (alpha test), test. This helps greatly with separating
                  debugging efforts, and helps avoid embarrassing "it was in my
                  working dir" problems.
bin/resetto     - Reset a working directory, following the same rules as pushto.
                  This simplifies modifying the working directory in-place and
                  then cleaning it.
bin/split-file  - Copies a file, opens both for editing, tries to commit both.
									This is intended for when you're splitting code out of a file.
binary-search/  - Binary-search-related utilities

# Licence

Except where otherwise specified, all code within this directory and any subdirectories have copyright and licencing as described in the file COPYING.
