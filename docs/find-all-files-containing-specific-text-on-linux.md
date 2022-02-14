# Find all files containing specific text on Linux

```bash
  $ grep -rnw '/path/to/somewhere/' -e 'pattern'
```
  
  * -r or -R is recursive,
  * -n is line number, and
  * -w stands for match the whole word.
  * -l (lower-case L) can be added to just give the file name of matching files.
  * -e is the pattern used during the search

Along with these, --exclude, --include, --exclude-dir flags could be used for efficient searching.