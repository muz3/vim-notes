# Runtimepath has ordering. 

```bash

#------------------syntax-------------------
# Enable customized syntax highlighting
# System defaults usually defined in $VIMRUNTIME/syntax
:E $VIMRUNTIME/syntax
# current file is sourced from $VIMRUNTIME/syntax/markdown.vim


# print current file path /usr/share/vim/vim81/syntax/syntax.vim
:echo @%

# in sytanx.vim, runtime syntax/synload.vim is the used.


# syntax enable vs syntax on, syntax on use default. enable can change color, so used to for overwrite
# highlight group 
:highlight Statement ctermfg=Red  # change foreground color

# example: .ssh/known_hosts file
:echo exists('g:syntax_on')
:high
:set iskeyword?
# setlocal iskeyword=@,48-57,_,192-255,$,-


# change buffer syntax is gone
:b#


#----------------filetype detection(ftdetect/)-------------

# match file, detect filetype by using filetype.vim
# to use autocommand with event type 'read a buffer with name xxx'
au BufNewFile,BufRead known_hosts setfiletype sshknownhosts

# This can be modified using :set path^= instead of :set path+=, which prepends the new directory to the beginning of the path instead of appending it to the end. 

#-------------------autoload---------------------
# gcp upload demo

# to check if python3 compiled, by type
:version
# run autoload script
:call gcp#Upload()

#------------------compiler---------------------
:bot term
:compiler java
# change path of current window
:lcd

# compiling typescript
#You can assign to the clipboard with the special + register:
:let @+ = expand('%:p')
:r ! pwd

# In these commands, % gives the name of the current file, %:p gives its full path, and %:p:h gives its directory (the "head" of the full path).
:lcd %:p:h

#Sometimes it is helpful if your working directory is always the same as the file you are editing. To achieve this, put the following in your vimrc:
:set autochdir
# That's it! Unfortunately, when this option is set some plugins may not work correctly if they make assumptions about the current directory. Sometimes, as an alternative to setting autochdir, the following command gives better results:
:autocmd BufEnter * silent! lcd %:p:h


# 
:args **/*.ts
# create ~/.vim/compiler/typescript.vim

# Automate Typescript compilation

#--------------------ftplugin-------------------
# sourcing file
:so ~/.vim/xxx
:filetype detect









``` 
