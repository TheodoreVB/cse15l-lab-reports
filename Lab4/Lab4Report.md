# Lab Report 3

## Log into ieng6

For this part, I created an alias in my .bashrc folder with the following code:
`alias ieng6="ssh cs15lfa23mq@ieng6.ucsd.edu"`
The goal with this line of code was to create a custom command in my bash, that when I run `ieng6` with no arguments, bash will automatically log me into the ieng6 server on my account. This is works because I have set up the .ssh keys on my account so I don't need a password to log in.

Keys Pressed: `ieng6<enter>`

**INSERT IMAGE**

## Clone fork using SSH URL

Since I wouldn't have typically cloned a repository recently, I will just use the usual method for cloning, witch is `git clone git@github.com:TheodoreVB/lab7.git`

Keys Pressed: `git<space>clone<space> <ctrl-v>`

**INSERT IMAGE**

## First test run

To run the test file, I would first have to cd into the correct directory using the cd command. While not required, I like to `ls` to make sure I see the correct files. Once inside the `lab7` directory, I can then use `bash test.sh` to run the tests.

Keys Pressed: `cd<space>lab7<enter> ls<enter> bash<space>test.sh<enter>`

**INSERT IMAGE**

## Edit the code

This process takes a bit longer as we have to go through the file to edit it. Assuming I already know what the bug is, I will first open the file with `vim ListExamples.java`. Using `:44` I can jump straight to the line that with the bug. I can use `e` to get to the end of the current word (cursor just before the 1 in index1) and change the 1 to a 2 using `cl2`, which deletes the next letter and puts you into insert mode at that point, which I then replace with 2. After leaving insert mode, I use the command `:wq` to save and quit the document.

Keys Pressed: `vim<space>ListExamples.java :44<enter> e cl2<esc> :wq<enter>`

After using `vim ListExamples.java`:


After using `:44`:


After using `e`:


After using `cl2`:


After using `:wq`:



## Second test run

To run the `test.sh` file again, we will use bash's history function to make it easier (slightly). Going up once in the history is the `vim` command I just ran, and going up again is the `bash` command I ran earlier. So I run that command again to test the files for the second time.

Keys Pressed: `<up><up><enter>`


## Commit and push to GitHub

Since we know the process to commit and push to GitHub, we can combine all 3 of the commands, `git add`, `git commit`, and `git push`, into one line. We can use `-m <message>` for the commit message so we don't have to type it into vim when it pops up.

Keys Pressed: `git<space>add<space>ListExamples.java; git<space>commit<space>-m<space>"Changed Index1 -> Index2"; git<space>push <enter>`














