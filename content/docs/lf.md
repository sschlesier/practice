# lf - file manager

### File Operations
- `d` - Cut (for moving files)
- `y` - Copy (yank)
- `p` - Paste (move/copy files from buffer)
- `c` - Clear cut/copy buffer
- `space` - Toggle selection of current file
- `v` - Invert selection (select all unselected)
- `u` - Unselect all files

### View Options
- `zh` - Toggle hidden files
- `zr` - Toggle reverse sort
- `zn/zs/zt` - Toggle info display (none/size/time)

### File Management
- `r` - Rename current file
- No default delete mapping (for safety - you need to define your own)
- `l` or `→` - Open file/enter directory
- `o` - Open with system default (custom mapping)

### Delete Files (no new mappings)
- Use `space` to select one or more files (or leave on current file for single delete)
- `:` then `delete` to remove selected/current files (lf will prompt for confirmation)

### Command Line
- `:` - Enter command mode (lf built-in commands)

### Shell Modes
| Key | Mode | Terminal | Blocks lf? | Use for |
|-----|------|----------|------------|---------|
| `$` | shell | Takes over terminal | Yes, until command exits | Interactive commands, editors, anything with UI |
| `!` | shell-wait | Takes over terminal, then shows "press any key" | Yes | Commands whose output you need to read before returning |
| `%` | shell-pipe | Inline at bottom of lf | Yes | Quick one-liners where you want to stay in lf (`du -sh $fx`) |
| `&` | shell-async | None (detached) | No | Background tasks, opening GUI apps |

All four modes export `$f`, `$fs`, and `$fx` (see below).

### Selected Files in Shell Commands
When you run a shell command (`$`, `%`, `!`, or `&`), lf exports these variables:

| Variable | Description |
|----------|-------------|
| `$f` | Current file (under cursor), full path |
| `$fs` | All selected files, newline-separated |
| `$fx` | Selected files if any, otherwise falls back to `$f` |

`$fx` is the most useful — it always does the right thing whether or not you have a selection.

**Quick workflow:** select files with `space`, press `$` (or `%`/`!`/`&`), use `$fx` in your command:
```sh
# show sizes of selected files
du -sh $fx

# iterate over selections (handles spaces in filenames)
IFS='
'
for f in $fx; do
    echo "Processing: $f"
done
```

### Search & Find
- `/` - Search forward
- `?` - Search backward
- `n/N` - Next/previous search result
- `f/F` - Find character forward/backward
- `;/,` - Next/previous find result

### Other
- `q` - Quit
- `Q` - Quit and cd
- `Ctrl+l` - Redraw screen
- `Ctrl+r` - Reload current directory
