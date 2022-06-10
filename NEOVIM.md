```
sudo apt install neovim
```

3modes:
* insert (SHIFT+I)
* command (ESC) (to exit SHIFT+I or A)
* visual (ESC, then V)
(for column edit mode, need to be in command mode already)

delete a line: ESC and DD

To use the mouse:
* :set mouse=a
* the 'a' means all vim modes:
* visual, normal, insert, command line

To edit a column in VISUAL mode:
* in command mode(ESC)
* go to where you want to start
* CTRL+V
* highlight column
* SHIFT+i (goes to insert mode)
* type what you want
* ESC (will show changes to all columns)

:wq
* to save

find
* ESC
* /word_to_find (ENTER)

find/replace (S)ubstitute
* ESC
* : s/cat/dog (first occurence)
* : %s/cat/dog   (one by one)
* : %s/cat/dog/g   (all at once)
* : %s/cat/dog/gc   (will ask y or Y)


To copy or cut and paste:
* go to where you want to highlight
* ESC (command)
* V (visual)
* Y(yank or copy) OR D (cut)
* go to where you want to paste
* P (paste)

