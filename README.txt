Autocommit is a program that automatically commits everything that you put into
a directory

--------------------------------------------------------------------------------

So, let's say that you're writing a book, and you're doing it on pencil and
paper. Every word that you write down gets recorded onto the paper. Every letter
and accidental scratch mark gets onto the paper, and you've got to cross out all
the words and paragraphs that you don't think worked well, and rewrite them in a
different way. In the end, you've got the final product of the book that you
wrote, but you've also got a record of every mess-up that you've made along the
way. You've got an eraser, so you can erase all the ugly sections and make the
text look OK in the end.

That's kinda what autocommit is.  It's like writing a novel in pencil.

--------------------------------------------------------------------------------

Autocommit uses the last history command as the git message, so you can know
what you typed, and what you edited.

In the cases where you edit a file outside of bash, like in vi or emacs, there's
a notify daemon spawned
which will pop up a zenity dialog to enter a commit message prior to committing.
You can hit escape to make the zenity dialog go away, but don't do that.  It
goes against the reasons for writing
in pencil.

Added bonus: you can still put your own text into the commit message by ending
the command with # followed by the comment

New feature: changed PS1 so that we know we're autocommitting

--------------------------------------------------------------------------------
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
