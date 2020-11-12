# Exercise 11 - Connect Your Project to SAP Cloud Platform Continuous Integration and - Pipeline Monitoring and Results

In this exercise, you will run a predefined continuous integration and delivery (CI/CD) pipeline that automatically tests, builds, and deploys your code changes.

## Exercise 11.1 - Verify the Success of Your Build

After completing these steps, you will have monitored the outcome of your job in SAP Cloud Platform Continuous Integration and Delivery.

1. In the *Jobs* tab in SAP Cloud Platform Continuous Integration and Delivery, click *Procurement* job and verify that a new tile appears in the *Builds* view. This tile should be marked as running.
    <br><br>![Job](images/2020-11_CICD_Monitor-2_.png)<br><br>

    >If no new tile appears, click the *Trigger Build* button to trigger the job manually.
    ><br><br>![Trigger Job](images/2020-11_CICD_Monitor-3_.png)<br><br>

2. Click the new tile to monitor the progress of the job. The specific job build view opens. The view presents the current state of the job build. You can click a specific stage of the job build to view its log. 
    <br><br>![Job Monitoring](images/2020-11_CICD_Monitor-4_.png)<br><br>

    >The view is refreshed approximately every 10 seconds. If it does not, you can click the refresh icon.

3. Wait until the job has finished, and verify that the build tile is marked as successful.
    <br><br>![Successful Build](images/2020-11_CICD_Monitor-5_.png)<br><br>

## Exercise 11.2 - Access the Deployed Application.

After completing these steps, you will have accessed your deployed application trough the SAP Cloud Platform cockpit.

1. To see the results of the deployment to Cloud Foundry, in the *SAP Cloud Platform Cockpit*, go to the Cloud Foundry space to which you deployed the app, and click the *Applications* tab. Click *products-inventory-router*, and then click the link in the *Application Routes* section.
    <br><br>![CP Apps](./images/CP_app_routes.png) <br><br>

4. Verify that the deployed application is running and showing the change that you've made.
    <br><br>![Fiori App](images/2020-11_SCP_App_Running_After_CICD_.png) <br><br>


## Summary

Nice job!!!

You created a repostiroy in GitHub to store your source code and used the repository as a source code management system. You successfully configured a predefined continuous integration and delivery pipeline, and by pushing a code change of your app to your GitHub repostiroy you triggered the pipeline that automatically builds, tests and deploys your app to your SAP Cloud Platform, Cloud Foundry space.

Continue to - [Exercise 12 - Add Columns to Worklist](../ex12/README.md).