---
title: "parallel"
weight: 1
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---

Easily execute commands per file

parallel execution of command on each txt file
```bash
parallel commmand {} ::: *.txt
```

Execute command a single instance at a time -j 1
```bash
parallel -j 1 commmand {} ::: *.txt
```