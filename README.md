# learngit
repo to practice github skills
This is a public repo

## TOC
1. [github stuff](#github)
2. [Readme](#readme)

This is a README file. Software people use it to write instructions on how to fetch their code. My team uses it as a "wikipedia" and an explanation document.  
The type of text is called 'Markdown', you learn more at this [cheet shet](https://wordpress.com/support/markdown-quick-reference/), but heres relevant stuff I use  

As a Non-software engineer, I don't have good hygiene. Each company has their own. My coding practice is used here.

This is by no means a comprehensive guide. This is the git commands for beginners that I use as I go.  


## github <a id="github"></a>
Try these commands with this git repo to see if you can get the hang of it

Things I use alot:  
1. **`git status`**
2. **`git branch --all`**
3. **`git checkout branchname`**
4. **`git pull`**
5. **`git add whatevername.py`**
6. **`git commit -m "Title" -m "Description .........."`**
7. **`git push`**

### Install/Setup git
I follow [this reference](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)  
Use some linux terminal (On Windows I use Windows subsystem for Linux (WSL)  

Configure your account identity. I do this globally. remove `--global` if you want an identity only on a repo
 * Email: `git config --global user.email "youremail@gmail.com"
 * Name: `git config --global user.name "username"

Setup SSH key for github
Taken from this [documentation](https://docs.gitlab.com/ee/user/ssh.html#adding-an-ssh-key-to-your-gitlab-account)
1. In terminal go back to biggest folder ever:  `cd`
2. go to ssh folder: `cd .ssh`
3. List files: `ls`
4. (?) Do see a `.pub` file? No(go to step 5), Yes(Go to Step 6)
5. Generate ssh key `ssh-keygen -t ed25519 -C "<comment>"` they suggest your email as the comment
6. Keep clicking enter for whatever they prompt
7. Now you have an ssh key. copy the public key.
   ~~~
   cd
   cd .ssh
   ls
   vim [file ending in .pub]
   copy text
   ~~~
   You now have ssh key in clip board
8. Go to Github website -> Click Top Right profile picture -> Setting -> SSH key -> New SSH Key -> Paste SSH key
9. Save
And you should be good?


### Getting Git Repo
If you own or are marked as a contributer, you can make changes to the code on your computer and push it up for everyone else to see. Otherwise, you have your own version of the code that is separate.  

You can also have use someone else's folder as part of your project. If Andrew is working on a calculator app and Vivian has a User Interface code, andrew can use vivian's User Interface code as a 'git submodule' and as Vivian updates her code, it will show up in Andrew's code when he updates the submodule.  

The general idea behind git is you are committing a change to your own code base that can be merged into the Production-level code after approval.
Make change on a separate branch > Add change to a commit to this branch > Commit to the branch with a message > Push the commit to your branch  

For these steps, my initial folder is `Documents`  

1. Make(Optional): On github website, make new repository.
2. Clone repo: Make a copy of the repo that points to the git repo that you can access. You may need to have certain ssh/encryption access keys at some company
   * My link here has https://github.com/nguyea4/learngit. `user=nguyea4`, `repo=learngit`
   * Template command: `git clone git@github.com:user/repo.git`.
   * `git clone git@github.com:nguyea4/learngit.git`
   * I go to that folder with `cd learngit`
   * I now have a folder `Documents/learngit` with the stuff in the `MAIN` branch
4. Pull repo to get latest updates: **`git pull`**
5. Test to make sure you have stuff and can run/see things. Try running  `python3 Hello_World.py`
   * Check all branches with `git branch --all'
   * You should see
   * ~~~
     git branch --all
     * main    [The branch you are on]
     remotes/origin/HEAD -> origin/main  [HEAD is the branch that you are working on. here's its pointing to the Online remote main]
     remotes/origin/main
     ~~~
6. **Make a Change**.
   * New or Switch branches: Make a new branch and checkout with `git checkout -b branchname`.
     * Never make changes directly into Main. A branch is your playground. the `-b` means new branch
     * If you see the branch you want to work on with someone, just do `git checkout branchname`
     * You should now be on a new branch
   * Test to make sure you can see the new branch if you created `git branch --all`
    *  ~~~~
       git branch --all
       * hello_world
       main
       remotes/origin/HEAD -> origin/main
       remotes/origin/main
       ~~~
    * Now you can make changes and you can test it too
7. Make your own file and make those changes
   * In whatever developer environment/IDE(I'm using notepad textfiles) save a python file `whatevername.py`
   * Code your python file in your IDE
   * See what changes you made: **`git status`**
    * ~~~
      git status
      On branch hello_world
      Untracked files:
        (use "git add <file>..." to include in what will be committed)
      
              hello_world.py
      
      nothing added to commit but untracked files present (use "git add" to track)
      ~~~ 
   * Add your change to a commit: **`git add whatevername.py`**.
    * You can also add whole folders
   * Commit change to your branch: **`git commit -m "Title" -m "Description .........."`**
    * 'Title' is the main thing people see on the website next to a file change
    * 'Description' is if you want to explain in more detail what change was made
    * ~~~
      git commit -m "Added Hello_World file" -m "It Prints out 'Hello, from Andrew'"
        [hello_world ded0e41] Added Hello_World file
         1 file changed, 1 insertion(+)
         create mode 100644 hello_world.py
      ~~~
   * Push commit to branch: **`git push`**
    *  It probably will tell you that there is no upstream for your new branch. This means your local branch needs to connect with the online repo branch. It will suggest making a branch with the same online that your local branch connects to with ` git push --set-upstream origin hello_world`
    *  EDIT: I ran into problems  when pushing. Just look on stackoverflow for your answer. Mine was that I didnt set up SSH.
  8. Changes are now up and can be merged into main
  9. Pull Request: If your branch is behind main(like Main is 3 commits ahead, your branch is 1 commit ahead), you first need to pull the NEW main into your branch and resolve merge. (Insert image)
  10. Merge Request: After your branch is now up to date with more commits ahead of main, you can merge it in. Resolve merge conflicts (insert image)
  11. You have alot of flexibility in who can make changes/approve/timeline etc. Play around with the setting but here are the basics!
  12. You're done!

## Markdown README file  <a id="readme"></a>
This is documentation stuff. Don't worry too much about it now.

use 1 \# [Header], or  \#\# [header2] or \#\#\# [header 3] etc. for smaller headers

To make a "new line" either '\<br\/\>' or '[space][space][enter]' at the end of a line  

To put code here use \` code \` (its the backquote key under esc) like this `python3 test.py`  

Two ways to do block code , surrounding lines in \~\~\~ on top and bottom or \`\`\` like this 
~~~
this is code
this is also code
~~~

You can write symbols like \< and \/ by using backslask('\\')

To hyperlink OUTSIDE of the doc use \[ link \] \( hyperlink \)  

To make a INTERAL hyperlink to jump around document, at end of a line/header put `<a id="nickname"></a>` and you can reference it anywhere with `[text](#nickname)`

