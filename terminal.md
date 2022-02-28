# Terminal Basics

To use terminal on windows, you can go to powershell (use as admin), then run 
```
wsl --install
```
to install the linux/ubuntu interface easily

## Current path
```
pwd
```

## Current user
```
whoami
```

## Check manual of command
```
man whoami -> will show how whoami works
```
Hit Ctrl+C to exit out of the long page

## List all files

List all files:
```
ls  
```

List all files in "folder1"
```
ls folder1
```

List files with info: allow you to know access of file (d:directory, r:read, w: write, x:execute)
```
ls -al
ls -l
ls -lh (human readable)
```

List all files including hidden files
```
ls -a
```

## Clear
```
clear
```
or Ctrl + L
 
## cd (Change Directory)
Go to specific file:
```
cd [file name/directory path]
cd test/directory [relative path]
cd /home/snowie [absolute path, starts with slash '/']
```

Go up by one folder:
```
cd ..
```

Go to previous path:
```
cd -
```

Back to home
```
cd
```

## Create new directory/ folder
```
mkdir new-folder
```

Other ways to use mkdir
```
mkdir folder1 folder2
mkdir folder1/innerfolder
mkdir -p folder1/innerfolder/innerinnerfolder   -> give permission to create all neccessary folder (default mkdir cannot)
```

## Create new file
```
touch index.html
```

## Copy file
Copy the text file into new-folder & named new-file-copy.txt:
```
cp new-file.txt new-folder/new-file-copy.txt
```

Copy whole folder with files inside to another folder (all in folder1 will be cloned to folder2)
```
cp -rv folder1 folder2
```

## Move file
Move file up by one folder:
```
mv new-file-copy.txt ../new-file-copy.txt
```

## 
file
Rename the file by giving it another name at the same directory:
```
mv new-file-copy.txt file-copy.txt
```

## Delete file
```
rm new-text-copy.txt
```

## Delete folder
-r : tell the terminal to remove everything inside the folder & also the folder itself (recursively)
```
rm -r new-folder
```

## Remove folder with result message
```
rm -v folder1 folder2  -> removed 'folder1', removed 'folder2'
```

## Edit File
Open new-file.txt with nano editor in terminal:
```
nano new-file.txt
```

Bottom will show relevant instructions
```
^x  =  Ctrl + 'X' -> exit 
^O  =  Ctrl + 'O' -> save
^W  =. Ctrl + 'W' -> search
```

## Expansion
```
*      -> all/ anything
*.??   -> ?? = 2 character extension
echo {a,b,c}    -> a b c
echo {1..5}     -> 1 2 3 4 5
touch main.{css,js}   -> main.css main.js
```

## gzip
zip the file using gzip
```
gzip -k largefile.txt -> output largefile.gz while keeping original file
```

unzip the file
```
gunzip largefile.gz
gzip -d largefile.gz
```

## tar 
take files into archive without file size compression, e.g.
output archive.tar which contains the three files
```
tar -cf archive.tar song1.txt song2.txt song3.txt
```

extract files from archive.tar
```
tar -xf archive.tar
```

tar & gzip at once
```
tar -czf bundle.tar.gz file1.txt file2.txt file3.txt
```

undo tar & zip at once
```
tar -xf bundle.tar.gz
```

## sudo
run command using the highest authority (root user)
```
sudo nano config.php
```

## chown
change owner of file/ folder, so that we can edit it
```
chown <owner> <file/folder>
sudo chown Elvis file1.txt
```

```
groups -> list groups who can read the files
```

## Permission
```
drwxr-xr-x
```
first character:   d:directory, -: regular file, c:character special file, l:symbolic link

next nine characters:
```
owner  group  world
rwx    rw-    r--
```
r:read     -- file can be listed (but cannot enter)
w:write    -- file can be modified
x:execute  -- file/directory can be entered or 'cd' into, script/program can be executed


## grant permission
chmod: change mode
```
chmod <mode> <file>
u: user (owner of file)
g: group
o: others (world)
a: all of the above
-: remove permission
+: grant permission
=: set a permission & remove others
r,w,x same as above
```

add read permission to everyone
```
chmod a+r file.txt
```

add write permission to the group
```
chmod g+w file.txt
```

everyone can only read
```
chmod a=r file.txt
```

grant user execute permission on script
```
chmod u+x some_script.sh
```

## chmod octals
base 8 representation of file permission
```
octal   binary   file mode
0       000      ---
1       001      --x
2       010      -w-
3       011      -wx
4       100      r--
5       101      r-x
6       110      rw-
7       111      rwx
```

allow owner to do all things, others can only read & execute the file/command
```
chmod 755 file.txt   ->   -rwxr-xr-x
```


## who
display the users logged into the system
```
who -> mary tony tom
```

## su
switch user
```
su elvis -> then login with his password & switched to elvis
```

## passwd
change password
```
passwd
passwd elvis
```

## Show content inside a file
cat means show content inside file to terminal
```
cat new-file.txt
```

list content of both files:
```
cat file-1.txt file-2.txt
```

put them inside a single file
```
cat file-1.txt file-2.txt > all.txt
```

## Redirect content operator

'>' put all the output the left-side into right-side file (but will overwrite original content in right-side file)
```
cat file-1.txt file-2.txt > combined-file.txt
ls > directory.txt
```

## Append content to the end of the file
word 'hi' will be appended to the end of the file
echo => prints content
'>>' => append to
```
echo hi >> combined-file.txt
```

## diff
```
diff file1.txt file2.txt      -> show difference between 2 files
diff -y file1.txt file2.txt   -> show diff side by side
```

## grep
find inside file that matches the word listed
```
grep green song.txt -> highlight the found keyword & display the content
```

## find
find all files with name containing 'project'
```
find . -name '*project*'
```

## history
show the history of commands runned before in terminal
```
history
!5      -> run the command again in line 5 of the command history
```

## wc
show word count, line count & byte count of file
```
wc file-1.txt
```

list the total word count, line count & byte count in current folder (| = pipe)
```
ls -l | wc
```

## xargs
pipe may not work sometimes when the target command needs to accept arguments,
this is when xargs can be used to pass the value as arguments into the commands
```
find . -size +1M | xargs ls -l
```

## Head & Tail
list first 10 lines or last 10 lines of file
```
head wow.txt
head wow.text -n 100 -> 100 lines
tail wow.txt
tail wow.text -n 100 -> 100 lines
```

## sort, uniq
sort content ascendin (ABC..)
```
sort file.txt
sort -n file.txt -> in number
sort -un file.text -> sort unqiue number
sort -u flavors.txt -> list unqiue line only
```

## Install/ upgrade/ remove packages
```
sudo apt-get install filezilla
sudo apt-get upgrade filezilla
sudo apt-get remove filezilla
```

## Date
show current time
```
date
```

## Process related commands
```
ps
bg 1&
top
kill 
killall
jobs
sleep
```














