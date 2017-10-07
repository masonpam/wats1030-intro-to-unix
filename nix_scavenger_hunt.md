# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox.

home/cabox/workspace

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. 

LICENSE  README.md  challenge_files  nix_scavenger_hunt.md  nix_scavenger_hunt_stretch.md  super_scavengers.md

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory.        

drwxrwxr-x 4 cabox cabox 4.0K Oct  2 22:19 .
drwxr-xr-x 7 cabox cabox 4.0K Oct  2 22:19 ..
drwxrwxr-x 8 cabox cabox 4.0K Oct  2 22:19 .git
-rw-rw-r-- 1 cabox cabox 1.1K Oct  2 22:19 LICENSE
-rw-rw-r-- 1 cabox cabox 2.7K Oct  2 22:19 README.md
drwxrwxr-x 7 cabox cabox 4.0K Oct  2 22:19 challenge_files
-rw-rw-r-- 1 cabox cabox 5.5K Oct  4 17:30 nix_scavenger_hunt.md
-rw-rw-r-- 1 cabox cabox  317 Oct  2 22:19 nix_scavenger_hunt_stretch.md
-rw-rw-r-- 1 cabox cabox  191 Oct  2 22:19 super_scavengers.md

* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://linux.die.net/man/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*

ls -a, --all: do not ignore entries starting with (.)
ls -l: use a long listing format 
ls -h: print sizes in human readable format
* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. 

ls /
bin  boot  dev  etc  fastboot  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:* 

/home/cabox

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*

workspace

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?* 

3 files, 2015_special_stuff.demo  cloaked-wookie.demo scooter-double-mamba.demo

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now? **/home/cabox/workspace**
* Press the up arrow on your keyboard. *What just happened? It gave me the last command that I used*
* Press the up arrow a few more times. *What do you see?* 

It went through all the commands that I used recently

* Run the `history` command. *What do you see?* 

Gives me a list of the commands that I have used

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?* 

cabox

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here: 

cabox    pts/0        Oct  6 19:38 (52.161.27.120)

* How long has your system been running? Use `uptime` to see, and *paste the result here:* 

