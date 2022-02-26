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

Copy whole folder with files inside to anthoer folder (all in folder1 will be cloned to folder2)
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

## Show content inside a file
cat means concat content inside file to terminal
```
cat new-file.txt
```

list content of both files:
```
cat file-1.txt file-2.txt
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

## Show Manual of the terminal command
will list out manual for the 'ls' command:
```
man ls
```
Hit Ctrl+C to exit out of the long page

## Install/ upgrade/ remove packages
```
sudo apt-get install filezilla
sudo apt-get upgrade filezilla
sudo apt-get remove filezilla
```

## grant permission to run script
```
chmod u+x some_script.sh
```















