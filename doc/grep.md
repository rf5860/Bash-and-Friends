# Grep

Grep is based on [Regular Expressions](http://en.wikipedia.org/wiki/Regular_expression). Don't be scared away by the occassionaly dense or theoretical texts!

## Regular Expressions

These pop up in a lot of programs. Eclipse, Notepad++, Vi, Emacs, Git, etc...

They're basically a way of matching texts that match some regular pattern.

### Examples

## Common Flags

|Flag|Usage|
|----|-----|
|colour|Colour the match under the specified condition|
|i|Insensitive|
|a|Treat binary files as text|
|I|Ignore binary files|
|v|Invert mtaches|
|r|Search directories recursively|
|m<N>|Stop after <N> matches|
|o|Show only the matching pattern|
|n|Output the line number|
|l|List files that match|
|L|List files that don't match|
|q|Quiet mode|
|C<N>|Show <N> lines of Context|
|A<N>|Show <N> lines after the match|
|B<N>|Show <N> lines before the match|

### Pattern Flags

|Flag|Usage|
|----|-----|
|E|Use Extended expression|
|P|Use Perl-Style Expression|
|G|Basic Expression|
|x|Require the whole line to match|

## Resources

- [Regular Expressions](http://www.regular-expressions.info/tutorial.html) - Great source of information.
- [Man Pages](http://linux.die.net/man/1/grep) - Always useful as a reference.
- [GNU Grep Manual](http://www.gnu.org/software/grep/manual/grep.html) - Like the man pages, but a little more verbose.
