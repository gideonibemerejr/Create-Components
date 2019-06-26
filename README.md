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
   ```


    read componentname

    mkdir $componentname &&
    cd $componentname &&
    touch $componentname.jsx
    ```

Lets go over what's happening here.

First, `#! /bin/bash` lets the shell know what type of interpreter to run. Then `echo ...` prompts the user for the component title. Next, the computer will run `read componentname`. This will **read** the user input and cache it in a variable called **componentname**.
Then `mkdir $componentname` creates a directory with the name cached in `$componentname`. The `&&` operator is used to chain the commands together. After the dir is created the script runs `cd $componentname` and `touch $componentname.jsx`. First the system is entering the newly created component directory and the variable `$componentname` is being used to create a `.jsx` file.
