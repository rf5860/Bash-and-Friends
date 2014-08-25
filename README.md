# Grep

## Common Flags

# Sed

## Common Flags

## Resources

# Awk

## Idiomatic Awk

## Resources

# Shell

## Hotkeys

## History

You can view history by running the ``history`` command:

```bash
$ history|tail -3
  565  history
  566  history|tail
  567  history|tail -3
```

### History Expansion

- Run the last command with ``!!``.
- Run history item n with ``!n``.
- Run the nth last cmmand with ``!-n``.
- Run the last command starting with a particular string by typing ``!command`` - where command can be replaced with anything.
- Run a command containing a string, such as "stash" with ``!?stash?``


#### Accessing Arguments

Building on the above, colons (:) can be used to select a word in the command. 0 is the initial command, and subsequent words are selected by increasing the number.

```bash
$ ls ./
0.stashed  1.stashed  2.stashed  3.stashed  4.stashed  5.stashed  6.stashed  7.stashed  README.txt  test
$ !!:0
ls
0.stashed  1.stashed  2.stashed  3.stashed  4.stashed  5.stashed  6.stashed  7.stashed  README.txt  test
```

- A useful shortcut for accessing the first argument: ``^``
- A useful shortcut for accessing the last argument: ``$``

Example:

```bash
$ touch a.txt b.txt
$ rm !^
rm a.txt
$ rm !-2:$
rm b.txt
```

### History Substitution

- Simplest substitution - replace in last command. Run as  ``^original^replacement`` Example:
```bash
$ git add file.txt
$ ^add^reset
git reset file.txt
```

## Resources
