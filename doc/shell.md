# Shell

## Hotkeys

There the basics:

- Up to go back through history
- Down to go forward through history

Sometimes though, the command you ran is quite a bit in the past, and it can be difficult to track it down. Fortunately, there's  shortcut to help us with that. In particular, Ctrl-r.

Example: Trying to find the last commmit command we typed, We could type ``Ctrl-rcommitCtrl-a``, then we can edit the command as necessary. Nifty!

Fun fact: Emacs inherited a lot of these keybinds.

Some useful shortcuts for moving around and editing around on the current line:

| Keystroke        | Action                                                 |
|------------------|--------------------------------------------------------|
| Ctrl-a           | Go to the start of the line                            |
| Ctrl-e           | Go to the end of the line                              |
| Ctrl-k           | Delete from the current position to the end of the line|
| Ctrl-u           | Delete from the current position to the end of the line|
| Ctrl-y           | Paste deleted contents                                 |
| Alt-.            | Last word pf the previous command                      |
| Alt-t            | Transpose words                                        |
| Alt-f            | Go forward a word                                      |
| Alt-b            | Go backward a word                                     |
| Alt-d            | Delete from the current position to the end of the word|
| Alt-[cul]        | Change case [Capitalize &#124; Upper &#124; Lower]     |

Useful shortcuts for modifying the state of the terminal:

| Keystroke| Action         |
|----------|----------------|
| Ctrl-l   |Clear the screen|


## Bash Profile

If you're using msysgit, you can create a file: ``~/<Username>/.bash_profile``. This file will get executed each term you start Git, so it's a convenient place to save things like Aliases and Functions.

## Aliases

Aliases provide a nice way of having shortcuts for frequently used commands. Suppose for example, you're tired of typing ``git add``, you could do:
```bash
$ alias ga='git add'
$ ga "Some files" # Just runs "git add some files" behind the scenes.
```

## File Navigation

## History

Most of the details here can be fund under [Event Designators](http://www.gnu.org/software/bash/manual/bashref.html#Event-Designators) in the reference manual.

You can view history by running the ``history`` command:

```bash
$ history|tail -3
  565  history
  566  history|tail
  567  history|tail -3
```

### History Substitution

- Simplest substitution - replace in last command. Run as  ``^original^replacement`` Example:
```bash
$ git add file.txt
$ ^add^reset
git reset file.txt
```

### History Expansion

- Run the last command with ``!!``.
- Run history item n with ``!n``.
- Run the nth last cmmand with ``!-n``.
- Run the last command starting with a particular string by typing ``!command`` - where command can be replaced with anything.
- Run a command containing a string, such as "stash" with ``!?stash?``


#### Accessing Arguments (Word Designators)

Details under [Word Designators](http://www.gnu.org/software/bash/manual/bashref.html#Word-Designators) in the Reference Document.

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

This isn't great if we want to access a range of arguments. Here's some ways to work with ranges:

```bash
# Create 3 files
$ touch a.txt b.txt c.txt d.txt e.txt
# Remove from the third file onwards.
$ rm !!:3*
rm c.txt d.txt e.txt
# Remove the first two arguments from two commands ago
$ rm !-2:1-2
rm a.txt b.txt
```

#### Modifiers

The final, powerful piece of the history expansion puzzle. Again, under the [Reference Document](http://www.gnu.org/software/bash/manual/bashref.html#Modifiers)

These are tacked onto the end of what we covered above, separated by colons (:).

The most common usage is global substituion.

```bash
$ echo "Some very foo sentence foo"
Some very foo sentence foo
$ !-1:gs/foo/bar/
echo "Some very bar sentence bar"
Some very bar sentence bar
```

## Shell Scripting

## Resources

- [Bash Reference Manual](http://www.gnu.org/software/bash/manual/bashref.html)
