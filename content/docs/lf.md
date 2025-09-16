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

### Command Line
- `:` - Enter command mode
- `$` - Execute shell command
- `!` - Execute shell command and wait
- `%` - Execute shell command with piped output
- `&` - Execute shell command asynchronously

### Search & Find
- `/` - Search forward
- `?` - Search backward
- `n/N` - Next/previous search result
- `f/F` - Find character forward/backward
- `;/,` - Next/previous find result

### Other
- `q` - Quit
- `Ctrl+l` - Redraw screen
- `Ctrl+r` - Reload current directory
