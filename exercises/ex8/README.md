# Exercise 2 - Exercise 2 Description

In this section, we describe steps how to configure and run predefined continuous integration and delivery (CI/CD) pipelines that automatically test, build, and deploy your code changes to speed up your development and delivery cycles.

## Exercise 2.1 Sub Exercise 1 Create Github Repository

This step describes how to create a Github repository in which you can store the source code of your project. You need to have a user in the public GitHub to execute the steps below.

1. Open your github home page.
2. Click on *New* in the 'Repository' tab to create a new repository.

   ![Create Github Repo](./images/newRepository.png)

3. Enter the name of the repository. For example, ‘extendUI’. Do not check the checkbox 'Intialize this repository with a README'.
4. Click on create repository.

    ![Create Github Repo](./images/createGitRepo.png)

5. Copy the github url of the newly created Git repository.

   ![Copy GitHub URL](./images/copyGitHubURL.png)


## Exercise 2.2 Sub Exercise 2 Generating OAuth Token

After completing these steps you will have...

1. As the public Git hub announced deprecation of Basic Authentication, we have described steps to login with the Access tokens to the Git.
2. Refer to the public Git Hub link and create a [Personal Access Token](https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token).
3. You can use these Access tokens when you want to use Git commands instead of giving Git password.

## Exercise 2.2 Sub Exercise 2 Add Git repository to HTML5 project

After completing these steps you will have...

1. Login to your SAP Cloud Platform account.
2. Goto your Subaccount and click on Subscriptions.
3. Search for **Business Application Studio** and click on 'Go to Application'.

   ![Open Biz App Studio](./images/openBizAppStudio.png)

4. You would be prompted with a login screen of the custom Identity Provider what you have configured.
5. Login to the Application using your custom Identity Provider credentials.
6. Open the previously created workspace with the HTML5 application.
7. Open a new terminal and navigate to project root folder.

   ![Open Terminal](./images/openTerminal.png)

8. Enter your email address and User name to be used by Git. You can use the email address which you have used to register the Git account.
   ```
   git config --global user.email "you@example.com"
   git config --global user.name "Your Name"
   ```
7. Now we are initializing a Git repository which can be used to convert an existing, unversioned project to a Git repository or initialize a new, empty repository. To use  other Git commands, you need an initialized repository, so this is usually the first command you'll run in a new project. Let us run the following commands:

	```
    git init
    git add .
    git commit -m "Push project content to github"
    ```
   ![Git Commit](./images/commitProject.png)

8. Now take the copied Git Repository URL which you created and copied in step 5 of 'Creating GitHub Repository' and add this URL pointing as the remote repository.

   ```
   git remote add origin <copied Git repository url.git>
   ```

9. Let us push the commit with project contents to this Git Repository.

   ```
   git push -u origin master
   ```

10. When prompted, enter your Git Username and Password (or Token).

    ![Git Commit](./images/gitPushRepository.png)


## Exercise 2.2 Sub Exercise 2 Continuous Integration and Delivery pipeline setup

After completing these steps you will have...

1. In your subaccount in the SAP Cloud Platform cockpit, choose Subscriptions.
2. Search for “Continuous Integration” and Click on “Continuous Integration & Delivery”
4. Click “Subscribe”, if you have not already subscribed and click on “Go to Application”.

   ![Git Commit](./images/openCICDService.png)

5. Login to the CI/CD application using the company identity provider account credentials.
6. In the next step, we will configure credentials for connecting SAP Cloud Platform Continuous Integration and Delivery to other services like Git and Cloud Accounts.

7. Let us create Credentials to connect to GitHub to clone the sources. This step is only needed if your GitHub repository is private else you can skip this step.
  - Choose the ‘Credentials’ tab and click '+'. For the user name, enter your Github user name.
  - For 'Type', select 'Basic Authentication'.
  - For 'Password', use the personal access token which you created in the Github in previous step.

     ![Git Commit](./images/gitCredentials.png)

