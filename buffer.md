# Terminology

```
Summary:
   A buffer is the in-memory text of a file.
   A window is a viewport on a buffer.
   A tab page is a collection of windows.

A window is a viewport onto a buffer.  You can use multiple windows on one
buffer, or several windows on different buffers.

A buffer is a file loaded into memory for editing.  The original file remains
unchanged until you write the buffer to the file.

```


ow to open new buffers and splits (or windows if you prefer).

Use :edit {file} (:e for short) to open file, {file}.

Use :split {file} (or :sp) to open file, {file}, in a new horizontal split

Use :vsplit {file} (or :vsp) to open file, {file}, in a new vertical split

Both :e and :sp use tab completion and globs to make your life easier (Use <c-d> to list completions)

Move between splits/windows via <c-w>j, <c-w>k, <c-w>h, <c-w>l

Use :q, :close, or <c-w>c to close a window

Use :qall or :qa to close all windows and quit Vim (be careful)

Use <c-w>_ to "maximize" a windows size and <c-w>= to make windows equal sizes

See :h CTRL-W to learn more window mappings

Use gf to go to the file under your cursor (See :h gf)

Now it is time for the main event, switching between buffers:

set hidden so you can freely switch between buffers without first saving the buffer

Use <c-^>/<c-6> to switch to the previous buffer. See :h CTRL-^ and :h alternate-file

Many people will suggest you learn :bnext and :bprevious to cycle between buffers, but "Why ride a bike when you can fly?"

Learn to use :b and :sb to switch buffers instead of cycling! (See :h :b)

Behold the power of :b!:

Uses <tab> completion

Use <c-d> to list out completion

Use partial file name. e.g. :b foo. Works great with <tab>.

Globbing. e.g. :b foo*bar or :b foo/**/bar

Split variant of :b is :sb.

Also accepts a buffer number

A common mapping: nnoremap <leader>b :ls<cr>:b<space>

Well that is great but just learning :b can't be all there is, right?

You are correct. Vim is a deep and complex subject that take some time to learn. It is best to learn Vim in small bite-size portions, make it a habit, then learn some more (This is sharpening the saw). The next topic should probably be to learn to use tags (see :h tags) and/or cscope (see :h cscope) which will help you jump between different files easily. You may also want to learn about :grep and :vimgrep (See :h :grep and :h :vimgrep) to learn how to search a code base. Include search and definition search commands also are a good set of tools to have in your toolbox (See :h include-search).

:b# means go to previous buffer for the current window.

