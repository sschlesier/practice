---
title: "httpie"
weight: 1
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---
https://httpie.io/docs

|Feature                 | Syntax                            |
|------------------------|-----------------------------------|
|Headers :               |Name:value                         |
|Query Params ==         |Name==value                        |
|Payload =               |Field=value                        |
|   =@                   |Field=@path-to-file.json           |
|Payload (non-string) := |Field:=1 Field:=["fee", "fi", "fo"]|
|Payload literal json :=@|Field:=@path-fo-file.json          |
|File upload @           |field@path-to-file.jpg             |
|  @ ;type=              |field@file.jpg;type=image/jpeg     |

--verbose for seeing everything
--follow -F to follow redirects
