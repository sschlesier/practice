---
title: "More JSON Tools"
weight: 20
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---
## Jo
#### Easily create valid json from a script

Simple key value
```bash
jo key=value key2="another value"
```
Outputs
```json
{"key":"value","key2":"another value"}
```

Embed calls to build up objects
```bash
jo -p key=$(jo foo=bar) 
```
Outputs
```json
{ "key": { "foo": "bar" } }
```

https://github.com/jpmens/jo

## Gron
#### Take json and output it as individual lines with a path to them for easy grep/sed etc, can also take lines and turn them back into json

jo key=value key2="another value" | gron json = {}; json.key = "value"; json.key2 = "another value";

https://github.com/tomnomnom/gron

JSON.sh - very much like gron but written in shell and with slightly different output formatting, not sure if it can rehydrate a json object

Jp - apply JMESPath to json

https://github.com/jmespath/jp

Jid - json interactive digger allows interactive building of queries to inspect json data

https://github.com/simeji/jid

Jmespath-terminal a repl for jmespath

https://github.com/jmespath/jmespath.terminal
