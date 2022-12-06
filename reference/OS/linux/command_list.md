# Ubuntu Command List
<br>

### Create
+ Create file
    - touch [FILENAME]
+ Create file and write data, end with EOF(Ctrl + D)
    - cat > [FILENAME]<br>[DATA1] [DATA2]...
+ Create folder
    - mkdir [FOLDERNAME]

### Read
+ Read directory list
    - ls
+ Print file content on console
    - cat [FILENAME]
+ Read file on IDE(Integrated Development Environment) editor
    - code [FILENAME]

### Update
+ Update dir
    - mv [FILENAME/FOLDERNAME] [FOLDERNAME]
+ Update filename
    - mv [OLD_FILENAME] [NEW_FILENAME]
+ Move files
    - mv [file1] [file2] [file3] [NEW_DIR]


### Delete
+ Remove file/Folder
    - rm -rf [FILENAME]
+ Remove file with exception
    - rm \`ls *|grep -v [FILENAME]\`
