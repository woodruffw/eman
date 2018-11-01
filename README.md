eman
====

Utilities for embedded manpages.

## Why?

I've never liked the fact that programs and their manpages used separate files &mdash; it adds an
additional file to worry about when installing software, and another thing to edit when bumping
a program's version.

So, I wrote some scripts for embedding manpages in custom ELF sections, plus extracting
those sections for viewing in `man`. It might also work with non-ELF binaries, although I haven't
tried those.

## Usage

You shouldn't use this, it's just an experiment. But, if you'd like to play with it:

```bash
# embed a manpage into a binary.
# compression is ignored; any and all contents are inserted into the .manpage section.
$ eman-embed /bin/bash /usr/share/man/man1/bash.1.gz ~/mybash

# view the .manpage section
$ eman ~/mybash

# gracefully fall back to normal `man`
$ eman bash

# section numbers also work
$ eman 2 read
```
