# Deploy to CF

In this exercise, you will create the deployment artifacts, deploy the app to CF, and test run the app on CF.

## Logon

After completing these steps you will know how to prepare the app to deployment to the CF runtime, and use CF command line tools as well as SCP Cockpit.

1. Open a new terminal using *[CTRL] + ~ keyboard* shortcut or *Terminal | New Terminal*.
<br><br>![](images\2020-10_BAS_Open_Terminal_.jpg)<br><br>

    > Tip: You can toggle maximize view, in this case teh terminal, by double clicking its tab header.

2. Change directory to the *productinventory* folder:
<br><br>![](images\2020-10_BAS_Change_Directory_.jpg)<br><br>

    ```Shell/Bash
    cd productsinventory
    ```

    > Tip: You can use auto-complete to enhance your productivity, e.g. in the terminal type *cd pro* and press [TAB] to auto-complete.


 3. You will now prepare teh app for deployment to CF. The preparation includes two steps: (1) Generating the deployment artifacts and turning the app into a multi-target application (MTA); and (2) Generating the SAP Fiori launchpad. Both part are executed using the following command:
<br><br>![](images\2020-10_BAS_NPX-1_.jpg)<br><br>

    ```Shell/Bash
    npx fiori add deploy-config
    ```

4. Select the following:

    | Step | Parameter | Value |
    |:-----|:----------|:------|
    | A | Please choose the target | *Cloud Foundry* |
    | B | Generate project artifacts in root folder: /home/user/projects/products-inventory? | *Yes* (default) |
    | C | Enter MTA ID | *products-inventory* (default) |
    | D | Enter MTA Description | *SAP Fiori Freestyle Demo* |
    | E | Enter MTA Version | *0.0.1* (default) |
    | F | Destination name | *northwind* |

    <br><br>![](images\2020-10_BAS_NPX-2_.jpg)<br><br>

    >After you complete the above, a script will run, and you'll enter the SAP Fiori launchpad configuration step.

    >![](images\2020-10_BAS_NPX-3_.jpg)<br><br>

5. To configure the SAP Fiori launchpad (FLP), select the following:

    | Step | Parameter | Value |
    |:-----|:----------|:------|
    | A | Please choose the targetAdd FLP config and generate artifacts | *Y* |
    | B | Semantic Object | *prinSO* |
    | C | Action | *display* |
    | D | Title | *Products Inventory* |
    | E | Subtitle (optional) | *Fiori Rocks!* |

    <br><br>![](images\2020-10_BAS_NPX-4_.jpg)<br><br>

    >After you complete the above, a script will run and an FLP is added to the project.

    >![](images\2020-10_BAS_NPX-5_.jpg)<br><br>

    >As a result of executing the *npx* command, you'll see that the project structure was updated accordingly.

    >![](images\2020-10_BAS_Project_After_Config_Deploy_.jpg)<br><br>

6. To build the app for deployment, right-click *mta.yaml* and select *Build MTA*.
    <br><br>![](images\2020-10_BAS_Build_MTA_.jpg)<br><br>

    >The task is run in a new tab *Task: Build MTA*.

    >![](images\2020-10_BAS_Build_MTA_Task_.jpg)<br><br>

    >When the build task completes, additional artifacts are added to the project. The artifact that is used for deployment is the MTA archive *product-inventory_0.0.1.mtar*.

    >![](images\2020-10_BAS_Project_After_Build_MTA_.jpg)<br><br>

7. Beofre deploying the app to CF, take a look at how your CF space looks like. Log in to your trial accuont and go enter your CF organization (SCP subaccount) and the space you'll deploy the app to. A new CF space should like the following:
    <br><br>![](images\2020-10_SCP_CF_Space_Applications_Before_Deployment_.jpg)<br><br>
    ![](images\2020-10_SCP_CF_Space_Service_Instances_Before_Deployment_.jpg)<br><br>

8. Login to the CF space to which you'll deploy the app. From the menu bar select *View | Find Command* to open the *command palette*.
<br><br>![](images\2020-10_BAS_Command_Palette_Open_.jpg)<br><br>

    >You can also login to CF using the terminal: Execute the *cf login* command and follow the same steps.

9. Select the command *CF: Login to cloud foundry*.
<br><br>![](images\2020-10_BAS_CF_Login-1_.jpg)<br><br>

    >Type `cf` to filter commands.

10. When prompted, provide your credentials, select the API endpoint, organization, and space for your project.

    >The Cloud Foundry organization and space appear in the status line at the bottom left part of the screen.

    >![](images\2020-10_BAS_CF_Login-2_.jpg)<br><br>

11. To deploy the app to CF, right-click *products-inventory_0.0.1.mtar*, and select *Deploy MTA Archive*.
    <br><br>![](images\2020-10_BAS_Deploy_MTA_Archive_.jpg)<br><br>

    >The task is re-using *Task: Build MTA* tab and changes its title to *Task: Deploy MTA Archive*.

    >![](images\2020-10_BAS_Deploy_MTA_Task_.jpg)<br><br>

    >You can follow the deployment progress both in the *Task: Deploy MTA Archive* tab as well as in the *SCP Cockpit*.

12. To see the results of the deployment to CF, go to the CF tab. Your CF space should look like the following:
    <br><br>![](images\2020-10_SCP_CF_Space_Service_Instances_After_Deployment_.jpg)<br><br>
    <br><br>![](images\2020-10_SCP_CF_Space_Applications_After_Deployment_.jpg)<br><br>

13. To run the application on CF, in the CF space *Applications* tab, click *products-inventory-router*, and then click the link in the *Application Routes* section.
    <br><br>![](images\2020-10_SCP_CF_Space_Application_Routes_.jpg)<br><br>

14. SAP Fiori luanchpad comes up with your application tile.
    <br><br>![](images\2020-10_FLP_.jpg)<br><br>

15. Click the application tile. The app is successfuly running on CF.
    <br><br>![](images\2020-10_App_on_CF_.jpg)<br><br>

## Summary

Congratulations, you completed the [Getting Started](#deploy-to-cf) exercise!

With this, you have successfully completed the deployment of your SAP Fiori app to SAP Cloud Platform using SAP Business Application Studio.

In this tutorial, you used high productivity tools that are available out-of-the-box in SAP Business Applications Studio that make it easy to build and deploy applications as well as work in the Cloud Foundry environment.

Continue to [Exercise 1 - Project Setup Using Business Application Studio](../ex1/README.md).
