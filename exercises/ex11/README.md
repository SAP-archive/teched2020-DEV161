# Exercise 11 - Connect Your Project to SAP Cloud Platform Continuous Integration and - Pipeline Monitoring and Results

In this exercise, we will create a project in a public GitHub repository in which to store your source code, enable SAP Cloud Platform Continuous Integration and Delivery, and configure and run a predefined continuous integration and delivery (CI/CD) pipeline that automatically tests, builds, and deploys your code changes.

## Exercise 11.8 Verify the Success of Your Build

After completing these steps, you will have monitored the outcome of your job in SAP Cloud Platform Continuous Integration and Delivery.

1. In the **Jobs** tab in SAP Cloud Platform Continuous Integration and Delivery, select your job and verify that a new tile appears in the **Builds** view. This tile should be marked as running.
![Job](./images/CICD_running_job.png)
**Note:** If no new tile appears, trigger the job manually by choosing the *Trigger Build* button.
![Trigger Job](./images/CICD_trigger_job.png)

2. Wait until the job has finished and verify that the build tile is marked as successful.
![Successful Build](./images/CICD_successful_build.png)

## Exercise 11.9 Access the Deployed Application.

After completing these steps, you will have accessed your deployed application trough the SAP Cloud Platform cockpit.

1. In your trial account in the SAP Cloud Platform cockpit, navigate to the **Cloud Foundry** tab and choose **Spaces**.

2. Select your space.
![CP Spaces](./images/CP_cloudfoundry.png)

3. Verify that the *products-inventory-router* application has been deployed and that the `cpapp-approuter` is running.
![CP Apps](./images/CP_apps.png) 

4. Choose the `cpapp-approuter`.

5. Choose the link under **Application Routes**.
![CP Apps](./images/CP_app_routes.png) 

4. Verify that the deployed application is running and showing the change that you've made.
![Fiori App](./images/fiori_app.png) 


## Summary

You've created a project in GitHub to store your source code and successfully configured and run a predefined continuous integration and delivery pipeline that automatically builds, tests and deploys your code changes.

Continue to - [Exercise 12 - Add Columns to Worklist](../ex12/README.md).