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

## Writing the Script

Let's begin writing a script that will create the new component. This will be the script that the computer will run through to create the directories.

1. Move into the Home `~/` directory by running `$ cd ~`

2. Once inside of the Home directory run:
   ```
   $ touch .newapp.sh && code .newapp.sh
   ```
   This is the command for [VS Code](https://code.visualstudio.com/). Change to editor of choice.
   
3. Write the following code in the `.newapp.sh` file:

   ```
   #! /bin/bash

   echo What is the App project\'s name? ***REMINDER*** !No Spaces!

   read projectname

   mkdir -p ~/Dev/Apps/$projectname/{01_Assets/{Photography,Inspiration,Typography},02_Design,03_Code,04_Proofs,05_Delivered/{01_Design,02_Code}}
   ```

Lets go over what's happening here.
