---
title: "Bash History"
weight: 1
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---
`!$` - repeat last arg `echo fee fi fo fum` `echo !$` => `echo fum`

`!:n` - repeat nth arg `echo fee fi fo fum` `echo !:2` => `echo fi`

`!:n-$` - range of args (especially 1-$) `echo fee fi fo fum` `echo !:1-$` => `echo fee fi fo fum`

`!-m:$` - repeat last arg from the 2nd most recent command `echo fee fi fo fum` `ls echo !-2:$` => `echo fum`

`!$:h` - get parent folder of last arg `ls /etc/systemd/journald.conf` `ls !$:h` => `ls /etc/systemd`

`!#:n` - reference arg on current line `cp ./important_stuff !#:1.bak` => `cp ./important_stuff ./important_stuff.bak`

`!!:gs/find/replace` - global substitute on previous command
