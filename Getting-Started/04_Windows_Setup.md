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
- [ ] Install [REST Clients](https://www.getpostman.com/downloads/)  
  * The individual plan is free.
  * Postman will allow you to easily test API servers using any of the standard RESTful methods (GET,POST,PUT,PATCH,DELETE) with full control over headers, body and authentication.


- Optional Git tools for visual people
  * [SourceTree](https://www.sourcetreeapp.com/) or [GitKraken](https://www.gitkraken.com/download)

## TROUBLESHOOTING
- If ``` npm i ``` or ``` npm install ``` inside the repo complains about python, you may need to install [node-gyp](https://github.com/nodejs/node-gyp#on-windows) globally.
  - You may also need to install bcrypt if it keeps complaining with ``` npm install --save bcrypt ```

Proceed to the rest of the Developer Onboarding Document.

## Useful Resources for New Developers

### Nodejs info from Microsoft
  * [NodeJS On Windows Guidelines](https://github.com/Microsoft/nodejs-guidelines)

### HTTP Status Code Resources
  * [Nouri Most Used HTTP Status Codes](https://github.com/nourimeals/documents/tree/master/Getting-Started/05_HTTP_Status_Codes.md)
  * [REST API Tutorial's Helpful Page](https://www.restapitutorial.com/httpstatuscodes.html)

### Serverless Documentation
  * [Serverless Framework Docs](https://www.serverless.com/framework/docs/)

### AWS DynamoDB Documentation
  * [Developer Guide and API Reference](https://docs.aws.amazon.com/dynamodb/index.html)