8. In the Credentials tab, choose '+' (Create Credentials) to configure credentials of a Cloud Platform user, who has the appropriate permissions. The user must have the Space Developer role and also be a member of the specified Cloud Foundry organization and space.
We recommend using a technical user. However, you can use also use your cloud credentials.
  - Enter a name for the cloud credentials, ex: cloud-credentials
  - Type: Choose 'Basic Authentication'
  - Username: Enter your SAP Cloud Platform email id
  - Password: Enter your SAP Cloud Platform user password

   ![Cloud Credentials](./images/cloudCredentials.png)

9. Before creating the CI/CD Job, let us copy the Cloud Foundry API endpoint, Org and Space which is needed for this next step.
10. Login to your SAP Cloud Platform account and copy the API Endpoint, Org Name into a text editor of your choice.  

    ![copy Cloud Data](./images/copyCloudData.png)

11. Choose 'Spaces' and copy the space name to a text editor of your choice.

    ![copy Space Name](./images/copySpaceName.png)

12. Choose the 'Jobs' tab and ‘+’ icon to create a new job.
13. In the next screen, enter the following inputs :

    - Job Name: For example, 'cloud-extension-html5-sample'
    - Repository URL: Enter the Github repository URL used in previous step.
    - Repository credentials : <Choose the GitHub credential you've created in step 7>
    - Branch: master
    - Pipeline: sap-ui5-cf
    - Version: latest or leave the default
    - Build retention: Keep the Logs : 25 days

    ![create CICD Job](./images/createCICDJob1.png)

14. Choose 'Tasks'. By default, the Build task is ‘ON’
15. Change the Deploy State ‘ON’
16. For the fields 'API Endpoint', 'Org Name', 'Space', enter the values copied from step 10 and step 11.
17. Choose the cloud credentials created in step 8.
18. Choose 'Create' to create the Continous Integration Job.

   ![create CICD Job](./images/createCICDJob2.png)

19. If you create the first job in a repository, the Webhook Creation pop-up appears. It provides you with the data you need to define a webhook in GitHub. Copy the 'Payload URL' and the 'Secret' into a text editor of your choice.

    ![copy payload URL](./images/payloadURL.png)

20. Open your Github repository and choose 'Settings' --> 'Hooks' --> 'Add webhook'.

    ![add Web Hook](./images/addWebHook.png)

21. For the 'Payload URL' and 'Secret', copy and paste the payload URL and secret from step 19.

    ![add Web Hook](./images/addWebHook1.png)

22. For 'Content Type', select 'application/json' and configure the job to be triggered for every 'Push' event and choose 'Add Webhook'. Now, any new push request to this repository triggers the CI/CD pipeline you have created.
23. To trigger the pipeline manually, go back to the CI/CD pipeline and choose the ‘Run’ icon as shown below.

    ![manual trigger Job](./images/manualTriggerJob.png)

24. You can see the successful log results of 'Build' and 'Deploy'. To view the full log file, click on the respective tile.

    ![Build Deploy Results](./images/buildDeployResults.png)   


## Exercise 2.2 Sub Exercise 2 Test automatic triggering of CI/CD job

After completing these steps you will have...

1. To test automatic triggering of the build job, let us change a file and push the changes to the Git repository.
2. Switch to the 'Business Application Studio' and open the workspace in which the project is created.
3. Change the index.html file by editing the title.

   ```
   <h1> Updated Business Partner </h1>
   ```
   ![update Project](./images/updateProject.png)

4. Switch to the 'Source Control: Git" tab and add the 'index.html' file from the unstaged changes to the staged changes by clicking the '+', Enter a commit message for example: "Test Commit". Click the tick symbol as shown in the screenshot to commit the changes.

   ![commit Changes](./images/commitChanges.png)

5. Let us push the commit by switching to the "Terminal" window like before and enter the following command, then enter your Git Username and Git Access Token.

   ```
   git push -u origin master
   ```

   ![push Commit](./images/pushCommit.png)

6. This Git push to the repository triggers the SAP Cloud Platform Continuous Integration and Delivery job. Switch to the browser window "Continuous Integration & Delivery" to check the automatically triggered job.

   ![retriggered Build Job](./images/retriggeredBuildJob.png)


## Summary

You have successfully configured and added a Continuous Integration / Continuous Delivery pipeline to your cloud application.

Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
