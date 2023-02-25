# LINUX COMMANDS

Cheatsheet

https://files.fosswire.com/2007/08/fwunixref.pdf


ALIAS: only a shell feature
```
alias ll='ls -l'
#
alias ll='ls -l' >> .bashrc
```
ENV VARIABLE: inherited by all subprocesses
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

Print ========
```
for i in {1..10}; do echo -n =; done
```
Print =1=2=3=4=5=6=7=8=9=10
```
for i in {1..10}; do echo -n =$i; done
```


Calendar
```
sudo apt install ncal
cal
cal 2023
```


For loop:
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


Run multiple jobs (similar to PowerShell's Get-ChildItem ... | Foreach-Object -Parallel { ..... } -ThrottleLimit 10)
```
parallel --jobs 10 --progress < list_jobs.txt
#
parallel echo ::: 1 2 3 4 5
#
cat count_file.txt | parallel echo {}
# download multiple URLs
cat download_items.txt | parallel --jobs 5 wget {}
```

Find file and output full path
```
find ~+ -type f -name "*.py"
```


Find the word "import" inside all subdirectories with files with multiple extensions
```
find . -iname "*.txt" -o -iname "*.md" -o -iname "*.py" | xargs grep import --color=auto
```


List all attached drives
```
sudo lsblk -o NAME,FSTYPE,SIZE,MOUNTPOINT,LABEL
sudo lshw -C disk
sudo fdisk -l
```

format SSD at /dev/sdc
```
sudo mkfs -t ext4 /dev/sdc
```

Replace string in a text file
```
sed -i 's,string_to_find,string_to_replace,g' filename
```


Find a folder
```
find / -xdev 2>/dev/null -name "GeographicLib"
```

Count # files
```
ls -l *jpeg | wc -l
```

RM recursively delete folders or files by name
```
rm -rf `find -type d -name tmp*`
rm -rf `find -type f -name *.csv`
```


APT-GET update
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade
sudo apt-get autoremove
```

PIP upgrade version
```
sudo -H pip install --upgrade pip
```

CURL lets you use wildcards to specify the URLs you want to download
```
curl -L https://s3-us-west-1.amazonaws.com/udacity-robotics/Term+2+Resources/P3+Resources/models.tar.gz | tar zx -C ~/.gazebo/
```

WGET can be used recursively and can recover when a download fails
```
https://github.com/andrespgd/linux_pgd/edit/master/README.md
```

List all available HDDs/Partitions
```
sudo lsblk -o NAME,FSTYPE,SIZE,MOUNTPOINT,LABEL
```

GIT setup account
```
sudo apt-get update
sudo apt-get install git
git config --global user.name  "Your Name"
git config --global user.email "youremail@domain.com"
git config --list
```

BASH previous commands execution
```
CTRL-R   and   type nmap   and  start typing
ex.
CTRL-R  , type nmap, type git....
```

Find a word inside a file in a directory
```
grep -r word_on_file *
OR
grep -rnw -e 'word_on_file'
```

# UBUNTU

UBUNTU install notepad-plus-plus</br>
-set alias on .bashrc to npp

UBUNTU install nano text editor
```
sudo apt install nano
```

UBUNTU install screen recorder
```
sudo add-apt-repository ppa:fossproject/ppa
sudo apt update
sudo apt install green-recorder
```

UBUNTU Screenshot shortcuts (pre-installed)
```
Prt Scrn - desktop.
Alt+Prt Scrn - window.
Shift+Prt Scrn - area you select.
```

UBUNTU Nautilus File Manager:
* right-click on any white part of the window, click on "Open in Terminal"
* right-click on file/folder, copy, then on Terminal, right-click "paste as filenames" (similar to Path-Copy-Copy)
* drag file/folder to Terminal, and will show the path
* to get folder path, click on file/folder --> CTRL+L
