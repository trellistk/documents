# Pipelines and CI/CD

Notes: This currently applies to the [Back End API](https://github.com/ambergkim/nouri-api) but in the process of being implemented for the [Website](https://github.com/nourimeals/website) and [Front End App](https://github.com/ambergkim/nouri-native).

## The Workflow
### Initial
1. Clone down the repository from GitHub

### Ongoing
1. Pull down the ```develop``` branch
2. Create your own branch from ```develop```
- Checkout the [Git SOP](SOPs/Git_Standard_Operating_Procedures.md)
3. Do your work
4. Create your PR
5. Ensure your PR is passing the Heroku CI Build
6. Get Feedback and Apply
7. Get your PR approved
8. Merge your work via ```Rebase and Merge```.

Once your work has been merged to develop, your work should automatically be deployed to our development environment.

9. Once your work has been deployed, test your work in the development environment.

### Releases & Hotfixes
Once work has been validated in ```develop``` and we are ready to create a release, we create a PR from ```develop``` to ```master``` which will trigger build and deployments to production environments.

Hotfixes right now should still go through ```develop``.

### Sample tree
```
feature1   feature2 
|          |
|          |
|         /
|        /
|       /
develop
|
|
|
|
|
|
master
```