# Notes: Automate Everything: An egghead Guide to Productivity

## Create a Lesson Template

1. Go to CodeSandbox and create a Sandbox.

2. Then we'll create a GitHub repo from this template by signing in with GitHub, forking the Sandbox.

3. From Github, grab the link to clone repo, use `degit`:

```bash
npx degit git@github.com:laurosilvacom/vanilla-template.git vanilla-01
```

## Create Repos on Github from the CLI with hub

```bash
# create a repo to host a new project on GitHub
git init
git add .
git commit -m "And so, it begins."
hub create
→ (creates a new GitHub repository with the name of the current directory)
git push -u origin HEAD
```

```bash
alias git="hub"
```

## Automate Lesson Creation From Templates With ZSH Functions

```bash
+vanilla(){
  cd ~/content
  npx degit laurosilvacom/vanilla-template "$1"
  cd "$1"
  git init
  git add .
  git commit -m "✨ inicial commit"
  git create
  git push -u origin master
  npm install
  code . -g src/index.js
  npm start
}

```

## Branch and Create a Lesson in a Single ZSH Function

```
+lesson(){
  git checkout -b "$1"
  git add .
  git commit -m "$(date)" --allow-empty
  git push --set-upstream origin "$1"
  open -a "Google Chrome"\
    "https://codesandbox.io/embed/github/laurosilvacom/${PWD##*/}/tree/$1/"
}
```

## Add Conditions to ZSH Functions to Prevent Mistakes

```bash

+vanilla(){
  if [ "$1" = "" ]
  then 
    echo Please name your project 😅
    return
  fi
  cd ~/content
  npx degit laurosilvacom/vanilla-template "$1"
  cd "$1"
  git init
  git add .
  git commit -m "✨ inicial commit"
  git create
  git push -u origin master
  npm install
  code . -g src/index.js
  npm start
}

+lesson(){
  if [ "$1" = "" ]
  then 
    echo Please name your branch 😅
    return
  fi

  git checkout -b "$1"
  git add .
  git commit -m "$(date)" --allow-empty
  git push --set-upstream origin "$1"
  open -a "Google Chrome"\
    "https://codesandbox.io/embed/github/laurosilvacom/${PWD##*/}/tree/$1/"
}
```

## Select a Lesson Template From an Alfred Workflow

https://github.com/johnlindquist/eggheadio-quick-lesson/tree/master


## Create a VS Code Extension to Pass Arguments to the Terminal

https://github.com/laurosilvacom/vscode-egghead-lesson

## Write Your Lesson Information to a Markdown File From a ZSH Function


## Create a Command Line Tool for Your Favorite Node Utility

https://github.com/laurosilvacom/dotfiles/tree/master/change-case
