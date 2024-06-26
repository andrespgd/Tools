# LINUX COMMANDS

## Cheatsheet

https://files.fosswire.com/2007/08/fwunixref.pdf

## TERMINAL copy/paste


CTRL+SHIFT+C
CTRL+SHIFT+V


## COPY/PASTE Clipboard (copyq)
```
sudo apt install copyq
```


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
```
# W/OUT
command1 & command2 & command3 
# With
parallel ::: 'command1' 'command2'
# Using a file with commands
parallel --jobs 10 --progress < list_commands.txt
# Example
parallel echo ::: 1 2 3 4 
# Example
cat count_file.txt | parallel echo {}
# Example download multiple URLs
cat download_items.txt | parallel --jobs 5 wget {}
```

## Find
### output full path
```
find ~+ -type f -name "*.py"
```
### output full path w/xargs
```
find -type f -name "*.py" | xargs readlink -e
```
### Find the word "import" inside certain file types and print line number
```
find . -iname "*.txt" -o -iname "*.md" -o -iname "*.py" | xargs grep import --color=auto -n
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
# List all available HDDs/Partitions
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
## Watch command
```
watch 'ls -ls *jpeg | wc -l'
```
## Delete
recursively delete by type/keywords
```
rm -rf `find -type d -name tmp*`
rm -rf `find -type f -name *.csv`
```

## CURL 
lets you use wildcards to specify the URLs you want to download
```
curl -L https://s3-us-west-1.amazonaws.com/udacity-robotics/Term+2+Resources/P3+Resources/models.tar.gz | tar zx -C ~/.gazebo/
```

## WGET 
can be used recursively and can recover when a download fails
```
wget https://github.com/andrespgd/linux_pgd/edit/master/README.md
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

### Find out distribution/version
```
lsb_release -a
```

# UBUNTU Installs

## APT-GET update
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade
sudo apt-get autoremove
```

## Enable SSH
```
sudo apt update
sudo apt install openssh-server
#
sudo systemctl status ssh  # will show ssh.service # press q to get back to command
#
sudo ufw allow ssh
```

## Enable X11 Forwarding
On **server**, go to /etc/ssh/sshd_config
* X11 Forwarding yes
* restart sshd if needed
```
sudo service sshd restart
```
On **client**
```
ssh -X user@xxx.xxx.xxx.xxx
gedit #test
```

## Enable XDRP (install Remmina to RDP from Windows and Linux)
```
# should start by default
sudo apt install xdrp    
sudo apt install xfce4 xfce4-goodies -y
sudo apt install xfce4 xfce4-goodies -y
# check status
sudo systemctl status xrdp
# if not runnning
sudo systemctl start xrdp
```
To have a typical Ubuntu Desktop environment:
Create ~/.xsessionrc
```
export DESKTOP_SESSION=ubuntu
export GNOME_SHELL_SESSION_MODE=ubuntu
export XDG_CURRENT_DESKTOP=ubuntu:GNOME
```

## Remmina
```
-from Windows, use RDP to connect
-if after login , black screen, logout off Linux computer physically
- how to fix color profile pop-up windows 20-04-20-10/
https://devanswers.co/how-to-fix-authentication-is-required-to-create-a-color-profile-managed-device-on-ubuntu-
```

## Utilities
```
# gcc and g++
sudo apt install build-essential
#
sudo snap install notepad-plus-plus
alias npp="notepad-plus-plus" >> .bashrc
#
sudo apt install nano
#
sudo apt install htop
#
sudo add-apt-repository ppa:fossproject/ppa
sudo apt update
sudo apt install green-recorder
#
sudo apt install neofetch
# 
sudo apt install speedtest-cli
```

## Speed Test
```
speedtest-cli --simple
```

## NVIDIA driver
### Find out what graphics card is installed
lshw -class display
### Go to NVIDIA driver and find the driver #
Example 525.92
### Go to NVIDIA Xfree and download the .run file for that version
https://download.nvidia.com/XFree86/Linux-x86_64/
```
wget xxxxxxxxxxxxxxxxxx.run
chmod 755 .run
./xxxxxxxxxxxxxxx.run
```
OR</br>
Install it on the Software Window in Ubuntu (may require to create a temp password to be enter in AMOK on bootup)</br>
Check that is working correctly by:
```
nvidia-smi
```

## NVIDIA Cuda
```
sudo apt install nvidia-cuda-toolkit
```


## Screenshot shortcuts (pre-installed)
```
Prt Scrn - desktop.
Alt+Prt Scrn - window.
Shift+Prt Scrn - area you select.
```



## Nautilus File Manager:
* right-click on any white part of the window, click on "Open in Terminal"
* right-click on file/folder, copy, then on Terminal, right-click "paste as filenames" (similar to Path-Copy-Copy)
* drag file/folder to Terminal, and will show the path
* to get folder path, click on file/folder --> CTRL+L

## Battery Status
```
upower -i /org/freedesktop/UPower/devices/battery_BAT0
```

## Resize .JPG batch mode
```
sudo apt install imagemagick
convert <INPUT_FILE> -quality 10% <OUTPUT_FILE>
for file in *.jpg; do convert $file -quality 10% "resized_"$file ; done
```
