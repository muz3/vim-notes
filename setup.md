# My Vim Journal

+ brew install tree

+
Type in Terminal: vim --version
as you want check the vim's version, then scroll down you will find something like; user vimrc file: "$HOME/.vimrc"

```bash
# ingore vimrc
# -N no compatible mode
# -u improved, vim default
# NORC no rc config; vim has predfined default. this is to enforce nothing loaded;
vi -Nu NORC demo.py


#---------------1. initializing a vimrc -------------------
# vimrc loading order
$VIMINIT         (environment variable)
$HOME/.vimrc
$HOME/.vim/vimrc (preferred)
$EXINIT
$HOME/.exrc
$VIMRUNTIME/defaults.vim


# enable file type
:set filetype?
:filetype plugin indent on
:filetype detect

# highlighting
:syntax on

# enable backspace
:set backspace=start, eol, indent


# open up a file/directory
:e filename Open filename for edition
# open last file
:e#
# open last file
Ctrl-^

:!mkdir ~/.vim/vimrc

# You edit "file-a" and make some changes. Then you flip to "file-b" using ":e fileb". Vim says you cannot; you have unsaved changes. Okay, so you ":w" and then flip. But then you return to "filea" and want to undo the earlier changes. Oops: lapsing into a dumb Vi from Unix, Vim says there aren't any changes to be undone. Vim throws away buffers by default when you switch out of them, unless "set :hidden" is turned on. Then it behaves like any other normal application with multiple buffers. The "filea" buffer will stick around and keep its undo history, marks and other state.
:set hidden

#-----------------2. runtimepath and formatting------------------
# run time path
:set rtp? # to see prints
let $RTP=split(&runtimepath, ',')[0]
# enviroment variable to get to vimrc file
let $RC="$HOME/.vim/vimrc"


# go back to the first file of buffer list; first file of arugment list
:first

# set/list special char
:set list


# command line mode
to press ctrl-f


# python indention
:set shiftwidth=4 tabstop=4 softtabstop=4 expandtab autoindent smartindent

# color column boundary
:setcolor colorcolumn=80

:set list!


# search order:   only 1 and 5 to consider; 2 and 4 is shared folder; 3 system runtime
1. User Home .vim
2. Sysadmin folder
3. $VIMRUNTIME // system vim run time
4. Sysadmin "after" holder
5. User Home "after" folder


#-----------------------------------------------
## 3. FIX YOUR PATH
# insearch and highlight search
:set incsearch
:set hls
:nohl
# inspect for right path
:set path?
# . means current file; /usr/include current system vim run time located default; empty means current working directory
output: path=.,/usr/include,,
# for small project, can have a performance issue
# including all sub directories downwards
:set path=.,**
#Swap files store changes you've made to the buffer. If Vim or your computer crashes, they allow you to recover those changes. Swap files also provide a way to avoid multiple instances of Vim from editing the same file.
:noswapfile

#python.vim
setlocal path=.,**, tests, bin/**
# like gitignore
setlocal wildignore=*/__pycache__/*,*.pyc



#-----------------------------------------------
#4. include-search
## vim range copy, better than ctrl-o and paste
:?sub?t.





```
