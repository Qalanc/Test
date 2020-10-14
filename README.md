# Version Control with Git

Practical tasks inlude the following steps: 

## I Can Win

* Install Git using web-site [git-scm.com](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) and generate ssh keys using Git Bash:

```bash
$ ssh-keygen -t rsa -C "maksym.karpov@nure.ua"
```

* Add public key into Gitlab profile settings and set up username and email:

```bash
$ git config --global user.name "Maksym Karpov"

$ git config --global user.email "maksym.karpov@nure.ua"
```

* After initial settings create project and clone it to PC:

```bash
$ git clone git@gitlab.com:maksym.karpov/online-python-external-program.git
```
* In project working directory, create the folder named `GIT` and place there `song.txt` file containing the first half of favourite song. Add created file to index, than commit and push to the server:

```bash
$ git add GIT/

$ git commit -m "add first half of my favorite song"

$ git push
```

* With  GitLab web interface, add the second half of text to `song.txt` file and clone remote repository to PC using command:

```bash
$ git pull
```

## Bring It On

* Add `.gitignore` file to project with the following instructions, that hiding files with extensions **.db**, **.log** and directory named **target**:

~~~~
*.db
*.log
/target
~~~~

* Create `feature` branch and commit `.gitignore` file two times with required extensions and directory:

```bash
$ git checkout -b feature

$ git add GIT/

$ git commit -m "created file .gitignore and configured hiding of files with extensions .db, .log"

$ git add GIT/

$ git commit -m "configured hiding directory with name target"
```

* Merge `feature` branch into `master`, previously switched to `master` branch:

```bash
$ git checkout master

$ git merge feature
```

* Return to "feature" branch:

```bash
$ git checkout feature
```

* Create `arrows.txt` file and commit:

```bash
$ git add GIT/

$ git commit -m "created file arrows.txt on feature branch and added 2 strings of song"
```

* Go to `master` branch, create `arrows.txt` file and commit:

```bash
$ git checkout master

$ git add GIT/

$ git commit -m "created file arrows.txt on master branch and added 2 strings of song"
```

* Mearging `feature` branch into master, raise conflict in `arrows.txt`, to solve the conflict go to arrows.txt file in `master` branch and edit text in order previous steps. Edited file add to index and commit.

```bash
$ git merge feature
CONFLICT (add/add): Merge conflict in GIT/arrows.txt
Auto-merging GIT/arrows.txt
Automatic merge failed; fix conflicts and then commit the result.
```

```bash
$ git add GIT/

$ git commit -m "solved merge conflict"
```

## Hurt Me Plenty

* Create `storm` branch, `storm.txt` with two strings and commit file:

```bash
$ git checkout -b storm

$ git add GIT/

$ git commit -m "created storm.txt and added two strings"
```

* Add two more strings to `storm.txt` file and commit:

```bash
$ git add GIT/

$ git commit -m "added two more strings"
```

* Switch to `master` branch, create `pursuit.txt` file with four strings, commit:

```bash
$ git add GIT/

$ git commit -m "created file pircuit.txt and added four strings"
```
* Mark the commit with the session1 tag and go to the `storm` branch:

```bash
$ git tag session1
```

* To rebase the `storm` branch with the latest commit from `master`, switch to `storm` and use Git commands:

```bash
$ git checkout storm

$ git rebase master
```

## Hardcore

* Synchronizing local project and remote using the Git command:

```bash
$ git push
```
* View of existing repository:

```bash
$ git remote -v

origin  git@gitlab.com:maksym.karpov/online-python-external-program.git (fetch)
origin  git@gitlab.com:maksym.karpov/online-python-external-program.git (push)
```

* Remove old project, create new and add it to origin:

```bash
$ git remote remove origin

$ git remote add origin git@gitlab.com:maksym.karpov/online-python-external-program-for-git.git
```

* Push files from old project to new repository:

```bash
$ git push --set-upstream origin master
```

Old and new projects have tha same files/

## Nightmare!

Last practical task complete at the same way as previous four, but without using text editors and file managers.

* Use Unix commands:

  * `cd` to change directory:

  ```bash
  $ cd GIT/
  ```

  * `cat` to view content of file:
  
  ```bash
  $ cat pursuit.txt
  The warming sun returns again
  And melts away the snow
  The sea is freed from icy chains
  Winter is letting go
  ```
  
  * `vi` to edit file
  
  ![Vi Editor](https://github.com/Qalanc/Test/blob/main/vi.jpg)
