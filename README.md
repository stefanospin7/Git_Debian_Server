# CREATE A GIT REPO ON LOCAL DEBIAN SERVER

## On your server:


### Install git and create a git user

sudo apt-get install git-all 

sudo adduser git

su git

cd

touch .ssh/authorized_keys && chmod 600 .ssh/authorized_keys


## On personal machine:

### Generate an ssh key:

ssh-keygen -b 4096

cat .ssh/id_rsa.pub

## on server (as git user):

### Copy the id_rsa.pub content from local machine and paste it into authorized_keys:


nano .ssh/authorized_keys

### (Now you should log into git user with ssh without writing the password)

## On server (log as root):

mkdir /srv/git

chown git:git git/


### As git user go to /sr/git dir:

mkdir newRepo.git

cd mkdir newRepo.git

git init --bare


## On personal machine:

cd testGit (project dir)


git init

git add .

### Set your credentials :

git config --global user.email "you@example.com"
git config --global user.name "Your Name"
  
  
 
git commit -m 'my first commit'



git remote add origin git@192.***.***.***:/srv/git/newRepo.git


### Now you can use all the git commands, I suggest to use the GitHub cheat sheet:

https://github.com/stefanospin7/Git_Debian_Server/blob/main/Git%20cheat%20sheet.pdf


