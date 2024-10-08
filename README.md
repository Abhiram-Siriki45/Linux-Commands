<img src="https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/09331f04-27c3-4751-bd77-9cf8507091d7/dhsuidg-8293208d-6896-42da-9f13-e55e7bfcca86.gif?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7InBhdGgiOiJcL2ZcLzA5MzMxZjA0LTI3YzMtNDc1MS1iZDc3LTljZjg1MDcwOTFkN1wvZGhzdWlkZy04MjkzMjA4ZC02ODk2LTQyZGEtOWYxMy1lNTVlN2JmY2NhODYuZ2lmIn1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmZpbGUuZG93bmxvYWQiXX0.6Vl3W5CXv4d_Pj99tgNDp8YHFHx3-EZTTld3GHlVkqU" 
 width="50px"></a> 
 # LINUX COMMANDS🐧


## 👇DIRECTORY

    sudo - super user do
---
    pwd --> displays present working directory
---
    mkdir (directory name)  --> This command create a directory
---
    cd (directory/folder where you want to navigate) -->This command change directory.
---
    ls --> lists contents of current directory
---
    ls -l --> list contents of current directory with detailed output
---
    ll --> list contents of current directory with detailed output
---
    cd <folder>
---
    cd .. --> to come out of a directory
---
    rm -r testdir --> to remove a directory
---
    ~ --> Home directory
---
    mkdir -p folder/subfolder/subfolder2 --> create parent and child directory

---
---

## 👇FILE

    touch test.txt(file name) --> creates a empty file
---
    ls -l --> lists the contents in current directory
---
    echo  Print Output

    echo "This is a text" > test.txt
---   
    cat test.txt --> writes the content of file into terminal & exits
---
    more test.txt --> writes the content of file on terminal page by page ( to move to next page need to hit space bar on keyboard )
---
    less test.txt --> open the file on terminal & can be read line by line (use arrows to scroll up & down)

    				  To comeout need to press 'q' on the key board
---
    vi test.txt --> Visual Editor
    		-This opens the file in read only mode
    		-To edit the file, press 'i' on keyboard for INSERT mode & then you can write anything
    		-once the text is entered, press 'ESC' on keyboard to return back on readonly mode
    		-press ':wq' on keyboard -- to save & come out of the file
    		-press ':q' on keyboard -- to come out of the file without saving
    		-press ':wq!' on keyboard -- to save forcefully & come out of the file
    		-press ':q!' on keyboard -- to come out of the file forcefully without saving
---
    rm test.txt --> To remove a file
---
# 👇COPY/RENAME/MOVE/OPERATION

    While performing these operations, we can always use absolute paths or relative paths accrodingly.
    These commands expects source & dest values

    cp A.txt B.txt  --> makes a copy of A.txt names it to B.txt in current directory

    cp /home/A.txt /tmp/A.txt --> make a copy of A.txt to /tmp

    cp -r testdir/ newdir/ --> makes a copy of testdir & names it to newdir in current dirctory

    cp -r /home/testdir /tmp/testdir --> makes a copy of testdir to /tmp

    mv A.txt new.txt ---> renames A.txt to new.txt in current path

    mv A.txt /tmp ---> moves to A.txt to /tmp

    mv testdir newdir --> renames testdir to newdir in crrent path

    mv newdir /tmp ---> moves newdir to /tmp path

---

## 👇Linux pipes

    cat test.txt | grep 'searchkey' ---> Only gives lines from that file thant contains the key in ''

    cat test.txt | less ---> Prints out file content, but you have the possibility to scroll
                             Quit the reading with 'q'

    cat test.txt | uniq ---> This will sort the given file and print the unique values only.

    cat test.txt | head -4 ---> Only prints out the last 4 lines of the command before the pipe, you can specify any number you want

    ls | wc -l ---> prints out the linenumber of the command before the pipe

---

## 👇PERMISSION

Observe the output of ls:

drwxrwxr-x 2 manifoldailearning manifoldailearning 4096 Nov 7 23:38 testdir
-rw-rw-r-- 1 manifoldailearning manifoldailearning 126 Nov 7 23:37 abc.txt
-rw-rw-r-- 1 manifoldailearning manifoldailearning 126 Nov 7 23:38 one.txt

    drwxrwxr-x or -rw-rw-r--   --> Read/Write/Execute Permission for a file or a directory in linux

    (1st value)manifoldailearning --> owner of the file/directory
    (2nd value)manifoldailearning --> group who owns file/directory

---

How to update the owner & group for a file/dir -

    chown ( change owner ) is the command to update the owners of dir/file
    note: note that you need to have previliges to update the permissions for a file/directory

    Syntax: chown owner:group filename/dirname

---

How to update the read,write & execute permissions for a file/dir

    	How to decode the Read/Write/Execute Permission terminology:

    	-/d    ---> denotes if it is a file or directory ( - means file / d means directory )
    	rwx    ---> means read,write & execute permissions for super user ( root )
    	rw-    ---> means read,write permissions for the owner of the file ( ex: manifoldailearning as above )
    	r--    ---> means read only permissions for others ( whoever login to the machine )


    	r  --> Permission to read the file.
    	w  --> Permission to write (or delete) the file.
    	x  --> Permission to execute the file, or, in the case of a directory, search it.

    chmod ( change mode ) is the command to update the read/write/execute permissions for a file/directory
    	r = 4, w = 2, x = 1

    	- | rwx  | rwx  | rwx
    	- | 421  | 421  | 421

    	To update the permissions we can sum 421
    	If super user needs to have read,write & exeute give 7
    	If the owner need to read & write give 6
    	If other need to have only read give 4


    	chmod 777 file/dir -- rwx for root, rwx for owner, rwx for others
    	chmod 764 file/dir -- rwx for root, rw for owner, r for others
    	chmod 755 fire/dir -- rwx for root, rw for owner, rw for others
---

<br>
<br>

[![Maintened by - Abhiram-Siriki45](https://img.shields.io/badge/Maintained%20by-Abhiram%20Siriki45-red)](https://github.com/Abhiram-Siriki45)
