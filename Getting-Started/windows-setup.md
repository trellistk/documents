## Setting Up A Windows Development Environment


### Set Up Your Computer
- [ ] [Setup Git](gitforwindows.org)  
  * This [video](https://www.youtube.com/watch?v=2j7fD92g-gE) will walk you through the installation choices.  
  * To set it as your integrated terminal in Visual Studio Code, got to **settings**, click on **Features**, click on **Terminal**. Find “Integrated > Shell: Windows”. Click **Edit in settings.json**. Inside the brackets, type this:  
  * “terminal.integrated.shell.windows”: “C:\\Program Files\\Git\\bin\\bash.exe”    .
- [ ] Install [Node](nodejs.org) OR [nvm-windows](https://github.com/coreybutler/nvm-windows).
  * I prefer nvm as it lets me easily switch between different versions of node for many projects.
  * after using the installer inside the zip file nvm-setup.zip, you will likely need to tell nvm to use the version you installed.
  ```
  nvm use <latest node version>
  ```
  * In the end, you should be able to type ``` node -v ``` or ``` npm ``` and get good feedback in the cmd.exe prompt or bash. If bash doesn't show, try closing it and restarting it.
- [ ] Install [Mongo](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/).
  * After installation, follow the instructions to set up the correct folders and how to start your database using the cmd prompt.
  * You will need the mongodb to be running in the background if you want to use your local database with the API app.
  * [Creating Aliases for Mongo](https://teamtreehouse.com/community/how-to-setup-mongodb-on-windows-cmd-or-gitbash-with-shortcuts) This will allow you to simply type 'mongod' or 'mongo' to start up the database instead of the annoyingly long file path shown in the Mongo Docs.
- [ ] Install [REST Clients](https://www.getpostman.com/downloads/)  
  * The individual plan is free.
  * Postman will allow you to easily test API servers using any of the standard RESTful methods (GET,POST,PUT,PATCH,DELETE) with full control over headers, body and authentication.


- [ ] Install Extra useful tools
  * [Robo 3T](https://robomongo.org/download)
- Optional for visual people
  * [SourceTree](https://www.sourcetreeapp.com/) or [GitKraken](https://www.gitkraken.com/download)

## TROUBLESHOOTING
- If ``` npm i ``` or ``` npm install ``` inside the repo complains about python, you may need to install [node-gyp](https://github.com/nodejs/node-gyp#on-windows) globally.
  - You may also need to install bcrypt if it keeps complaining with ``` npm install --save bcrypt ```

Proceed to the rest of the Developer Onboarding Document.

## Useful Resources for New Developers

### Nodejs info from Microsoft
  * [NodeJS On Windows Guidelines](https://github.com/Microsoft/nodejs-guidelines)