### Vim Complete Reference
visit (official)[http://vimdoc.sourceforge.net/htmldoc/]

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
