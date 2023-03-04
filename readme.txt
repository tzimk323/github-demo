Είχα προτζεκτ
git init
ftiaxnw sto remote
git commit
git pull https://github.com/tzimk323/lastmlyTest main --allow-unrelated-histories
git push https://github.com/tzimk323/lastmlyTest main


git version
    git version 2.33.0.windows.2


git config --global user.name "jim"
git config --global user.email "tzim323@gmail.com"


//pairnw link απο Github
git clone https://github.com/tzimk323/github-demo.git

Σε ποιο branch είμαι:
git status
εμφανίζει¨:
On branch main

No commits yet


Commit:
    git commit -am "DFFDFD"

πως να προσθέσεις νεα αρχεία στο staging:
    git add fileName

Για να ξε add το file:
    git restore --staged <file>

πως να προσθέσεις νεouς φακέλους στο staging (recoursively):
    git add .

ορίζω το default branch
    git config --global init.defaultBranch main
    git push origin main

Cloning
    git clone https://github.com/libgit2/libgit2

πως να δείς τις ρυθμίσεις σου:
    git config --global --list

εμφανίζει
    filter.lfs.clean=git-lfs clean -- %f
    filter.lfs.smudge=git-lfs smudge -- %f
    filter.lfs.process=git-lfs filter-process
    filter.lfs.required=true
    user.name=jim
    user.email=tzim323@gmail.com



create new repository
    git init another-example
δημιουργεί ένα φάκελο και μέσα τον φάκελο .git  (είναι κρυφός)

ορίζω default editor
    git config --global code.editor "notepad++.exe multiInst -nosession"
vc


αρα για project σε νέο:
    1.φτιάχνω στο  remote ένα repo
    2.κάνω git init another-example
    3.σπρώχνω στο repo μου

πως να δείς τα remote branches σου
    git branch -r

πως να δείς τα remote branches σου kai ta local mazi
 git branch -a

εμφανίζει:
    origin/HEAD -> origin/main
    origin/main



πως να δείς τα local branches sou
    git branch -l



git repo σε ηδη existing project (αν υπάρχει ηδη git file τοτε κανει reinitialize):
    git init


Fork
    copy of a repository to our personal space (mporeis an thes na to ananewneis apo to arxiko) fgf


git config file:
    C:\Users\tzim3\.gitconfig

EXAMPLE:

    [init]
        defaultBranch = main
    [difftool "sourcetree"]
        cmd = "'' "
    [mergetool "sourcetree"]
        cmd = "'' "
        trustExitCode = true
    [code]
        editor = C:\\Program Files (x86)\\Notepad++\\notepad++.exe



δες όλα τα files π είναι staged
	git ls-files


αν θελω να πάρω πίσω git add σε file
	git reset HEAD test.txt

αν θελω να πάρω πiσω αλλαγες σε file (p itan sto proigoumeno commit)
	git checkout -- test.txt

αν θελω να μετονομάσω αρχείο (σε os level, και κανει stage oti einai renamed) , σε περιπτώση π το κάνω διαφορετικά το git to βλέπει
σαν δυο πράξεις: 1. οτι το αρχειο εγινε delete, 2. oti dimiourgithike ena allo arxeio
    git mv fdfdgf.txt gfgfgf.txt


    ???????????? kati oti katalavainei oti exei ginei renamed en teli
    git add filename
    git add -u


git add A???????


remove file
    git rm newfile.txt

    an thelw na anairesw to delete
git reset Head filename

What is git rebase? Rebasing is the process of moving or combining a sequence of commits to a new base commit.
 Rebasing is most useful and easily visualized in the context of a feature branching workflow.



---------------------------history functions
    git log

εμφανίζει:
commit 578fb021849dba42120e47655a49c60b572bc9ef
Author: jim <98760445+dmKonstant@users.noreply.github.com>

commit f293da9db7de86c66e7f3476346e7bb62af55722
Author: jim <tzim323@gmail.com>
Date:   Wed Feb 15 21:46:46 2023 +0200


