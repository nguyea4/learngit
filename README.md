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

### Installing git
I follow [this reference](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)  
Use some linux terminal (On Windows I use Windows subsystem for Linux (WSL)  

Configure your account identity. I do this globally. remove `--global` if you want an identity only on a repo
 * Email: `git config --global user.email "youremail@gmail.com"
 * Name: `git config --global user.name "your name"
And you should be good?


### Getting Git Repo
If you own or are marked as a contributer, you can make changes to the code on your computer and push it up for everyone else to see. Otherwise, you have your own version of the code that is separate.  

You can also have use someone else's folder as part of your project. If Andrew is working on a calculator app and Vivian has a User Interface code, andrew can use vivian's User Interface code as a 'git submodule' and as Vivian updates her code, it will show up in Andrew's code when he updates the submodule.  

The general idea behind git is you are committing a change to your own code base that can be merged into the Production-level code after approval.
Make change on a separate branch > Add change to a commit to this branch > Commit to the branch with a message > Push the commit to your branch  

For these steps, my initial folder is `Documents`  

1. Make(Optional): On github website, make new repository.
2. Clone repo: Make a copy of the repo that points to the git repo that you can access. You may need to have certain ssh/encryption access keys at some company
`git clone https://github.com/nguyea4/learngit`. I go to that folder with `cd learngit`
   * I now have a folder `Documents/learngit` with the stuff in the `MAIN` branch
3. Test to make sure you have stuff and can run/see things. Try running  `python3 Hello_World.py`
   * Check all branches with `git branch --all'
   * You should see
   * ~~~
     git branch --all
     * main    [The branch you are on]
     remotes/origin/HEAD -> origin/main  [HEAD is the branch that you are working on. here's its pointing to the Online remote main]
     remotes/origin/main
     ~~~
4. Make a Change.
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
5. Make your own file and make those changes
   * In whatever developer environment/IDE(I'm using notepad textfiles) save a python file `whatevername.py`
   * Code your python file in your IDE
   * See what changes you made: `git status`
    * ~~~
      git status
      On branch hello_world
      Untracked files:
        (use "git add <file>..." to include in what will be committed)
      
              hello_world.py
      
      nothing added to commit but untracked files present (use "git add" to track)
      ~~~ 
   * Add your change to a commit: `git add whatevername.py`.
    * You can also add whole folders
   * Commit change to your branch: `git commit -m "Title" -m "Description ..........";
    * 'Title' is the main thing people see on the website next to a file change
    * 'Description' is if you want to explain in more detail what change was made
    * ~~~
      git commit -m "Added Hello_World file" -m "It Prints out 'Hello, from Andrew'"
        [hello_world ded0e41] Added Hello_World file
         1 file changed, 1 insertion(+)
         create mode 100644 hello_world.py
      ~~~
   * Push commit to branch: `git push`
    *  It probably will tell you that there is no upstream for your new branch. This means your local branch needs to connect with the online repo branch. It will suggest making a branch with the same online that your local branch connects to with ` git push --set-upstream origin hello_world`
    *  EDIT: I ran into problems with authentication needing to make a token. I followed [this instruction](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens) given by the terminal. Follow whatever they suggest. Still figuring out how this work.

## Markdown README file  <a id="readme"></a>
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

