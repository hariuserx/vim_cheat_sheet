### Vim Complete Reference
visit [official page](http://vimdoc.sourceforge.net/htmldoc/)

### Vim Help
VIM offers extensive converage of help documentation. Access it with
`:help <anything thing. Need no be just a vim command>`

`:help help` Get help on using help :)

### Vim interpreter
Start Vim `vim`. Press `:` and then you have access to Vim interpreter

> Examples

* add two numbers

`:` -> `let a = 10 <Enter>` -> `let b = 20 <Enter>` -> `echo a + b` 

__Note:__ If we start vim using `vim` everytime we execute a command using `:` we have to re-enter `:` to execute the next command, to avoid that and to use a vim instance just completely in execution mode, launch vim with `vim -E` or `vim -e`. Check out `help -e` and `help Ex-mode` for more info

`vim -E` is really helpful while testing small snippets


### String concat Vim
This is done by dot `.`

> Example
```vimscript
let a = "World"
echo "Hello" . a

```

### echo Statements
This is done by `echo`. Use `echom` in case you want to save the messages in message-history which can be accessed via `:messages`. `echom` is really useful to put some debug statements in your vim files

### Convert to string
Often we can to convert int/float/list and others to string. Use `string()` for this purpose

### Folding
When the code gets huge, you might want to fold using {Visual}`zf`. Select a visual block and press `zf`. Use `set foldcolumn=1` to display a column which lists the folds. You can set it to a higher value to make multi level folds more intutive. Folds can be opened and closed using `zo` and `zc` respectively.

### Comparisions
See `help expr4` 

### Core commands

#### Start VIM
`gvim <file/folder/.>`

#### Exit
`:q`  -> Quit
`:q!` -> Quit ignoring changes
`:qa` -> Quit all windows
`:qa!`	-> Quit all windows ignoring changes

#### Write
All the Exit commands with `q` replaced by `w`

#### Tabs
`tabe` or `tabnew` : new tab buffer
`gt` or `Ctrl + Shift + PageDown` : switch tab forwards
`gT` or `Ctrl + Shift + PageUp` : switch tab backwards
`<tab-index-n>gt` : switch to n'th tab

#### Split Panes
`:vsplit` : vertical split, opens the same buffer
`:split` : horizontal split, opens the same buffer
`:new` : horizontal split, opens new buffer
`:vnew` : vertical split, opens new buffer
`Ctrl + w + Arrow keys` : Navigate between split panes
`Ctrl + w + <h/j/k/l>`  : Navigate between split panes left/up/down/right

#### File Explorer
People mostly use _nerdtree_ for this purpose but I find VIM's `:Explore` good enough. <br>
To open in a new vertical buffer use, `Vexplore`. By default vim explorer shows all the hidden files.

#### Typing Non-ASCII characters
>  Welcome Message<br>
>  autocmd VimEnter * echo "Welcome back \xcf\xa6\xce\x91\xc9\xbc\xca\x96"

Place this in your .vimrc file to display `Welcome back <hari in some utf-8 characters>`

#### Example vimrc file
An example .vimrc file is provided with the default VIM installation, 
We can use it by adding the beow line in your .vimrc file<br>

```vim
"use the example vimrc file"
source /usr/local/share/vim/vim81/vimrc_example.vim
``` 

I find it good enough to start with. But it bring along backup and undo files which are annoying.<br>
Add below lines to get rid of those.

```vim
"disable annyoing backup files"
set nobackup
set noundofile
```

#### VIM Modes
> Normal : press `<ESC>` key, default mode<br>
> Insert Mode: press "i"<br>
> Visual Mode: press "v"<br>

#### Locating you VIM installation directory, vimrc
`:echo $MYVIMRC`  -> vimrc file in use
`:echo $VIMRUNTIME`  ->  vim run time

#### List all loaded vim scripts
`:scriptnames`

#### Seeing recent messages
`:messages`
Here we can see all the messages history.<br>
While writing vim plugins and editing vimrrc, I find it very useful to output some debug statements.<br>
Using conventional `echo` won't save the messages for future use. Use `echom` for such purposes.

#### Custom VIM key mappings
See `:help map` for more info, Mostly we will need, visual, insert and normal mode mappings
<br>
Some Examples:

```vim
" Some short cuts. By default <leader> is mapped to "\"
" 'noremap' specifies non-recursive mapping. Better use it every where unless you want to really recurse and 'n' specifies mapping is for normal mode.
nnoremap <leader>ev :vsplit $MYVIMRC<cr>
nnoremap <leader>sv :source $MYVIMRC<cr>

" basic editing commands

" Copy current word under cursor
nnoremap <leader>cw viwy
" Paste in the current word under cursor
nnoremap <leader>pw viwpviwy
```

#### Vim Abbrevations
Extemely useful while typing long names
`:iabbrev chc chocolate`
In insert mode when ever we type chc followed by space, vim automatically replaces _chc_ with _chocolate_<br>
Note the chc must be a separate word. _achc_ won't get replaced with _achocolate_.

#### Vim auto complete
In insert mode press: `Ctrl + n`
Goes over all the words in all open buffers and list downs all near matches

