---
title: "parallel"
weight: 1
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---

A nice [overview](https://blog.ronin.cloud/gnu-parallel/)

## Easily execute commands per file

parallel execution of command on each txt file
```bash
parallel commmand {} ::: *.txt
```

Track slot number `%` and job number `#`
```bash
parallel echo {%} {#} {} ::: *.txt
```
outputs
```bash
1 1 foo.txt
2 2 fee.txt
1 3 fi.txt
2 4 fum.txt
```

Manage max slots with `-j`

Slots default to the number of available processors
```bash
parallel -j 1 echo {} ::: *.txt
```
outputs
```bash
1 1 foo.txt
1 2 fee.txt
1 3 fi.txt
1 4 fum.txt
```

Check for correctness using `--dryrun`
```bash
parallel --dryrun echo {} ::: *.txt
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
