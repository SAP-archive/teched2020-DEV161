# Exercise 2 - Exercise 2 Build, Deploy, and Test

- How to build and deploy an application to SAP Cloud Platform, Cloud Foundry environment
- How to configure Cloud Foundry settings in SAP Business Application Studio
- How to run the deployed app from your space on SAP Cloud Platform, Cloud Foundry environment

## Exercise 2.1 Sub Exercise 1 Build the application

After completing these steps you will have created...

1. Click the **Explorer** view icon to open the **Explorer** view.

    !![Open explorer view](images/01-01 AppStudio Explorer View Open_.jpg)

2. In the menu bar, select **View | Find Command**.

    !![Open command palette](images/01-02 AppStudio Command Palette Open_.jpg)

3. Select the command **Build MTA**.

    !![Command palette build mta](images/01-03 AppStudio Command Palette Build MTA-1_.jpg)

    >The build process creates a multitarget archive (`MTAR`) file in your project that packages all the project modules for deployment. You can find the `MTAR` file in the `DemoFiori/mta_archives` folder.

    !![terminal mbt build results](images/07-02-02 AppStudio Terminal MBT Build_.jpg)



## Exercise 2.2 Sub Exercise 2 Set Cloud Foundry preferences

Before you can deploy your new application, set your Cloud Foundry preferences.

1. In the menu bar, select **View | Find Command** to open the **command palette**.

    !![Command Palette-Login to CF](images/08-01 AppStudio CF Login_.jpg)

2. Select the command **CF: Login to cloud foundry**.

    >Type `cf` to filter commands.

    !![Command Palette-Login to CF](images/08-01-02 AppStudio CF Login_.jpg)

3. When prompted, provide your credentials, select the API endpoint, organization, and space for your project.

    >The Cloud Foundry organization and space appear in the status line at the bottom left part of the screen.

    !![Logged in to CF](images/02-03 AppStudio CF Login_.jpg)


## Exercise 2.2 Sub Exercise 2 Deploy the application

After completing these steps you will have...

Deploy your application to SAP Cloud Platform, Cloud Foundry environment.

Right-click the `mtar` file and select **Deploy MTA Archive**.

!![deploy mtar](images/03 AppStudio Fiori Project Deploy_.jpg)

>The application deployment to the space you are connected to starts and a notification appears. The deployment process takes a few minutes. You can see that the deployment is still in progress in the **Task: Deploy** console at the bottom right of your screen.

>When the deployment process is complete, a notification will temporarily appear at the bottom-right part of the screen.

>!![deploy success notification](images/03 AppStudio Fiori Project Deploy Success Notification_.jpg)


## Exercise 2.2 Sub Exercise 2 Get URL to access the application

This step is only applicable to apps that use **Standalone Approuter** (see [Create an SAP Fiori App Using SAP Business Application Studio](images/appstudio-fioriapps-create) > Create new SAP Fiori project > **HTML5 Applications**).

Access your deployed application in the SAP Cloud Platform cockpit. The steps below show you how to create a URL that you can use to access your new application.

1. Access the space to where the app is deployed and go to the **Applications** tab.

    !![Application's space](images/04-01 SCP Space Applications_.jpg)

2. Make sure your application is in **Started** state, and  click its name (`fioridemo_approuter`). The **`Application: fioridemo-approuter - Overview`** page opens.

3. Right-click the URL under **Application Routes** and save the URL in a text file.

    !![Get application base URL](images/10-03 SCP Space Application URL_.jpg)

4. Locate the `sap.app id` from the `manifest.json` file located in your HTML5 module, and add it to the copied link after removing the periods.

    !![app id from manifest](images/10-04 AppStudio SAP Fiori Project Manifest_.jpg)

    > For future reference, this is the construct of the final URL: `<URL_from_application_overview_page>/<mynamespace><project_name>/index.html`.

    >Example: `https://SUBACCOUNT-SPACE-fioridemo-approuter.cfapps.eu10.hana.ondemand.com/nsBusinessPartners/index.html`

    You can use this URL in any browser to access your new application in your space on SAP Cloud Platform, Cloud Foundry environment.



## Summary

With this, you have successfully completed the deployment of your SAP Fiori app to SAP Cloud Platform using SAP Business Application Studio.

In this tutorial, you used high productivity tools that are available out-of-the-box in SAP Business Applications Studio that make it easy to build and deploy applications as well as work in the Cloud Foundry environment.


Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
