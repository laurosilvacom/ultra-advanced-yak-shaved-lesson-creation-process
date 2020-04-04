# Notes: Automate Everything: An egghead Guide to Productivity

## Create a Lesson Template

1. Go to CodeSandbox and create a Sandbox.

2. Then we'll create a GitHub repo from this template by signing in with GitHub, forking the Sandbox.

3. From Github, grab the link to clone repo, use `degit`:

```bash
npx degit git@github.com:laurosilvacom/vanilla-template.git vanilla-01
```

## Create Repos on Github from the CLI with hub

```
# create a repo to host a new project on GitHub
git init
git add .
git commit -m "And so, it begins."
hub create
→ (creates a new GitHub repository with the name of the current directory)
git push -u origin HEAD
```

```
alias git="hub"
```

## Automate Lesson Creation From Templates With ZSH Functions

## Branch and Create a Lesson in a Single ZSH Function

## Add Conditions to ZSH Functions to Prevent Mistakes

## Launch a New Lesson From a Keyboard Shortcut

## Select a Lesson Template From an Alfred Workflow

## Create a Command Line Tool for Your Favorite Node Utility

## Create a VS Code Extension to Pass Arguments to the Terminal

## Write Your Lesson Information to a Markdown File From a ZSH Function

## Speed Editing in Screenflow by Remapping Your Mouse with Karabiner

## Bind the Middle Mouse Button to Dragging the Screenflow Timeline Using Karabiner
