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

### History Substitution

- Simplest substitution - replace in last command. Run as  ``^original^replacement`` Example:
```bash
$ git add file.txt
$ ^add^reset
git reset file.txt
```

## Resources
