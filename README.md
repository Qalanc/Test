# Version Control with Git

Practical tasks 

## I Can Win

Install Git using web-site [git-scm.com](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) and generate ssh keys using Git Bash:

```bash
ssh-keygen -t rsa -C "maksym.karpov@nure.ua"
```

Add public key into Gitlab profile settings and set up username and email:

```bash
git config --global user.name "Maksym Karpov"

git config --global user.email "maksym.karpov@nure.ua"
```

After initial settings create project and clone it to PC:

```bash
git clone git@gitlab.com:maksym.karpov/online-python-external-program.git
```
In project working directory, create folder named GIT and place there "song.txt" file containing first half of favourite song. Add created file to index, than made commit and push to the server:

```bash
git add GIT/

git commit -m "add first half of my favorite song"

git push
```

With  GitLab web interface, add second half of text to "song.txt" file and clone remote repository to PC using command:

```bash
git pull
```
