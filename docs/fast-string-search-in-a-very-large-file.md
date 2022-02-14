# Fast string search in a very large file

To search a single pattern:

```bash
grep -F pattern large_file
```

To search a multiple patterns:

```bash
grep -F -f pattern_file large_file
```
