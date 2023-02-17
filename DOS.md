
Format command by adding the /P parameter. This new parameter allows you to overwrite every sector on a disk with 0's during the format procedure:
```
Format volume /P:passes
```
The /P parameter allows you to specify the number of passes or # overwrites every sector with 0's.
```
Format D: /P:4
```




Compare 2 files:
```
FC file1 file2
```
Compare 2 binary files:
```
FC /B file1 file2
```

To find out where an executable is:
```
where executable.exe
```

Concatenate text files into a single file:
```
copy /b *.txt newfile.txt
```
To add a newLine at the end of each concatenated file, use type instead of copy, as follows:
```
type *.txt > newfile.txt
```
For a few text files, the copy command can be used to append them together:
```
copy file1+file2+file3 targetfile
```
For binary files, add in the '/b' option:
```
copy /b file1+file2+file3 targetfile
```
