# yavdb

This is a generic Vim <-> Debugger Interface Tool designed to be adaptable to any debugger application. 

## Supported debuggers

Currently supported debuggers:

- jdb: [java debugger](https://docs.oracle.com/javase/7/docs/technotes/tools/windows/jdb.html)
- gdb: [gnu debugger](http://www.gnu.org/software/gdb/)

## Background

This fork comes from [vim-scripts/yavdb](http://www.vim.org/scripts/script.php?script_id=1954)

## Requirements:

- VIM compiled with Signs, Client-Server, and Python support.
- Python 2.5
- An operating system with support for named pipes

## Use

Is needed to launch yavdb from command line

    yavdb [-s servername] [-t type] <debugger command line>

Options:

- `-s` specifies the Vim servername. If no VIM (or GVIM) window exists with this servername, a new GVIM window will be opened. If not specified, the servername 'VimDebugger' will be used. If multiple applications are being debugged simultaneously unique servernames must be used.

- `-t` can be used to override the debugger type. If this option is omitted the debugger name will be used as the type. Currently supported debugger types include 'gdb' and 'jdb'. Note that jdb will only correctly notify VIM of events when classnames are identical to filenames (other than the .java extension).

## Key mapping

Vim will have the following key mappings set:

<C-F5> Run Application
<F5> Continue Execution
<F7> Step Into a Function
<F8> Next Instruction
<F9> Set Breakpoint
<F10> Print variable value under cursor

