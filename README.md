# Create-Components

Quick bash script to create react components a bit faster.

This assumes you will be in a file system created by [Create React App](https://github.com/facebook/create-react-app) and you are using the following structure to contain your components:

```
  ├── node_modules/
  ├── public/
  ├── src/
      ├── **components/**
      └── ...other files
  ├── .gitignore
  ├── package-lock.json
  ├── package.json
  └── README.md
```

**Be sure to `$ cd` into your `src/components/` folder before running this script!** Failure to do so will result in the component directory being created wherever you are in the terminal

## Writing the Script

Let's begin by writing a script that will create the new component.

1. Run the following:

   ```
   $ touch ~/.newcomponent.sh && code ~/.newcomponent.sh
   ```

   This is the command for [VS Code](https://code.visualstudio.com/). Change to editor of choice.

2. Write the following code in the `.necomponent.sh` file:

   ```
   #! /bin/bash

   echo What\'s the Component Name?

   read componentname

   mkdir $componentname &&
   cd $componentname &&
   touch $componentname.jsx
   ```

Lets go over what's happening here.

First, `#! /bin/bash` lets the shell know what type of interpreter to run. Then `echo ...` prompts the user for the component title. Next, the computer will run `read componentname`. This will **read** the user input and cache it in a variable called **componentname**.
Then `mkdir $componentname` creates a directory with the name cached in `$componentname`. The `&&` operator is used to chain the commands together. After the directory is created the script runs `cd $componentname` and `touch $componentname.jsx`. Here, the system is going inside the newly created component directory and again we are using variable `$componentname`, this time a it is being used to create a `.jsx` file.

3. Next, save the file and change some preferences to allow terminal access. For this, open a Finder window.

4. Navigate to the Home directory and press Command + Shift + . to see the hidden files. (When the .newcomponent.sh file was saved earlier, the "." in front created it as a hidden file)

5. Right click or Control + Click the file and select "Get Info"

6. At the very bottom of the window look for the following (it may be necessary to scroll):

   <img style="padding: 20px;" src="https://imgur.com/zF3XjHc.png" width="400">

7. Click the lock icon. Got a password? Your machine will prompt you to enter it in order to unlock the permissions, otherwise it will just unlock.
8. Once unlocked, go back to the terminal and run `$ chmod 700 ~/.newcomponent.sh`
9. This will change the file into an executable file.
10. In the terminal run `$ ./.newcomponent.sh`. Voila!

Next [add an alias](#add-alias) to create a command to quickly initialize this script.

## Add Alias

Last step! Make a quick command to make these components quickly when needed. Depending on the terminal there are different files to open. This README only includes the process for [oh-my-zsh](https://ohmyz.sh/) users:

1. Navigate to the Home directory.
2. Inside the Home directory run:
   ```
   $ ls -a
   ```
   The `-a` flag will show the _hidden_ files.
3. Open the `.zshrc` file: `$ code .zshrc`
4. Scroll to the bottom of the `.zshrc` file to the comments:
   ```
   # Set personal aliases, overriding those provided by oh-my-zsh libs,
   # plugins, and themes. Aliases can be placed here, though oh-my-zsh
   # users are encouraged to define aliases within the ZSH_CUSTOM folder.
   # For a full list of active aliases, run `alias`.
   #
   # Example aliases
   #
   # alias ohmyzsh="mate ~/.oh-my-zsh"
   # alias zshconfig="mate ~/.zshrc"
   ```
5. Create the following `alias` line:

   ```
   alias cc="~/.newcomponent.sh"
   ```

   cc is short for Create Component. Neat right?

6. Save the file and restart the Terminal app.

7. Try and run:

   ```
   $ cc
   ```

Voila x2!