ενώ το git log --abbrev-commit

    εμφανίζει με μικρότερο hash

PS C:\Users\tzim3\Desktop\Projects\gitrepo\github-demo> git log --abbrev-commit
commit f9776f3 (HEAD -> main)
Author: jim <98760445+dmKonstant@users.noreply.github.com>
Date:   Thu Mar 2 21:02:47 2023 +0200

    windows

commit ed2ff76 (origin/main, origin/HEAD)
Author: jim <98760445+dmKonstant@users.noreply.github.com>
Date:   Wed Mar 1 22:20:07 2023 +0200




git log --oneline --graph --decorate

       εμφανίζει (PROSEKSE LEEI K POTE STO REMOTE)
    * f9776f3 (HEAD -> main) windows
    * ed2ff76 (origin/main, origin/HEAD) DF
    * 300ef18 hgh
    * 3a615ac hgh
    * cf0adb2 Ffd
    * 578fb02 df
    * 3bf7626 FD
    * 7cfb16e asds
    * f293da9 DFFDFD
    * f3c7f30 Initial commit


git log --since="3 days ago"

MONO GIA AUTO TO FILE COMMITS
git log readme.txt


Δείχνει τι έχει αλλάξει σε ένα commit

git show 300ef18703f801da230b59ab9827fd3f6df55cc8



----git alias---
πρόσεξε οτι βγάζεις το git απο το string
    git config --global alias.hist "log --oneline --graph --decorate"

και μετά πατάω απλα git hist
ή απλα το βάζω στο config file

[alias]
	hist = log --oneline --graph --decorate




-----GIT IGNORE----
ftiakse file:
.gitignore

κάθε γραμμή και file
μπορω και πολλά files
    *.txt
kαι φάκελο
    folder/
νομιζω οτι δν πρέπει να είναι add



Rename branch
    git branch -m main

Delete branch (nomizw kai apo remote kai apo local)
    git branch -D main

ADD ALL FILES
    git add -A

Checkout to a brunch
    git checkout --orphan latest_branch

delete all commit history and go to main

Deleting the .git folder may cause problems in your git repository. If you want to delete all your commit history but keep the code in its current state, it is very safe to do it as in the following:
Checkout
        git checkout --orphan latest_branch
Add all the files
        git add -A
Commit the changes
        git commit -am "commit message"

Delete the branch

        git branch -D main

Rename the current branch to main

        git branch -m main

Finally, force update your repository

        git push -f origin main

PS: this will not keep your old commit history around


OTAN ERROR :
Username for 'https://github.com': dmKonstant
Password for 'https://dmKonstant@github.com':
remote: Support for password authentication was removed on August 13, 2021.

TOTE APLA VALE ANTI GIA KODIKO TO PERSONAL ACCESS TOKEN

MULTI PULL ALIAS
alias multipull='find . -mindepth 1 -maxdepth 1 -type d -print -exec git -C {} pull \;'
mporw na valw epilogi autostash
mporw na valw ektos apo ekei p eimai?
mporw otan exei merge ekei p eimai na me petaei?



REMOVE UNTRACKED FILES
    git clean -fd
To recap, git clean is a convenience method for deleting untracked files in a repo's working directory.


-----------DES DIAFORES----------------------
    git diff --staged HEAD   (STAGED AREA TO HEAD dld last commit)

git diff

MONO GIA ENA FILE
    git diff file


Diff se commits

to head me head -1 commit
    git diff HEAD HEAD^

Diafores se duo commits
git diff b321654 ed2ff76


Diafores se duo local branch and remote
    git diff master origin/master



-------------------GIT BRANCHES AND MERGING------------------


create a branch
    git branch mynewbranch

rename branch:
 git branch -m mynewbranch newbranch

delete branch:
 git branch -d newbranch

go to another branch
     git checkout main

create a branch and checkout to it
    git checkout -b title-change

ADD COPYRIGHT