23:41:40 up  3:10,  1 user,  load average: 0.00, 0.00, 0.00

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?* 
A list of all processes in the system
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root         1  0.0  0.4  33200  2544 ?        Ss   20:31   0:00 init
root         2  0.0  0.0      0     0 ?        S    20:31   0:00 [kthreadd/133879]
root         3  0.0  0.0      0     0 ?        S    20:31   0:00 [khelper/1338790]
root       153  0.0  0.1  19428   840 ?        S    20:31   0:00 upstart-udev-bridge --daemon
root       167  0.0  0.2  49216  1420 ?        Ss   20:31   0:00 /lib/systemd/systemd-udevd --daemon
syslog     296  0.0  0.2 184188  1436 ?        Ssl  20:31   0:00 rsyslogd
root       408  0.0  0.5  61316  3052 ?        Ss   20:31   0:00 /usr/sbin/sshd -D
root       417  0.0  0.1  15492   864 ?        S    20:31   0:00 upstart-file-bridge --daemon
root       419  0.0  0.1  15604   964 ?        S    20:31   0:00 upstart-socket-bridge --daemon
root       435  0.0  0.1  12740   840 tty1     Ss+  20:31   0:00 /sbin/getty 38400 console
root       437  0.0  0.1  12740   844 tty2     Ss+  20:31   0:00 /sbin/getty 38400 tty2
root       456  0.0  0.6  63876  3308 ?        Ss   23:09   0:00 sshd: cabox [priv]
cabox      458  0.0  0.2  64140  1520 ?        S    23:09   0:00 sshd: cabox@notty
cabox      459  0.0  0.1  12784   884 ?        Ss   23:09   0:00 /usr/lib/openssh/sftp-server
root       460  0.0  0.6  63876  3460 ?        Ss   23:11   0:00 sshd: cabox [priv]
cabox      462  0.0  0.2  63876  1472 ?        S    23:11   0:00 sshd: cabox@pts/0
cabox      463  0.0  0.3  18128  2032 pts/0    Ss   23:11   0:00 -bash
cabox      481  0.0  0.2  15520  1144 pts/0    R+   23:44   0:00 ps aux
* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?* 
Shows tasks managed in real time and processor activity
top - 23:56:56 up  3:25,  1 user,  load average: 0.00, 0.00, 0.00
Tasks:  18 total,   1 running,  17 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni,100.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
KiB Mem:    524288 total,    24192 used,   500096 free,        0 buffers
KiB Swap:   524288 total,        0 used,   524288 free.    17692 cached Mem

  PID USER      PR  NI    VIRT    RES    SHR S  %CPU %MEM     TIME+ COMMAND
    1 root      20   0   33200   2544   1436 S   0.0  0.5   0:00.28 init
    2 root      20   0       0      0      0 S   0.0  0.0   0:00.00 kthreadd/133879
    3 root      20   0       0      0      0 S   0.0  0.0   0:00.00 khelper/1338790
  153 root      20   0   19428    840    596 S   0.0  0.2   0:00.03 upstart-udev-br
  167 root      20   0   49216   1420    944 S   0.0  0.3   0:00.00 systemd-udevd
  296 syslog    20   0  184188   1436    940 S   0.0  0.3   0:00.00 rsyslogd
  408 root      20   0   61316   3052   2372 S   0.0  0.6   0:00.00 sshd
  417 root      20   0   15492    864    400 S   0.0  0.2   0:00.00 upstart-file-br
  419 root      20   0   15604    964    416 S   0.0  0.2   0:00.00 upstart-socket-
  435 root      20   0   12740    840    692 S   0.0  0.2   0:00.00 getty
  437 root      20   0   12740    844    700 S   0.0  0.2   0:00.00 getty
  456 root      20   0   63876   3308   2556 S   0.0  0.6   0:00.00 sshd
  458 cabox     20   0   64140   1532    712 S   0.0  0.3   0:00.01 sshd
  459 cabox     20   0   12784    884    656 S   0.0  0.2   0:00.00 sftp-server
  460 root      20   0   63876   3460   2708 S   0.0  0.7   0:00.00 sshd
  462 cabox     20   0   64008   1492    728 S   0.0  0.3   0:00.08 sshd
  463 cabox     20   0   18128   2032   1540 S   0.0  0.4   0:00.01 bash
  482 cabox     20   0   19852   1472   1068 R   0.0  0.3   0:00.04 top

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?* 

2 files, credit_cards.txt credit_cards2.txt

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*

1-15-2015

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located? 

In the tmp sub-directory, ./tmp/modi_laboriosam.txt

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?* 

2 files, Britt-Erdman.user:O'Harachester, WA 37261 Lissie-Strosin.user:Jewessfurt, WA 00816-7241

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*  

grep -r Waldo
serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidunt. Explicabo vel esse blanditiis dolorem culpa non quia.

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?* 

A list of all the names of the files in the directory

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.* 

A list of the current directory that fits into one screen and can scroll as needed

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:* 
root       545  0.0  0.6  63876  3304 ?        Ss   21:17   0:00 sshd: cabox [priv]
cabox      547  0.0  0.2  64008  1496 ?        S    21:17   0:00 sshd: cabox@notty
cabox      548  0.0  0.1  12776   844 ?        Ss   21:17   0:00 /usr/lib/openssh/sftp-server
root       582  0.0  0.6  63876  3456 ?        Ss   21:36   0:00 sshd: cabox [priv]
cabox      584  0.0  0.2  63876  1468 ?        S    21:36   0:00 sshd: cabox@pts/0
cabox      585  0.0  0.3  18156  2068 pts/0    Ss   21:36   0:00 -bash
cabox      598  0.0  0.2  15520  1144 pts/0    R+   21:41   0:00 ps aux
cabox      599  0.0  0.1   8816   744 pts/0    S+   21:41   0:00 grep --color=auto cabox

