## install bzip2 packege install the bzip2 packege the enable .bzp compression
1.  yum install bzip2
   compress a single file compress file nameusing the burrows wheeler algorithum 
   2. .bzip2 filename 
compress multiple file 
3. bzip2 file1 file2 file3
   verbose compresion:show detaild output during compression
4. bzip2 -v filename
    compresss the corn and firewall file 
5. bzip2 cron firewalled
   compress the all file in the root/d1/ directory
6. bzip2 /root/d1/*
    compress .txt file in /root/d1/
7. bzip2 /root/d1/* .txt
   compress all file ending in .log in current directory
8. bzip2 *.log
   compress files whose name begin with the latter s 
9. bzip2 s*
   compress file in the current directory displaying verbose output
10. bzip2 -v *


- *Compress every file in the current directory, displaying verbose output:*

1. bzip2 -v *

- Decompress all.bz2 files in /root/d1/:

1. bumip2 /root/d1/*

- Decompress all .bz2 files in /root/d1/that start with ip:

1. bunzip2/root/d1/ip*

- Decompress filename.bz2:

1. bunzip2 filename.bz2

- Decompress messages1.bz2 and messages2.bz2 at the same time:

1. bunzip2 messages1.bz2 messages2.bz2

- Decompress every.bz2 file that starts with messages:

1. bunzip2 messages*

- Decompress every.log.bz2 file in the current directory:

1. bunzip2 *.log.bz2

- Decompress every.bz2 file:

1. bunzip2 *.bz2

- Decompress all.bz2 files that start with s:

1.  bunzip2 s*

- Decompress every.bz2 file in the current directory:

1. bunzip2 *

## Gzip

- Install gzip: Installs gzip for.gz compression.

1. yum install gzip

- Compress a single file: Creates .gz file from a single file.

1.  gzip filename

- Compress messages2 Into messages2.gz:

1. gzip messages2

- Compress messages3 and messages4 Into separate .gz files:

1. gzip messages3 messages4

- Compress every .log file:

1. gzip *. log

- Compress every fe in the current directory that starts with s:

1. gzip s*


## Gunzip

- Decompress filename.gz back to its original file:

1.  gunzip filename.gz 

- Decompress messages3.gz:

1. gunzip messages3.gz

- Decompress messages.gz and lastlog.gz in one command:

1.  gunzip messages.gz lastlog.gz

- Decompress all.log.gz files in the current directory with verbose output:

1. gunzip -v *.log.gz

- Decompress every.log.gz file in the current directory:

1.  gunzip *.log.gz

- Decompress every.gz file in the current directory:

1.  gunzip *

- Recursively compress all files in the log/directory:

1. gzip -r log/

- Recursively compress all files in the log/ directory with verbose output:

1.  gzip -vr log/

- Recursively decompress all .gz files within the log/ directory:

1. gunzip -r log/

- Recursively decompress all.gz files within the log/ directory with verbose output:

1. gunzip -vr log/

- Compress all files in the /root/d1/directory:

1. gzip  /root/d1/*

- Decompress all .gz files in the /root/d1/directory:

1. gunzip /root/d1/*

- Compress all files in /root/d1/ starting with ip:

1. gzip /root/d1/ip*

- Decompress all .gz files in /root/d1/starting with ip:

1. gzip /root/d1/ip*

- Compress every file in the current directory:

1. gzip *

- Compress filel, file2, and file3 into separate .gz files:

1. gzip file1 file2 file3

- Verbose compression: Shows progress during compression.

1. gzip -v messages-2


## Zip

- Install zip and unzip: Installs zip and unzip tools.

1.  yum install zip

 2. yum install unzip

- Create a ZIP archive messages.zip containing messages:

1.  zip messages.zip messages3

- Create a ZIP archive messages-all.zip containing messages4, messages5, and messages6:

1.  zip messages-all.zip messages4 messages5 messages6

- Create a ZIP archive log.zip containing all .log files in the current directory:

1.  zip log.zip *.log

- Create a ZIP archive files1.zip containing all files starting with b, with verbose output:

1.  zip -v files1.zip b*

- Create a ZIP archive all-files.zip containing all files in the current directory:

1.  zip all-files.zip *

- Recursively create a ZIP archive log.zip containing the entire log directory:

1. zip -r log.zip log/

- Create a ZIP archive filename.zip containing the file filesname:

1.  zip filename.zip filesname

- Create a ZIP archive filename.zip containing file1, file2, and file3:

1. zip filename.zip file1 file2 file3

- View zip archive information: Lists details about .zip contents.

1. zipinfo messages-all.zip

## Unzip

- Extract the contents of messages.zip into the current directory:

1.  unzip messages.zip

- Extract the contents of messages-all.zip Into the current directory:

1. unzip messages-all.zip

- Extract the contents of messages-all.zip Into the directory mes:

1.  unzip messages-all.zip -d mes

- Extract the contents of filename.zip Into the current directory:

1.  unzip filename.zip

- Extract the contents of log.zip into the /tmp/directory:

1. unzip -d /tmp/ log.zip

- Extract the contents of log.zip into the current directory 
unzip log.zip
Extract the contents of log.zip Into the /tmp/directory:

1. unzip -d /tmp/ log.zip

- Extract the contents of log.zip Into the current directory:

1.  unzip log.zip

- Extract all .zip files in the current directory:

1. unzip *.zip

## 7z (7-Zip)

- Install 7z: Install the 7-Zip archiving tool (via EPEL repository).

1. yum install epel-release.noarch

2. yum install p7zip

- Show usage help: Displays help and usage options.

1. 7za --help

- Create an archive named messages. 72 containing the messages file/directory:

1. 7za a messages.7z messages

- Create an archive named mess.7z containing the messages file/directory:

1. 7z a mess.7z messages

- Create an archive messages-files.7z containing messages-3, messages-4, messages-5, and messages-6:

1.  7za a messages-files messages-3 messages-4 messages-5 messages-6

- Create an archive logfiles.7z containing all .log files in the current directory:

1. 7za a logfiles.7z *.log

- Create an archive log.7z containing the log/ directory 

1. 7za a log.7za log/

- Create an archive files.7z containing all files and directories in the current directory starting with b:

1. 7za a files.7z b*

- Create an archive log.7z containing the log directory:

1. 7z a log.7z log

- Create an archive d1.7z by recursively archiving the /root/d1/ directory 

1. 7z a d1.72 -r /root/d1/

- The 7za command is a standalone version of 7-Zip that works with a limited set of compression formats. The following command lists the contents of the archive file logfiles.7z:

1. 7za l logfiles.7z

- Similarly, to view the contents of another archive named log.7z:

1. 7za l log.7z

- The 7z command is a more complete tool, supporting additional compression formats . To list the contents of mess.7z

1. 7a l mess.7z

- To view the contents of d1.7z:

1.  7z 1 d1.7z

- You can also list the contents of multiple .7z archives at once:

1.  7z 1 *.7z

- Or, if you have archives in different directories:

1.  7z 1 /path/to/directory/*.7z

- Extract Files From messages.7z Using 7za

1.  7za e messages.7z

- Extract log.7z To A Subdirectory Named Log

1. 7za e log.7z -o log

- Extract log.7z To A Subdirectory Named log2

1.  7za e -olog2 log.7z

- Extract log.7z To Current Directory

1.  7za e log.7z

- Extract Files From mess.7z Using 7z

1. 7z e mess.7z

- Extract Files From d1.7z Using 7z

1. 7z e d1.7z

- Explanation Of Thee Command 

e stands for extract.
It does not preserve directory structure.
Use -o<dir>to specify the output directory 
1 7za e archive.7z -ooutput_dir

When To Use e vs x

- Use e (extract) when:

. You want a flat output (no subfolders).

. You're extracting a simple archive with only files.

- Use x (extract with full paths) when:

. You want to preserve the directory structure inside the archive.

- Example using x:

1. 7za x archive.7z

Extract with directory structure: Keeps folder structure during extraction.

1.  7za x log.7z

2. 7z x log.72

Test archive integrity: Verifies archive integrity.

1. 7za t log.7z

2.  72 t mess.72


## Tar


Display help: Lists tar's options and usage.

1. tar--help

The tar command in Linux is used to archive files and directories. By default, it does not compress them (you can add compression options later like -z for gzip or -j for bzip2). Here, we're using the -c (create), -v (verbose), and -f (file name) options.

Create An Archive Named messages.tar Containing The Directory messages3

1 tar -cvf messages.tar messages3

- -c :- create a new archive.

- -v :- verbose output showing the files being archived.

- -f messages.tar :- specifies the archive file name.

messages3 :-the directory to include in the archive.

Create An Archive Containing Multiple Directories

1 tar -cvf messages-files.tar messages messages3 messages4 messages5

Create An Archive Of A Directory Named Log

1 tar -cvf log.tar lag/

Creates an archive named messagest1.tar containing the messagest1 directory.

1 tar -cvf messagesl.tor messagesl

Creates an archive named messages2.tar containing the messages2 directory.

1 tar -cvf messages2.tar messages2

Creates an archive named messages3.tar containing the messages3 directory.

1 tar -cvf messages3.tar messages3

Create An Archive Named messages: tar Containing messages Directory

1 tar -cvf messages.tar messages

Create An Archive Using Wildcards

1 tar -cvf ip.tar ip*

This command archives all files and directories in the current dractory whose names start with ip. Examples of included items:

- ip

- ip1

- ip_config

- ip_addresses

Explanation Of The Command Options

 · -c:- Create a new archive.

- -v:- Show progress and list files as they are added.

- -f: Specify the filename of the archive.

This creates an archive called archive.tar from the specified directory.

1 tar -cvf archive.tar /path/to/directory

To add compression, include:

- -z for gzip :- tar -czvf archive.tar.gz /path
 · -j for bzip2 :- tar -cjvf archive.tar.bz2 /path

- -j for xz :- tar -cJvf archive.tar.xz /path

 · To extract an archive:

1 tar -xvf archive.tar

· To list the contents of an archive:

1 tar -tvf archive.tar

Compress tar archives separately: Use gzip/bzip2 after creating tar file.

1 gzip messages2.tar

2 bzip2 messages3.tar

Create compressed tar archives directly: Combines archiving and compression.

1 tar -czvf messages4.tgz messages4

2 tar -cjvf messages5.tbz messages5

3 tar -cjvf log.bz2 log/

4 tar -czvf log.tgz log/

5 tar -cjvf filename.tbz file

6 tar -czvf filename.tgz file

7 tar -xjvf filename.thz

8 tar -xvf d1.tar.gz

Check file type: Identify file type to avoid confusion.

1 file messages1.tar

Decompress compressed tar files separately: Uncompress before extracting.

1 gunzip file.tar

2 bunzip2 d1.tar.bz2

Create A Gzip-Compressed Archive of messages4

1 tar -czff messages4.tgz messages4

- -c: create a new archive.

- -z: compress using gzip.

- -v: show progress while archiving.

- -f messages4.tgz: output archive filename.

- messages4: the directory to archive.

- The .tgz extension is commonly used as a shorthand for.tar.gz archives.

Create A Bzip2-Compressed Archive of messages5

1 tar -cjvf messages5.tbz messages5

- -j: compress using bzip2.
- .tbz is often used as an alternative to .tar.bz2.

Create A Bzip2-Compressed Archive Of The log Directory

1 tar -cjvf log.bz2 log/

Create A Gzip-Compressed Archive Of The log Directory

1 tar -czvf log.tgz log/

Create A Bzip2-Compressed Archive Of A Single File

1 tar -cjvf filename.tbz file

Create A Gzip-Compressed Archive Of A Single File

1 tar -czvf filename.tgz file

Explanation Of Compression Options

- -z: Use gzip compression, produces.tar.gz or .tgz archives.

- -j: Use bzip2 compression, produces .tar.bz2 or .tbz archives.

- -J: Use xz compression, produces .tar.xz archives (more modern and highly compressed).

You can view the contents of a compressed archive without extracting it:

1 tar -tzvf archive.tgz

or

1 tar -tjvf archive.tbz

- Extract a gzip-compressed archive:

1 tar -xzvf archive.tgz

- Extract a bzip2-compressed archive:

1 tar -xjvf archive.tbz

Extract tar archives: Unpacks.tar, .tgz, .tbz files.

1 tar -xvf messages-files.tar

2 tar -xvf log.tar

3 tar -xvf messages.tar

4 tar -xvf filename.tar

5 tar -xvf d1.tar

6 tar -xzvf filename.tgz

7 tar -xjvf filename.tbz

8 tar -xvf d1.tar.gz

Check file type: Identify file type to avoid confusion.

1 file messages1.tar

Decompress compressed tar files separately: Uncompress before extracting.

1 gunzip file.tar

2 bunzip2 d1.tar.bz2


##  Cat-Command

The cat command (short for concatenate) is a commonly used in Linux utility for working with text files. It can display file contents,combine files create new file, and support redirection.below is a comprehensive reference with using example and description 

Display File Contents

Displays the contents of the /var/log/demo file.

1 cat /var/log/demo

Outputs the content of filename.txt to the terminal.

1 cat filename.txt

Displays the contents of multiple system files in sequence.

1 cat /etc/passwd /etc/shadow/etc/group/etc/gshadow

Displays multiple files using semicolon-separated commands.

1 cat test; cat test1; cat test2

Displays contents of a user file and the hostname configuration file.

1 cat 1.txt /etc/hostname

Display Multiple Files Together

Displays the contents of file1.txt and file2.txt in sequence.

1 cat file1.txt file2.txt

Combines contents of error and normal list files.

1 cat list-error.txt list.txt

Displays contents of three files together.

1 cat a1.txt a2.txt a3.txt

Displays the contents of two files named test and test1.

1 cat test test1

Combine and Save To New File

Combines two files and stores the result in combined.txt.

1 cat file1.txt file2.txt > combined.txt

Creates newfile.txt containing content from test.txt and text1.txt.

1 cat test.txt text1.txt > newfile.txt

Saves content from multiple system configuration files into 1.txt.

1 cat /etc/hostname /etc/hosts /etc/os-release > 1.txt

Concatenates all .conf files from /etc/directory into all-conf.txt.

1 cat /etc/*.conf > all-conf.txt

Combines two files into 1. txt.

1 cat Hacking Ethical-Hacking > 1.txt

Append to an Existing File

Appends content interactively to test.txt (end input with Ctrl+D).

1 cat >> test.txt

Appends system hosts file content to 1. txt.

1 cat /etc/hosts >> 1.txt

Appends content of list.txt to t1.txt.

1 cat list.txt >> t1.txt

Create a New File Using Cat

Creates a new file test.txt by typing interactively. End Input with Ctrl+D.

1 cat > test.txt

Uses a here-document (heredoc) to create a file named test.

1 cat << EOF >> test

Example:

1 cat << EOF >> notes.txt

2 Line 1

3 Line 2

4 EOF

Display with Line Numbers Or Symbols

Displays content with line numbers.

1 cat -n test.txt

Displays content with line numbers and shows $ at line ends.

1 cat -ne a4.txt

Displays line endings explicitly using $ symbol.

cat -e test

Suppress Blank Lines

Removes repeated blank lines while displaying.

1 cat -s filename.txt

Use With Paging Tools

Displays long file content page-by-page using more.

1 cat test.txt | more
 
2 more /var/log/messages

Displays long file content page-by-page using less.

1 cat test.txt | less

2 less /var/log/messages

Typical Use Cases

- View the contents of text or log files.

- Combine multiple files into one.

- Create small test or note files.
 
- Append data to existing documents.

- Pipe file content into other commands.

Nano-Command

The nano command is a simple, user-friendly, terminal-based text editor used to create and edit text files in Linux. It is ideal for beginners due to its intuitive interface and on screen command hints 

Install Nano

Installs the nano editor using the yum package manager (typically for RHEL/CentOS/Fedora-based systems).

1 yum install nano

Open Nano Editor

Launches the nano editor without opening any specific file.

1 nano

Open Or Create A File
Opens an existing file named armour.txt If it exists, or creates it if it doesn't.

1 nano armour.txt

Basic Usage Instructions

- Use the arrow keys to navigate.

- Type text normally to edit.

- Use the following shortcut keys for operations:

- Ctrl+0 - Write (save) the file.

- Ctrl+X Exit the editor.

- Ctrl+K-Cut a line.
- 
- Ctrl+U - Paste a line.

- Ctrl+W - Search in the file.

- Ctrl+G - Help.

Example Workflow

1. Create or open a file:

   1 nano notes.txt

2. Type content inside the editor.

3. Press Ctrl+0 to save.

4. Press Enter to confirm the filename.

5. Press Ctrl+X to exit.

Vim-Command

vim is a powerful and widely used text editor in Unix/Linux systems. It stands for Vi IMproved, which is an enhanced version of the older vi editor.

- Vi comes from "Visual Editor"

- Vim is not WYSIWYG (What You See Is What You Get)

- Used for editing configuration files, scripts, and programming

Launch Vim

Opens the vim editor without any file.

1 vim

Opens the Vim help menu.

1 :help

Opens or creates a file named filename.

1 vim filename

Vim Modes

Vim operates in multiple modes, each with a specific purpose:

1. Command Mode - Default mode on start. Used to move, delete, copy, or navigate.

2. Insert Mode - Allows text input. Enter with i or insert.

3. Visual Mode - Used for selecting blocks of text. Enter with v.

4. Replace Mode - Replace characters. Enter with R.

5. Command-Line Mode (Last Line Mode) - Used for saving, quitting, and search/replace commands. Enter with : .

Command-Line Mode Examples

Run shell commands from within Vim:

1  :!ls

1  :! pwd
 
1  :! id

Enable line numbers:

1 :set number

1 :set nu

Disable line numbers:

1 :set nonumber

Search And Replace In Vim

Find and replace within the current line:

1  :s/AI/Armour Infosec/s
G= kitne bhi match honge sari ko reply kr degaa agar g nhi lgayege to har ak line ka first ko hi replace kregaa 

Find and replace between lines 1 and 32:

1 :1,32s/AI/ARMOUR

Replace all instances in the entire file:

1 :%s/AI/ARMOUR

Prompt before each replacement:

1  :%s/AI/ARMOUR/c 
C = confirm krega reply Krna hai kyaa 
Replace kr diyee or wapis lana hai to U dbao simple 

Global search and replace:

1 :%s/nologin/bash/g

Case-sensitive replace with confirmation:

1 :%s/bash/sh/gc

Case-insensitive replace:

1 :%s/bash/sh/gi

1. Replace Al with Artificial Intelligence in all lines:

1 :%s/AI/Artificial Intelligence/g

2. Replace bash with sh, but ask for confirmation:

1 :%s/bash/sh/gc

3. Replace /bin/bash with /sbin/nologin only:

1 :%s/\/bin\/bash/\/sbin\/nologin/g

4. Replace only from line 3 to 6:

1 :3,6s/AI/ML/g
5. Remove extra blank lines :
 1  :g/^$/d

Replace in a specific line range:

1 :56,65s/bahs/bash/g

Change default login shell for all users (example):

1 :%s/\/bin/bash/\/sbin\/nologin/g

1 :%s/\/sbin\/nologin/\/bin\/bash/g

Clear search highlighting:

1 :nohl

Command Mode - Moving The Cursor

Move left by one character:

1.  h

Move down one line:

1.  j

Move up one line:

1.  k

Move right one character:

1.  l

Command Mode - Deleting character 

Delete a single character:

1.  x

Delete 10 characters:

1.  10x

Delete character before the cursor:

1.   X

Delete 10 characters before the cursor:
1.  10X

Command Mode - Deleting Words

Delete one word from the cursor:

1.  dw

Delete 10 words:

1.  10dw

Command Mode - Deleting Lines

Delete one line:

1.  dd

Delete 10 lines:

1.  10dd

Delete to the end of the line from the cursor:
1.  D

Command Mode - Replacing Character 

Replace a single character:

1.  r

Replace 3 characters:

1.  3r

Command Mode - Replacing Words

Change (replace) a word from the cursor:

1.  cw

Change 3 words:

1.  3cw

Command Mode - Replacing Lines

Change text from the cursor to the end of line:

1.  C

Replace 3 lines:

1.  3C

Command Mode - Insert Blank Lines

Insert a blank line below the current line:

1.  o

Insert a blank line above the current line:

1.  0

Command Mode - Joining Lines

Join two lines into one:

1.  J

Join three lines into one:

1.  3J

Command Mode - Copy And Paste Lines

Copy a line:

1.  yy

Paste a copied line:

1.  p

Insert 
1.  I
Save file 
2.  :w
Exit 
3.  :q
Save + exit 
4. :wq
Force full save exit
5.  :wq!

Vim prectice tool
1.  vimtutor

String-Processing

String Processing

String Processing in the context of Linux refers to the manipulation, transformation and analysis of text (string) data using various command -line utilities.
These tools are especially useful when working with log files, configuration files, data files,or outputs from other commands . They help in filtering, sorting, counting, and displaying specific parts of text.

Common Use-Cases for String Processing:

- Viewing parts of files (head, tail)

- Counting words/lines (wc)

- Sorting data (sort)

- Filtering duplicates (uniq)

- Repeating a command (watch for monitoring)

- Parsing and transforming text (cut, awk, sed not covered above but related )

Head

Used to display the first few lines or bytes of one or more files.

Examples

Print the first 10 lines of /etc/passwd:

1.  head /etc/passwd

Print the first 10 lines of /var/log/messages:

1.  head /var/log/mussages

Navigate to /var/log/directory:

1.  cd /var/log/

View/atc/passed with line numbers:

1.  cat -n /etc/passwd

View first 10 lines of messages:

1.  head messages

Print first 5 lines of messages:

1.  head -n 5 messages

Print first 150 lines of massages:

1.  head -n 150 messages

Print first 4 lines of multiple system files:
1.  head -n 4 /etc/passwd /etc/shadow/etc/group/etc/gshadow

Verbose mode with filename headers:

1.  head -v -n 4 /etc/passwd

Display first 500 bytes of /etc/shadow:

1.  head -c 500 /etc/shadow

Display first 5 bytes of two files:

1.  head -c 5 /etc/shadow /etc/passwd

Display first 4 bytes of four system files:

1.  head -c 4 /etc/passwd /etc/shadow /etc/group /etc/gshadow 

Display first 40 bytes of multiple system files:

1.  head -c 40/etc/passwd /etc shadow /etc/group /etc/gshadow

Tail

Used to display the last few lines or bytes of files. Helpful for reading logs in real time.

Examples

View/etc/passwd with line numbers:

1.  cat -n /etc/passwd

Display last 10 lines of /etc/passwd:

1.  tail /etc/passwd
 
Display last 10 lines of /var/log/messages:

2.  tail /var/log/messages

View last 20 lines of messages:

1.  tail -n 20 /var/log/messages

View last 5 lines of multiple system files:

1.  tail -n 5 /etc/passwd /etc/shadow/etc/group /etc/gshadow

Tail multiple files:

1.  tail /etc/passwd /etc/shadow

Verbose file name output:

1.  tail -v /var/log/messages

Tall with verbose output on multiple files:

1.  tail -n 5 -v /etc/passwd /etc/shadow

Verbase mode with 3 lines from end:

1.  tail -v -n 3 /var/log/messages

Read last 500 bytes of a file:

1.  tail -c 500 /etc/passwd

Read last 50 bytes with verbose output:

1.  tail -c 50 -v /etc/passwd /etc/shadow

Follow live updates to log file:

1.  tail -f /var/log/messages

Follow Apache access logs:

1.  tail -f /var/log/apache2/access.log

Follow HTTPD access logs:

1.  tail -f /var/log/httpd/access_log

WC (Word Count)

The wc command prints the number of lines, words, and characters in a file.

Examples

Count lines, words, and characters in /etc/passwd:

1.  wc/etc/passwd

Count in log file:

1.  we /var/log/message

Line count only:

1.  wc -1 /var/log/messages

Word count only:

1.  wc -w /var/log/messages

Character count only:

1.  wc -c /var/log/messages

Multiple files:

1.  wc /etc/passwd /etc/shadow/etc/group /etc/gshadow

All.conf files in /etc:

1.  wc /etc/.conf

All files in current directory:

1.  wc *

Line count for all files:

 1. wc -l

Count files/folders in current directory:

1.  ls | wc -l

Files in /etc:

1.  ls /etc/ | wc -l

Include hidden files:

1.  ls -a /etc/ | wc -l

One entry per fine:

1.  ls -a1 | wc -l

Processes running 

1.  ps -aux | wc -l

Sort

Sorts lines from text files.

Input File Examples

test1.txt

Contains fruits, numbers, names, and mixed-case entries for sorting tests 

datafile.txt

1.  John 25

2.  Alice 30

3.  Bob 22

4.  Eve 35

5.  Charlie 28

6.  Diana 30

datafile2.txt

1.  John, 25, Engineer

2.  Alice, 30, Manager

3.  Bob, 22, Intern

4.  Eve, 35, Director

5.  Charlie, 28, Analyst

6.  Diana, 30, Consultant


Basic Sort Commands

Sort default:

1.  sort test.txt

Human-readable number sort:

1.  sort -h test.txt

Dictionary order sort:

1.  sort -d test.txt

Numeric sort:

1.  sort -n test.txt

Reverse sort:

1.  sort -r test.txt

Reverse numeric:

1.  sort -r -n test.txt

Human-readable reverse sort:

1.  sort -hr test.txt

Unique numeric sort:

1.  sort -u-n test.txt

Alternative unique numeric:

1.  sort -un test.txt

Reverse human-readable sort:

1.  sort -r -h test.txt

Unique sort from file:

1.  sort -unique -n no.txt
 
Random sort:

2.  sort -R no.txt

Sort with Column and Delimiter

Sort by numeric value in column 2:

1 sort-h-k 2 datafile.txt

Sort comma-separated entries by name:

1.  sort datafile2.txt

Use, as delimiter:

1.  sort -t ' , ' datafile2.txt

Sort by age (2nd column):

1 sort -t ' , ' -k 2 datafile2.txt

Sort by designation (3rd column):

1.  sort -t ' , ' -k 3 datafile2.txt

Sort by name (1st column):

1.  sort -k 1 -t ' , ' datafile2.txt

Sort by numeric age:

1.  sort -k 2 -t ' , ' datafile2.txt

Human-readable sort on 3rd column:

1.  sort -h -k 3 -t ' , ' datafile2.txt

Regular sort on 3rd column 

1.  sort -k 3 -t ' , ' datafile2.txt

Month Sort

Default alphabetical:

1.  sort month-name.txt

Human readable:

1.  sort -h month-name.txt

Dictionary order:

1.  sort -d month-name.txt.

By actual month order:

1.  sort - M month-name.xt

Sort And Remove Duplicates

Sort:

1.  sort duplicates.txt

Unique entries only:

1.  sort -u duplicates.txr

Direct use of uniq

1.  uniq duplicates.txt

Sort then remove duplicates:

1.  sort duplicates.txt | uniq

Sort, then count duplicates:

1.  sort duplicates.txt | uniq -c

Using sort -u with piped input:

1.  cat no.txt | sort -u

Another method:

1.  sort -u no.txt

Sort and remove duplicates:

1.  sort no.txt | uniq

Count repeated line

1.  cat no.txt | sort | uniq -c

Watch

Re-runs a command at a fixed interval for real-time monitoring.

Examples

Refresh w every 5 seconds:

1.  watch -n 5 w

Monitor GPU usage every 0.01 seconds:

1.  watch -n 0.01 nvidia-smi

grep-Command

grep Command - Pattern Matching in Linux

grep (Global Regular Expression Print) is used to search for patterns in files or Input text streams.

The grep command is a powerful tool used to search for specific patterns in files. Below are examples of how to use grep to find occurrences of usernames or keywords like root, armour or home in system configuration and  log files. 

Basic Syntax

1.  grep [options] PATTERN [FILE ... ]

Basic Examples

Searches for lines containing the string root in /etc/passwd.
Typically used to check root user account information.

1.  grep root /etc/passwd

Searches for the string armour in /etc/passwd.
Used to check if a user named "armour" exists on the system.

1.  grep armour /etc/passwd

Searches for lines containing the string home in /etc/passwd.
Useful for listing users whose home directories are under/home.

1.  grep home /etc/passwd

Searches both /etc/passwd and /etc/shadow for the string root.
Used to confirm that the root account is defined and has a shadow passwor

1.  grep root /etc/passwd /etc/shadow

Searches for root in /etc/passwd, /etc/shadow, /etc/group,and /etc/gshadow.
Provides a complete audit of all references to the root user and group.

1.  grep root /etc/passwd /etc/shadow /etc/group /etc/gshadow

Searches/var/log/messages for lines containing root
. Helps detect root-level events such as logins, commands, or service activity.

1.  grep root /var/log/messages

Searches /var/log/messages for Root (capital 'R). Some logs or applications may capitalize usernames or Identifiers.

1.  grep Root /var/log/messages

Performs a case-Insensitive search for root in /var/log/messages.Matches all variations like root, Root, or ROOT.

1.  grep -i root /var/log/message 

Using cat with grep

Searches /var/log/messages for lines containing the string root using a pipeline with cat. Functionally equivalent to grep root /var/log/messages, but the use of cat is redundant in this case.

1.  cat /var/log/messages | grep root

Performs a case-insensitive search for root in /var/log/messages using a pipeline with cat. Matches variations like root, Root, or ROOT. The cat command is unnecessary here as well, since grep can read the file directly.

1.  cat /var/log/messages | grep -i root

Quoting Patterns

Searches /var/log/messages for lines containing the exact phrase Started Session, using double quotes to preserve the space between words.

1.  grep "Started Session" /var/log/messages

Searches /var/log/messages for the phrase Started Session, using single quotes for the same purpose. Both single and double quotes are valid, depending on shell context.

1.  grep 'Started Session' /var/log/messages

Searches for Started Session in /var/log/messages by escaping the space between the words with a backslash. This also preserves the phrase as a single argument to grep.

1.  grep Started\ Session /var/log/messages

Multiple File Matching

Uses grep -E (extended regex) to search /var/log/messages for lines containing either root or armour. The I acts as a logical OR within the pattern.

1.  grep -E "(root | armour)" /var/log/messages

Searches /var/log/messages for lines containing the word Session, then filters only those lines that also contain the word Start. This is done using a pipeline of two grep commands.

1.  grep "Session" /var/log/messages | grep Start

Searches for lines containing Session and Start in /var/log/messages, but excludes any line that also contains the word root using grep -v.

1.  grep "Session"/var/log/messages | grep Start | grep -v root

Grouped Searches

Uses extended regular expressions to search /var/log/messages for lines containing either Started or Starting.

1.  grep -E "(Started/Starting)" /var/log/messages

Searches for lines containing either Started Session or Starting Session, and then filters those that also contain either armour or root.

1.  grep -E "(Started Session Starting Session)" /var/log/messages | grep -E "(armour|root)"

Searches for lines with Started Session or Starting Session, but excludes any line that contains either root or armour.

1.  grep -E "(Started Session Starting Session)" /var/log/messages | grep -vE "(rootlarmour)"

Regex Operators

Searches /var/log/messages for lines containing the string root.
(the period is escaped so it is treated as a literal dot, not a regex wildcard).

1.  grep *"root\."*/var/log/messages


