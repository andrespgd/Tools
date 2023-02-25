# LINUX COMMANDS

## Cheatsheet

https://files.fosswire.com/2007/08/fwunixref.pdf


## ALIAS: only a shell feature
```
alias ll='ls -l'
#
alias ll='ls -l' >> .bashrc
```

## ENV VARIABLE: inherited by all subprocesses
```
color='blue'
echo $color
#
export FAV_COLOR='cyan'
echo $FAV_COLOR
#
export FAV_COLOR_FOR_SHELL='green' >> .bashrc
```

Print at variable to screen
```
echo $USER
```

Print all system variables
```
env
```

## FOR LOOP Print ========
```
for i in {1..10}; do echo -$i =; done
```
Print =1=2=3=4=5=6=7=8=9=10
```
for i in {1..10}; do echo -n =$i; done
```
Process files
```
for f in *.jpeg; do echo "Processing $f file.."; done
```
OR
```
for f in file1 file2 file3 file4
do
 echo "Processing $f"
 # do something on $f
done
```


## Calendar
```
sudo apt install ncal
cal
cal 2023
```

## Parallel
W/OUT
```
command1 & command2 & command3 
```
With
```
parallel ::: 'command1' 'command2'
```
Using a file with commands
```
parallel --jobs 10 --progress < list_commands.txt
```
Example
```
parallel echo ::: 1 2 3 4 
```
Example
```
cat count_file.txt | parallel echo {}
```
Example download multiple URLs
```
cat download_items.txt | parallel --jobs 5 wget {}
```

## Find
output full path
```
find ~+ -type f -name "*.py"
```
Find the word "import" inside all subdirectories with files with multiple extensions
```
find . -iname "*.txt" -o -iname "*.md" -o -iname "*.py" | xargs grep import --color=auto
```
Find a folder
```
find / -xdev 2>/dev/null -name "GeographicLib"
``````

## GREP
Find a word inside a file in a directory
```
grep -r word_on_file *
OR
grep -rnw -e 'word_on_file'
```



## List hardware
```
sudo lsblk -o NAME,FSTYPE,SIZE,MOUNTPOINT,LABEL
sudo lshw -C disk
sudo fdisk -l
```
List all available HDDs/Partitions
```
sudo lsblk -o NAME,FSTYPE,SIZE,MOUNTPOINT,LABEL
```


## Format SSD at /dev/sdc
```
sudo mkfs -t ext4 /dev/sdc
```

## Replace string
```
sed -i 's,string_to_find,string_to_replace,g' filename
```

## Count # files
```
ls -l *jpeg | wc -l
```

## Detele
RM recursively delete folders or files by name
```
rm -rf `find -type d -name tmp*`
rm -rf `find -type f -name *.csv`
```


## APT-GET update
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade
sudo apt-get autoremove
```

## PIP upgrade version
```
sudo -H pip install --upgrade pip
```

## CURL 
lets you use wildcards to specify the URLs you want to download
```
curl -L https://s3-us-west-1.amazonaws.com/udacity-robotics/Term+2+Resources/P3+Resources/models.tar.gz | tar zx -C ~/.gazebo/
```

## WGET 
can be used recursively and can recover when a download fails
```
https://github.com/andrespgd/linux_pgd/edit/master/README.md
```


## GIT setup account
```
sudo apt-get update
sudo apt-get install git
git config --global user.name  "Your Name"
git config --global user.email "youremail@domain.com"
git config --list
```

## BASH previous commands execution
```
CTRL-R   and   type nmap   and  start typing
ex.
CTRL-R  , type nmap, type git....
```


# UBUNTU Installs


## Screenshot shortcuts (pre-installed)
```
Prt Scrn - desktop.
Alt+Prt Scrn - window.
Shift+Prt Scrn - area you select.
```

## notepad-plus-plus
-set alias on .bashrc to npp

## Nano
```
sudo apt install nano
```

## Screen recorder
```
sudo add-apt-repository ppa:fossproject/ppa
sudo apt update
sudo apt install green-recorder
```


## Nautilus File Manager:
* right-click on any white part of the window, click on "Open in Terminal"
* right-click on file/folder, copy, then on Terminal, right-click "paste as filenames" (similar to Path-Copy-Copy)
* drag file/folder to Terminal, and will show the path
* to get folder path, click on file/folder --> CTRL+L
