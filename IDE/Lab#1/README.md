# IDE Laboratory Work #1

## Subject

Command Line Interface; CLI Editors; Setting Server Environment; Version Control Systems

## Objectives:
  - Understanding and using CLI (basic level)
  - Administration of a remote linux machine using SSH
  - Ability to work remotely (remote code editing)
  - Ability to work with VCS

## Executed Tasks:
  - **Mandatory Tasks:**
    - Connect to a remote server via SSH
    - Initialize a repository on server
    - Create a file in repository folder, write in your name, save it and commit it
  - **Tasks With Points:**
    - Connect to server using public key (1 pt)
    - Create 2 more branches with at least one unique committed file per branch (1 pt)
    - Set a branch to track a remote origin on which you are able to push (ex. github, bitbucket or a custom server) (1 pt)
    - Reset a branch to previous commit, reset a branch to some specific commit (1 pt)
    - Restore a reset branch back to its previous state (1 pt)
    - Create a VCS alias (1 pt)
  - **Additional Tasks:**
    - Referencing to commits using branch titles

## Theoretical Work:

As I'm using CLI and VCS for the last few years all the solutions were familiar to me. Even if something new was encountered it wasn't a problem to read some documentation and do it. It is worth to say that this experience comes more from using Unix based systems than Windows. However I felt that my CLI (OS X default bash) could be better. I didn't built my own CLI, I just looked for something more _famous_ thus ending up with **zsh**. Actually [_oh-my-zsh_](https://github.com/robbyrussell/oh-my-zsh) that I really recommend for a better life.

By using CLI I had to work on remote machines so I got familiar with SSH. However I could never say that I really know it. It was too simple to have a need to dig in details. A simple `ssh user@ip:port` followed by _insert your password_ was more than enough in 99% of cases. In case of using a connection more often or in case of need to execute remote commands automatically it was a good practice to use public keys. First setup may seem hard, but it is really a piece of cake. However SSH is much more powerful one particularly useful command that I love is SSH tunneling. You can create a SOCKS proxy tunnel just by typing `ssh -D 8080 user@server.at.home -p 443`.

I'm definitely not an expert with any VCS (I'm using GIT on daily basis) even if I'm using them for the last 3-5 years. I had some experience with SVN but it was long ago, it was on Windows through Tortoise SVN and each movement was like walking on minefield. At some point it began to be fun. Latter I switched to GIT (and GitHub). Hence I used once Mercurial: I needed a source of some tool and it was available only as googlecode Mercurial repository. So I installed Mercurial, cloned project and forgot about it. But it may be a good idea to revise it as it seems that there are forces (facebook) who found it as a powerful tool and now invest in it. Back to business: by using GIT for some time and reading its main documentation book I can say that I feel comfortable with it. Also I had some fun finding out and trying some tools like _bisect_ and _cherry-pick_. Once I was updating a project that was 1k commits ahead. It took me 4 hours to solve all conflicts, but without knowing right tools it could be much more (or even impossible).

## Practical Work:

### Connect to a remote server via SSH

This one is easy. As I'm using OS X that has ssh by default connecting to a remote machine via SSH is done by running a command like `ssh user@ip:port`


### Initialize a repository on server

`git init`

### Create a file in repository folder, write in your name, save it and commit it

This one is quite nice. Now I understand the joke: _I'm working in VIM for 3 years because have no idea how to quit it_.

```
vim file.txt
i
Truhin Alexandr
Ctrl+c
:wq
git add file.txt
git commit -m "added file with my name"
```

### Connect to server using public key (1 pt)

This is one really useful, secure and time-saver feature. Generate a public/private key pair, register your public key on remote host and add remote host data to git configuration file.

### Create 2 more branches with at least one unique committed file per branch (1 pt)

```
git checkout -b branch1
create and commit a file
git checkout -b branch2
create and commit a file
```

### Set a branch to track a remote origin on which you are able to push (ex. github, bitbucket or a custom server) (1 pt)

```
git remote add origin git@github.com:TUM-FAF/FAF-081-Truhin-Alexandr.git
git push -u origin master
```

### Reset a branch to previous commit, reset a branch to some specific commit (1 pt)

There are few reset strategies. Actually there are 3 of them: soft, hard and mixed. It all depends on the purpose. If you created a commit but forgot to add a file to commit you may use soft strategy, however if you want to remove one file from revision you may use soft strategy and then unstage a file or use mixed strategy and add only necessary files. If your commit is not last than you may want first to create a separate branch, reset to that commit, make your changes and then cherry-pick or rebase all the rest of commits. There are many other nice strategies on [Seth Robertson post](http://sethrobertson.github.io/GitFixUm/fixup.html).

### Restore a reset branch back to its previous state (1 pt)

A good review [by our colleague](http://www.code-speculations.me/blog/a/omg_git_reset_hard).

### Create a VCS alias (1 pt)

You may take a look at my aliases [in my dotfiles repo](https://github.com/bumbu/.dotfiles).

### Referencing to commits using branch titles

An good thing to know is that branch names are shortcuts to commits. Also you may refer to commits by pointing how many commits ago it was like `master~2` that is a pointer to third commit from HEAD.

## Conclusions:

Based on the thing that I knew how to do all the tasks I had almost no difficulties executing this laboratory work. However as I'm using GIT aliases it was tricky to remember how to jump between branches. Even now I have no idea how to style GIT log output as I have 5 aliases that cover all my needs. A new thing was switching from default OS X shell to oh-my-zsh. It still looks strange and too colorful to me.
