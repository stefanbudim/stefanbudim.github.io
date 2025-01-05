---
title: "Linux: find"
categories: [linux, find]
tags: [linux]     # TAG names should always be lowercase
---

Useful find commands.

## -print and -delete
Step 1: Show matched files (to ensure regex works as intended, -print is default and not needed)
Step 2: Delete by appending '-delete'
```bash
find dir1 -type f -path "*/in/a_*b.log" -print
find dir1 -type f -path "*/in/a_*b.log" -delete
```

## Date and Time

### Find files newer than DATE. Find Files NOT newer than DATE
```bash
find ~ -type f -newermt "2024-12-20"
find ~ -type f -newermt "2024-12-01 00:00:00"

find ~ -type f ! -newermt "2024-12-20"
```

### Sort files by modified timestamp

```bash
find . -type f -printf "%T+ %p\n" | sort -r
```

find the 10 most recently modified files
```bash
find ~ -type f -printf "%T+ %p\n" | sort -r | head -n 10
```


## Regex

### Basic Regex
```bash
find ~ -name "*ekyll*
NOK: find ~/pj/obsidian-vault  -name ".*ekyll.*"
```

```bash
find . -regex '\./[a-f0-9\-]\{36\}\.jpg'
```
The -regex option matches the entire path, not just the file or directory name. If you want to match only the name part, you can use -name with shell globbing or narrow the regex to consider just the filename.



### Regex in Path

```bash
find dir1 -type f -path "*/in/a_*b.log"
```
The find command does not interpret wildcards (`*`) within a file path in the same way as a shell would. If you want to search for files matching the pattern a_*b.log within subdirectories under dir1, you need to let find handle the directory traversal.






### Switch Regex Type
To see which regular expression types are known, use -regextype help.

switch to egrep expressions by `-regextype posix-egrep`:
```bash
find . -regextype posix-egrep -regex '\./[a-f0-9\-]{36}\.jpg'
```

```bash
 find . -regextype sed -regex ".*/[a-f0-9\-]\{36\}\.jpg"
```

`-E` uses extended regex support
```bash
find -E . -regex ".*/[a-f0-9\-]{36}.jpg"
```