Searches /var/log/messages for lines where root. appears at the end of a line. The dollar sign

$ anchors the match to the line's end.

1.  grep "root\.$" /var/log/messages

Searches /var/log/messages
for lines that start with Apr
anchors the pattern to the start of the line, and the double space is preserved for proper date formatting.

1.  grep "^Apr 8" /var/log/messages

Filters lines starting with Dec 7 in /var/log/messages, then narrows the result to those also containing the word Session.

1.  grep "^Dec 7" /var/log/messages | grep Session 

Searches /etc/passwd for lines ending with bash. The dollar sign $ ensures that only entries where bash is at the end (L.e., the user's login shell) are matched.

1.  grep 'bash$' /etc/passwd

Searches /etc/yum.conf for lines that begin with a # character. This typically finds comment lines.

1.  grep "^#" /et/yum.conf

Excluding Comments and Empty Lines

- Displays all lines from /etc/httpd/conf/httpd.conf except those that contain the character anywhere in the line. Useful for filtering out inline comments.

1.  grep -v '#' /etc/httpd/conf/httpd.conf

- Shows only the non-empty lines from /etc/ssh/sshd_config. The caret^and dollar sign $ together match empty lines, and -v excludes them.

1.  grep -v '^$' /etc/ssh/sshd_config

- Filters /etc/ssh/sshd_config to exclude both empty lines and comment lines (those starting with #). The extended regex (^#^$) matches lines starting with # or that are empty.

1.  grep -v -E "(^#|^$)" /etc/ssh/sshd_config

Pattern Matching with Wildcards

- Searches /etc/yum.conf for lines that start with the string log. The caret ensures the match is only at the beginning of the line.

1.  grep "^gpgcheck" /etc/yum.conf

- Searches /etc/yum.conf for lines containing the letters followed by any single character. The dot
matches any single character except a newline.

1.  grep "s." /etc/yum.conf

- Searches /etc/yum.conf for lines containing any one character from the set a orn. The square brackets [] define a character class, matching any one character within the brackets.

1.  grep "[an]" /etc/yum.conf

Matching from a File

- Searches url-list.txt for lines that contain the string netzclub.not. This performs a straightforward substring match.

1.  grep netzclub.net url-list.txt

- Searches url-list.txt forlines that match any pattern listed in domain-nane.txt. The f option tells grep to read multiple patterns from a file.

1.  grep -f domain-name.txt url-list.txt

- Displays lines from url-list.txt that do not match any pattern in domain-name.txt. The -v option inverts the match, showing only non-matching lines.

1.  grep -v -f domain-name.txt  url-list.txt

- Searches url-List.txt for lines that contain fixed string matches from domain-name.txt (no regex Interpretation), and saves matching lines to matching-urls.tst. The -F treats patterns literally, and -f read pattern from a file.

1.  grep -Ff domain-name.txt url-list.txt > matching-urls.txt

reach pattern

- Character Classes
 
1.  grep "[[:upper:]]" user.txt #uppercase
2.  grep "[[:lower:]] user.txt #lowercase
3.  grep "[[:digit:]] user.txt       # 0-9
4.  grep "[[:alnum:]] user.txt      #latter+digit
5.  grep "[[:space:]] user.txt      # whitespace
6.  grep "[[:alpha:]] user.txt      # A-Z and A-Z

Grep with Process and Network Commands

- Filters the output of ifconfig to show only lines containing inet (IPv4 addresses), while excluding any lines related to inet6 (IPv6).

1.  ifconfig | grep inet | grep -v inet6

- Displays all running processes that have the string root anywhere in their details .This includes processes run by root and processes mentioning root in arguments.

1.  ps-aux | grep root

- Shows all running processes excluding those that mention root anywhere in their details. This is the inverse of the previous command

1.  ps -aux grep -v root

- Displays only the processes whose owner is exactly root. The caret ensures the match occurs at the beginning of the line, where the username appears in ps-aux output

1.  ps -aux | grep "^root"

Recursive Search

- Recursively searches the /etc/directory for files containing the exact string armour. The -r option enables recursive search.

1.  grep -r armour" /etc/

- Recursively searches all files under /etc/ (including subdirectories) for the string root, Ignoring case (-1), and displays the filename, line number, and matched line (-n). Errors (like permission denied) are suppressed by redirecting them to /dev/null

1.  grep -irn root /etc/* 2> /dev/null

- Recursively searches all files under /etc/for the string root, Ignoring case (-1), and only displays filenames that contain matches(-1) Errors are suppressed 

1.  grep -ilt root /etc/* 2> /dev/null

File and Line Number Output

- Searches all files ending with sslscan. Log in the current directory for the string TLSv1.1 and displays only the filenames that contain a match.

1.  grep -1 "TLSv1.1" *sslscan.log

- Recursively searches all files under /etc/for the string armour, and shows matching lines with line numbers. The nit options enable line numbering and recursive search.

1.  grep -nR "armour" /etc/

- Recursively searches the /var/www/html/php directory for the string exec. Useful for detecting usage of potentially dangerous functions in PHP code.

1.  grep -r "exec" /var/www/html/php

Output Matching Strings Only (-o)

1.  grep [0-9][0-9][0-9][0-9] passwd -o

Tips

- Use -i for case-insensitive matches.

- Use -v to invert match (lines not containing the pattern).

- Use -E for extended regular expressions.

- Combine grep, sort, uniq, awk, cut, and sed for advanced string processing.

Extract file extensions:

1.  ls | cut -d ',' -f 2

- Shows the full contents of the CSV file.

1.  cat users.csv

- Extract the first column (ID) from the CSV file.

1.  cut -d ',' -f 1 users.csv

- Extracts the second column (first name).

1.  cut -d ',' -f 2 users.csv

Extracts the third column (last name).

1.  cut -d ',' -f 3 users.csv

- Extracts the first, second, and third columns (ID, first name, last name).

1.  cut -d ',' -f 1,2,3 users.csv

- Same as above, using a range.

1.  cut -d ',' -f 1-3 users.csv

- Extracts the first and fourth columns (ID and email).

1.  cut -d ',' -f 1,4 users.csv

- Saves the output (ID and email) to a new file.

1.  cut -d ',' -f 1,4 users.csv > my-csv2.csv

Text File with Space Separator (my-users.txt)

- Shows the full content of the space-separated beer data file.

1.  cat my-users.txt

Extracts the first field (ID) using default tab delimiter.

1.  cut -f 1 my-users.txt

- Extracts ID, first name, and last name using space as the delimiter.

1.  cut -d ' ' -f 1-3 my-users.txt

System Files and /etc/passwd

- Extracts only usernames from /etc/passwd.

1.  cut -d ':' -f 1 passwd

- Extracts username, home directory, and shell.

1.  cut -d ':' -f 1,6,7 passwd

- Extracts the first field (username) from a comma-separated file.

1.  cut -f1 -d, db.txt
System Files and /etc/passwd

Extracts only usernames from /etc/passwd.

1.  cut -d ':' -f 1 passwd

- Extracts username, home directory, and shell.

1.  cut -d ':' -f 1,6,7 passwd

- Extracts the first field (username) from a comma-separated file.

1 cut -f1 -d, db.txt

- Extracts the second field from a comma-separated file.

1.  cut -f2 -d "," db.txt
 
- Extracts the first and second fields.

1.  cut -f1,2 -d, db.txt

- Extracts the first and third fields.

1.  cut -f1,3 -d, db.txt

- Extracts the first three fields.

1.  cut -f1-3 -d, db.txt

- Extracts fields 1, 2, and 4.

1.  cut -f1-2,4 -d, db.txt

- Extracts fields 1-2 and 3-4 (overlapping ranges).

1.  cut -f1-2,3-4 -d, users.csv

- Show Just usernames from /etc/passwd.

1.  cut -d : -f 1 passwd

- Extract username and fields 5-7.

1 cut -d : -f 1,5-7 passwd

Interface Info from ifconfig

- Shows the first field from each line of ifconfig.

1.  ifconfig cut - f1 -d" "
 
- Extracts the first three fields.

1.  ifconfig | cut -f1-3-d" "

- Extracts usernames from /etc/passwd.

1.  cut - f1-d ":" /etc/passwd

- Extracts fields 1 through 4.

1.  cut -f1,2,3,4-d ":" /etc/passwd

- Alternative format with pipe:

1.  cat passwd | cut -f 1 -d ":"
 
- Extract fields 1, 5, 6, and 7.

1.  cat passwd | cut -f 1,5,6,7 -d":"

- Extract all 7 fields.

1.  cat passwd cut -f1-7 -d":"

*Network Info* 

- Extracts the 10th field from lines containing inet.

1.  ifconfig | grep "inet"| cut -f10 -d" "

- Equivalent command with reordered flags.

1.  ifconfig | grep "inet" | cut -

d" " -f10

- Extracts the MAC address (assumed at field 10) from lines with ether.

1.  ifconfig | grep ether | cut -f 10 -d" " 

- Extracts the 13th field (typically the netmask).

1. ifconfig | grep netmask | cut -f 13 -d' '

- Extracts the first field from lines with MTU info.

1.  ifconfig | grep mtu | cut -f1 -d " "

*Filesystem Indexing with find and cut*

- Generates a list of all files.

1.  find /

- Saves all file paths to a file.

1. find / > fileindex.db

- Counts the number of line(files).

1.  cat fileindex.db | wc -l

- Alternative syntax:

1.  wc -l fileindex.db

- Extracts the second-level directory from the paths.

1.  cat fileindex.db | cut -d "/" -f 2

- Extracts the first and second levels.

1.  cat fileindex.db | cut -d "/" -f1,2

- Sorts and duplicate first two levels.

1.  cat fileindex.db | cut -d "/" -f 1,2 | sort -u

- Lists second-level dirs uniquely.

1.  cat fileindex.db | cut -d "/" -f 2 | uniq

- Sorted unique first two fields.

1.  cat fileindex.db | cut -d "/" -f 1,2 | sort | uniq

- Counts unique occurrences of second-level directories.

1.  cat fileindex.db | cut -d "/" -f 2 | uniq -c

- Filters for /root directory entries.

1.  grep "^/root" fileindex.db

- Filters and deduplicates entries under /root/d1.

1.  cut -d "/" -f1,2,3,4 fileindex.db | grep "^/root/d1" | uniq

- Lists full path starting with /root.

1.  cut -d "/" -f1- fileindex.db | grep "^\/root" | sort -u

- Counts and sorts second-level directories by usage.

1.  cat fileindex.db | cut -d "/" -f 2 1 uniq -c sort-n-r

- Filters third-level home directory entries.

1.  cat fileindex.db | cut -d "/" -f1-3 | uniq | grep home

- Filters and sorts entries under /etc.

1.  cat fileindex.db | cut -d "/" -f1-3 1 unia | grep "^/etc"

- Sorted unique entries under /etc.

1.  cut -d "/" -f1 -fileindex.db | grep "^\/etc" sort -u

- Filters entries under /etc/yum.repos.d.

1.  cat fileindex.db | cut -d "/" -f1-4 | uniq | grep "^/etc/yum.repos.d"

- Escaped grep for /etc/yum.repos.d.

1.  cut -d "/" -f1 -fileindex.db | grep "^\/etc\/yum\.repos\.d" | sort -u

*Path and Extension Filters*

- Filters paths containing home.

1.  grep home fileindex.dh

Filters paths explicitly inside/home/.

1 grep "/home/" fileindex.db

Filters paths that start with /home/.

1 grep "^/home/" fileindex.db

- Gets top 3 path components under/home.

1.  grep "^/home" fileindex.db | cut -f1,2,3 -d "/" | sort -u

- Same as above, without sorting.

1.  grep "^/home" fileindex.db | cut -f 1,2,3 -d "/" | uniq

- Filters entries under/home/infosec.

1.  grep "^/home/infosec" fileindex.db

- Filters and sorts top 3 levels under /etc.

1.  grep "^/etc/" fileindex.db | cut -f 1-3-d "/" | sort -u

* *File Type and Extension Filters*
Finds.db files (basic).

1.  grep ".db$" fileindex.db

- Escaped version (safer and precise).

1.  grep "\.db$" fileindex.db

- Finds.conf files.

1.  grep ".conf$" fileindex.db

- Escaped version of above.

1.  grep "\.conf$" fileindex.db

- Finds.html files.

1.  grep "\.html$" fileindex.db

*Access Logs*

Extracts unique IPs from access log.

1.  cat access.log | cut -d" " -f 1 sort -u

- Counts unique IPs and sorts by frequency.

1.  cat access.log | cut -d" " -f 1 sort uniq -c | sort -urn

- Extracts unique request methods/URLs from a specific IP.

1.  cat access.log | grep '192.168.1.10' | cut -d "\"" -f 2 1 uniq-c

Paste-Command

Paste Command in Linux

The paste command merges lines from multiple files horizontally, combining corresponding lines side by side.

Sample Input Files

1 vim fname.txt

1 Ankit

2 Ayush

3 Dhreeraj

4 Gourav

1 vim lname.txt

1 Sharma

2 Jain

3 Chauhan

4 Joshi

Merges lines from fname.txt and lname.txt using TAB (default delimiter).

1.  paste fname.txt lname.txt

- Merges using a space as the delimiter.

1.  paste -d" " fname.txt lname.txt

- Merges using a hyphen as the delimiter.

1.  paste -d"-" fname.txt lname.txt

- Merges using an underscore as the delimiter.

1.  paste -d "_" fname.txt lname.txt

- Merges using a slash as the delimiter.

1.  paste -d "/" fname.txt lname.txt

- Invalid usage - no delimiter provided, which causes an error.

1.  paste -d "" fname.txt lname.txt

- Merges using a space and redirects the output to fullname.txt.

1.  paste -d" " fname.txt lname.txt > fullname.txt

AWK-Command-in-Linux

The awk command is a powerful pattern scanning and processing language used for text and data extraction, particularly from files with structured content.

1 awk 'BEGIN {.....}
# Executed once before input 
2 {.....}
# Executed for every line 
3 END {....}'
# Executed once after input 

Example:
1.  awk 'BEGIN{print "start print"} {print $0} END{print "End print"}' file.txt

## *Basic Printing*

- Prints all lines from /etc/passwd.

1.  awk '{print $0}'/etc/passwd

- Prints all lines from both /etc/passwd and /etc/shadow.

1.  awk '{print $0}' /etc/passwd /etc/shadow

*Using Field Separator (-F)*

- Prints the first field (username) using colon as the delimiter.

1.  awk -F: '{print $1}' /etc/passwd /etc/shadow

- Prints username and full name (fields 1 and 5).

1.  awk -F: '{print $1,$5}' /etc/passwd

- Prints username, full name, and home directory (fields 1, 5, 6).

1.  awk -F: '{print $1,$5, $6}' /etc/passwd

 *Pattern Matching*