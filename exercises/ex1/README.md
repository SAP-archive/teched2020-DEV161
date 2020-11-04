# Getting Started

In this exercise, you will learn how to access SAP Business Application Studio, and prepare it for development of an SAP Fiori app.

## Exercise 1.1 - Log in to SAP Business Application Studio

After completing these steps you will know how to access SAP Business Application Studio.

1. Open a browser of your choice (Google Chrome, Microsoft Edge, Apple Safari, etc).

2. Go to [SAP Cloud Platform Landing Page](https://www.sap.com/products/cloud-platform.html?btp=10a432f3-a259-46c4-aebc-79c090a69b22), and click *Log in to trial* to log in to your SAP Cloud Platform cockpit. 
    >If the log in doesn't work, make sure you fulfill the [requirements](../../README.md#requirements).

    <br>![](images/2020-10_SCP_Trial_Landing_Page_.jpg)<br><br>

3. Click **SAP Business Application Studio** to launch SAP Business Application Studio, and log in with your credentials. 
    >You may need to accept the legal terms.

    >If the log in doesn't work, make sure you fulfill the [requirements](../../README.md#requirements).

    <br>![](images/2020-10&#32;SCP&#32;Access&#32;AppStudio.jpg)<br><br>

## Exercise 1.2 - Create Dev Space

SAP Business Application Studio provides turn-key solution based on what we call dev-spaces. Dev-Spaces are like isolated virtual machines in the cloud that can be instantly spinned up. 
Each Dev-Space type contains tailored tools and pre-installed runtimes for a target scenario such as SAP Fiori or mobile development. 
This simplifies and saves time in setting up the development environment as there’s no need to install anything or upgrade, letting developers to focus on their business domain, anytime, anywhere 

4. Now you can create your dev space! Click *Create Dev Space*.
<br><br>![](images/2020-10_BAS_Dev_Space_Manager_Empty_.jpg)<br><br>

5. Enter the new name of your dev space, e.g. *Procurement*, select *SAP Fiori* as application type, and click *Create Dev Space*.
<br><br>![](images/2020-10_BAS_Dev_Space_Create_.jpg)<br><br>

6. Your dev space is being prepared and starts up. This might take a few minutes. Wait until the status shows *RUNNING*.
<br><br>![](images/2020-10_BAS_Dev_Space_Starting_.jpg)<br><br>
![](images/2020-10_BAS_Dev_Space_Running_.jpg)<br><br>

## Exercise 1.3 - Launch the Development Environment

7. Click on your dev space name, e.g. *Procurement*. You'll be redirected to your newly created SAP Business Application Studio dev space.
    >You may need to accept the legal terms.

    <br><br>![](images/2020-10_BAS_Launched_.jpg)<br><br>

8. Bookmark this URL, so it'll be easier for you to access your dev space within SAP Business Application Studio.
    >Tip: If you want to go back to the dev space manager page, remove the URL part after its *index.html*, and click [ENTER].

## Exercise 1.4 - Preparations for the next exercises

9. Click *Open Workspace*.
    <br><br>![](images/2020-10_BAS_Open_Workspace_.jpg)<br><br>

10. Select *projects*, and click *Open*.
    <br><br>![](images/2020-10_BAS_Open_Workspace-2_.jpg)<br><br>
    >Wait for SAP Business Application Studio to re-load.

11. From the main menu select *File | New Folder*.

12. Name the folder *data*, and click *OK*.
    >Using information in the popup message verify that the new folder will be created in */home/user/projects*.
    <br><br>![](images/2020-10_BAS_New_Folder_.jpg)<br><br>


13. Click the following [link](data/metadata.xml?raw=true) to access the *metadata.xml* file.

14. Right-click the data area, and select *save as...*.
    >You'll save the file to your local machine.

15. Choose the folder to where the file will be saved (*Downloads* is the default folder). Use *metadata.xml* as the *File name*, and click *Save*.
    >The default file extension using this method is *txt*. Make sure you modify it accordingly.

16. Open the folder to where you saved the file, and drag and drop it to the *data* folder you created in SAP Business Application Studio.
    <br><br>![](images/2020-10_BAS_App_Mock_Uploaded_.jpg)<br><br>

    >Follow the same steps for [ui5.yaml](data/ui5.yaml?raw=true), [package.json](data/package.json?raw=true), [manifest.json](data/manifest.json?raw=true), which will be used in a later stage of the workshop.

## Summary

Congratulations, you completed the [Getting Started](#getting-started) exercise!

Continue to [Exercise 1 - Project Setup Using Business Application Studio](../ex1/README.md).
