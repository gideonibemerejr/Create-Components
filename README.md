# Create-Components

Quick alias to create react components a bit faster.

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

## Writing the Alias function
This will be a command to make these components quickly when needed. It will take in one variable after the *alias* that is the name of the component. Depending on the terminal there are different files to open. This README only includes the process for [oh-my-zsh](https://ohmyz.sh/) users:

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
5. Type the following line:

   ```
    cc() {
      mkdir $* &&
      cd $* &&
      touch $*.jsx
    }
   ```

   cc is short for Create Component. Neat right?

6. Save the file and restart the Terminal app.

7. Try and run:

   ```
   $ cc <componentName>
   ```

Voila!
