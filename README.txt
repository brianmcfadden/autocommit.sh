autocommit is a program that automatically commits everything that you put into a directory


It uses the last history command as the git message, so you can know what you typed, and what you edited.

Added bonus: you can still put your own text into the commit message by ending the command with # followed by the comment

New feature: changed PS1 so that we know we're autocommitting

-------------------------------------------------------------------------------
Script started on 2019-09-13 05:17:53-04:00 [TERM="xterm-256color" TTY="/dev/pts/5" COLUMNS="176" LINES="43"]
brian@fiste:~/Projects$ mkdir autocommit
brian@fiste:~/Projects$ cd autocommit/
brian@fiste:~/Projects/autocommit$ autocommit 
fatal: not a git repository (or any of the parent directories): .git
fatal: not a git repository (or any of the parent directories): .git
brian@fiste:~/Projects/autocommit$ git init .
Initialized empty Git repository in /home/brian/Projects/autocommit/.git/
brian@fiste:~/Projects/autocommit$ cp ~/bin/autocommit .
brian@fiste:~/Projects/autocommit$ cat > README.txt <<EOF
> autocommit is a program that automatically commits everything that you put into a directory
> 
> It uses the last history command as the git message, so you can know what you typed, and what you edited.
> 
> I think that this is either very useful or very, very stupid, and I'm not sure which.
> EOF
brian@fiste:~/Projects/autocommit$ git log
commit 3f32ebe0c131c637e39079c49b7638a468e8e977 (HEAD -> master)
Author: Brian McFadden <brianmmcfadden@gmail.com>
Date:   Fri Sep 13 05:18:26 2019 -0400

    cat > README.txt <<EOF

commit 9a716766e8090ab23ca26c274219d9cf8c72fd94
Author: Brian McFadden <brianmmcfadden@gmail.com>
Date:   Fri Sep 13 05:18:13 2019 -0400

    cp ~/bin/autocommit .
brian@fiste:~/Projects/autocommit$ exit
brian@fiste:~/Projects/autocommit$ exit

Script done on 2019-09-13 05:18:45-04:00 [COMMAND_EXIT_CODE="0"]
-------------------------------------------------------------------------------
