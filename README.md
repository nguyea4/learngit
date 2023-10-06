# learngit
repo to practice github skills

## TOC
1. [github stuff](#github)
2. [Readme](#readme)

This is a README file. Software people use it to write instructions on how to fetch their code. My team uses it as a "wikipedia" and an explanation document.  
The type of text is called 'Markdown', you learn more at this [cheet shet](https://wordpress.com/support/markdown-quick-reference/), but heres relevant stuff I use  

This is by no means a comprehensive guide. This is the git commands for beginners that I use as I go.  


## github <a id="github"></a>
Try these commands with this git repo to see if you can get the hang of it

### Installing git
I follow [this reference](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)  
Use some linux terminal (On Windows I use Windows subsystem for Linux (WSL)  
And you should be good?

### Getting Git Repo
If you own or are marked as a contributer, you can make changes to the code on your computer and push it up for everyone else to see. Otherwise, you have your own version of the code that is separate.  
You can also have use someone else's folder as part of your project. If Andrew is working on a calculator app and Vivian has a User Interface code, andrew can use vivian's User Interface code as a 'git submodule' and as Vivian updates her code, it will show up in Andrew's code when he updates the submodule.

1. Make(Optional): On github website, make new repository.
2. Clone repo: Make a copy of the repo that points to the git repo that you can access. You may need to have certain ssh/encryption access keys at some company
`git clone https://github.com/nguyea4/learngit`

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

