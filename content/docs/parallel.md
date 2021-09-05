---
title: "parallel"
weight: 1
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---

## Easily execute commands per file

parallel execution of command on each txt file
```bash
parallel commmand {} ::: *.txt
```

Execute command a single instance at a time -j 1
```bash
parallel -j 1 commmand {} ::: *.txt
```

## File and path variations

### Insert filename with `{}`
```bash
parallel echo {} ::: **/*
```
outputs
```bash
a.txt
b.txt
subdir/c.txt
subdir/d.txt
```

### Strip extension by adding `.`
```bash
parallel echo {.} ::: **/*
```
outputs
```bash
a
b
subdir/c
subdir/d
```

### Strip path by adding `/`
```bash
parallel echo {/} ::: **/*
```
outputs
```bash
a.txt
b.txt
c.txt
d.txt
```

### Strip path and extension by adding `/.`
```bash
parallel echo {/.} ::: **/*
```
outputs
```bash
a
b
c
d
```

### Keep only path by adding `//`
```bash
parallel echo {//} ::: **/*
```
outputs
```bash
.
.
subdir
subdir
```
