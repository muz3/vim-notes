# Vim registers: the basic and beyond
[ ref link ] (https://www.brianstorti.com/vim-registers/)

You can think of registers as a bunch of spaces in memory that vim uses to store some text. Each of these spaces have a identifier, so it can be accessed later.
It’s no different than when you copy some text to your clipboard, except that you usually have just one clipboard to copy to, while vim allows you to have multiple places to store different texts.



Never lose a yanked text again
It already happened to all of us. We yank some text, than delete some other, and when we try to paste the yanked text, it’s not there anymore, vim replaced it with the text that you deleted, then you need to go there and yanked that text again.
Well, as I said, vim will always replace the unnamed register, but of course we didn’t lose the yanked text, vim would not have survived that long if it was that dumb, right?

vim automatically populates what is called the numbered registers for us. As expected, these are registers from "0 to "9.
"0 will always have the content of the latest yank, and the others will have last 9 deleted text, being "1 the newest, and "9 the oldest. So if you yanked some text, you can always refer to it using "0p.


```bash
# to list all registers
:reg

# expression register
insert mode: crtl-r = system('ls')

# clipboard register in osx is either unamed or + register
# when yark something, it goes to clipboard register
:set clipboard=unamed


# ---------------------------------
# the unnamed register
The unnamed register
vim has a unnamed (or default) register that can be accessed with "". Any text that you delete (with d, c, s or x) or yank (with y) will be placed there, and that’s what vim uses to paste, when no explicit register is given. A simple p is the same thing as doing ""p.

Never lose a yanked text again
It already happened to all of us. We yank some text, than delete some other, and when we try to paste the yanked text, it’s not there anymore, vim replaced it with the text that you deleted, then you need to go there and yanked that text again.
Well, as I said, vim will always replace the unnamed register, but of course we didn’t lose the yanked text, vim would not have survived that long if it was that dumb, right?

vim automatically populates what is called the numbered registers for us. As expected, these are registers from "0 to "9.
"0 will always have the content of the latest yank, and the others will have last 9 deleted text, being "1 the newest, and "9 the oldest. So if you yanked some text, you can always refer to it using "0p.




# --------------------------
# search register
The search register, as you may have imagined, is where the latest text that you searched with /, ?, * or # is. If, for example, you just searched for /Nietzsche, and now you want to replace it with something else, there is no way you are going to type “Nietzsche” again, just do :%s/<Ctrl-r />/mustache/g and you are good to go.



```


