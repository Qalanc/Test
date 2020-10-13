# Version Control with Git

My execution steps of practical tasks Version Control with Git

## I Can Win

I installed Git using web-site [git-scm.com](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) and generated ssh keys using Git command:

```bash
ssh-keygen -t rsa -C "maksym.karpov@nure.ua"
```

The next step was to add my public key into Gitlab profile settings and set up username and email:

```bash
git config --global user.name "Maksym Karpov"

git config --global user.email "maksym.karpov@nure.ua"
```

When I did initial settings I had to create project and clone it to my PC:

```bash
git clone git@gitlab.com:maksym.karpov/online-python-external-program.git
```
Using project working directory, I created folder GIT and placed there file song.txt with first half of song. Created file I added to index, than made commit and push to the server:

```bash
git add GIT/

git commit -m "add first half of my favorite song"

git push
```

Using GitLab web interface I added second half to song.txt and cloned remote repository to my PC using command:

```bash
git pull
```
