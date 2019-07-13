## Setting Up A Windows Development Environment


### Set Up Your Computer
- [ ] [Setup Git](gitforwindows.org)  
  * This [video](https://www.youtube.com/watch?v=2j7fD92g-gE) will walk you through the installation choices.  
  * To set it as your integrated terminal in Visual Studio Code, got to **settings**, click on **Features**, click on **Terminal**. Find “Integrated > Shell: Windows”. Click **Edit in settings.json**. Inside the brackets, type this:  
  * “terminal.integrated.shell.windows”: “C:\\Program Files\\Git\\bin\\bash.exe”    .
- [ ] Install [Node](nodejs.org) OR [nvm-windows](https://github.com/coreybutler/nvm-windows).  
  * I prefer nvm as it lets me easily switch between different versions of node for many projects.
- [ ] Install [Mongo](https://docs.mongodb.com/guides/server/install/)
- [ ] Install [REST Clients](https://www.getpostman.com/products)  
  * The individual plan is free.
  * Postman will allow you to easily test API servers using any of the standard RESTful methods (GET,POST,PUT,PATCH,DELETE) with full control over headers, body and authentication.

- [ ] Don't forget to install npm with `npm install -g npm`. The `-g` flag will install npm onto your machine instead of your package.json file, so it will be available for this and all future projects.


## Useful Resources for New Developers

### Git Good
  * [An introduction to Git: what it is, and how to use it](https://www.freecodecamp.org/news/what-is-git-and-how-to-use-it-c341b049ae61/)
  * [How to use Git efficiently](https://www.freecodecamp.org/news/how-to-use-git-efficiently-54320a236369/?source=linkShare-e41cd5edcdac-1535829065)

### Nodejs info from Microsoft
  * [NodeJS On Windows Guidelines](https://github.com/Microsoft/nodejs-guidelines)

### Reading and Reference Materials
  * [ES6 Features](http://es6-features.org/)
  * [Eloquent JavaScript](http://eloquentjavascript.net/)
  * [You Don't Know JS series](https://github.com/getify/You-Dont-Know-JS)