# Exercise 3 - Create a New Application from Template

In this exercise, you will learn how to  an SAP Fiori application for freestyle development. The application will follow the SAP Fiori Worklist floorplan.

## Exercise 3.1 - Preparation

Create a folder that will contain the app's project.

1. From the main menu select *File | New Folder*.

2. Name the folder *products-inventory*, and click *OK*.
    >Using information in the popup message verify that the new folder will be created in */home/user/projects*.
    <br><br>![](images/2020-10_BAS_App_Project_Folder_.jpg)<br><br>

## Exercise 3.1 - Launch Yeoman UI Generator

The easiest way to creaete from scratch an SAP Fiori app for freestyle development is to create it from a template. To continue developing an existing application, the best practice is to use git source code management and clone the repository.

1. From the menu bar select *View | Find Command* to open the *Command Palette*.
    <br><br>![](images/2020-10_BAS_Command_Palette_Open_.jpg)<br><br>

2. Type *yeo* in the *Command Palette* dialog to filter the *Yeoman UI Generators* command. Press [ENTER] or click *Yeoman UI Generators* to execute the command.
    <br><br>![](images/2020-10_BAS_Command_Palette_Yeo_.jpg)<br><br>

## Exercise 3.2 - Install SAP Fiori tools for SAP Fiori freestyle app development

SAP Fiori tools include high productivity tools, such as templates, wizards, editors, etc. for developing SAP Fiori apps, both fordevelopment of freestyle apps as well as for development of SAP Fiori elements apps.

3. Click *Explore and Install Generators...* to find and istall the SAP Fiori freestyle app templates. 
    <br><br>![](images/2020-10_BAS_Install_UI_Generators-1_.jpg)<br><br>
    >You may need to accept the legal terms.
    >![](images/2020-10_BAS_Yeoman_Generators_Lagal_Terms_.jpg)<br><br>
    
4. Search for *fiori* yeoman generators, locate the *@sap/generator-fiori-freestyle generator, and click *Install*. Wait until the installation is completed.
    <br><br>![](images/2020-10_BAS_Install_UI_Generators-2_.jpg)<br><br>

    installing:
    <br><br>![](images/2020-10_BAS_Install_UI_Generators-3_.jpg)<br><br>

    installation complete:
    <br><br>![](images/2020-10_BAS_Install_UI_Generators-4_.jpg)<br><br>

5. Close the *Explore and Install Generators* tab, and in the *Yeoman UI* tab scroll down to find the *SAP Fiori freestyle SAPUI5 application* generator, select it, and click *Next*.
    <br><br>![](images/2020-10_BAS_Select_Generator_.jpg)<br><br>

## Exercise 3.3 - Create Project Using SAP Fiori Worklist Application template

You'll use the worklist template available from SAP fiori tools to create the app.
   >To exit the wizard without generating the project, close the *Yeoman UI* tab.

   >Using the UI wizard you can click the `Back` button to go back to the previous step, or click the specific wizard step to go back to that step.

6. Select the *SAP Fiori Worklist Application* floorplan, and click *Next*.
    <br><br>![](images/2020-10_BAS_Template_Selection_.jpg)<br><br>

7. As datasource select *Upload a Metadata Document*.
    <br><br>![](images/2020-10_BAS_Datasource_and_Metadata_File_Path-1_.jpg)<br><br>

8. To select the *Metadata file path*, click the *folder* icon, expand *home > user > projects > data*, select *metadata.xml*, and click *Open*.
    <br><br>![](images/2020-10_BAS_Datasource_and_Metadata_File_Path-2_.jpg)<br><br>
    <br><br>![](images/2020-10_BAS_Datasource_and_Metadata_File_Path-3_.jpg)<br><br>
    <br><br>![](images/2020-10_BAS_Datasource_and_Metadata_File_Path-4_.jpg)<br><br>

9. Click *Next*.

8. For *Floorplan Customization*, select the following, and click *Next*.

    | Step | Parameter | Value |
    |:-----|:----------|:------|
    | A | Object Collection | **Products** |
    | B | Object Collection Key | **ProductID** |
    | C | Object Identifier | **ProductName** |
    | D | Object Number | **UnitPrice** |
    | E | Object Unit Of Measure | **QuantityPerUnit** |

    <br><br>![](images/2020-10_BAS_Floorplan_Customization_.jpg)<br><br>

9. For *Project Attributes*, select the following, and click *Finish*.

    | Step | Parameter | Value |
    |:-----|:----------|:------|
    | A | Module name | **productsinventory** |
    | B | Application title | **product Inventory** |
    | C | Application namespace | **products.inventory** |
    | D | Description | **An SAP Fiori freestyle app to manage products inventory (demo)** |
    | E | Project folder path | **/home/user/projects/products-inventory** |
    | F | Configure advanced options?  | **No** (default) |

## Exercise 3.4 - Open the Project's Workspace

10. Wait for the project to generate. Once it is generated, the *Yeoman UI* tab closes.

11. From the menu bar select *File | Open Workspace...*, select *products-inventory*, and click *Open*.
    <br><br>![](images/2020-10_BAS_Project_Workspace_Open_.jpg)<br><br>

11. SAP Business Applications reloads with an open workspace containing the *products-inventory* project. You can click *>* / *V* in the *Explorer* pane to expand/collapse the folders.
    <br><br>![](images/2020-10_BAS_Workspace_Open_.jpg)<br><br>

    > Tip: You can click the *Explorer* button, or any other pane button, e.g. Search, git, to expand/collapse its pane. This gives additional screen real-estate when needed. Only one pane can be open.
    > <br><br>![](images/2020-10_BAS_Pane_Closed_.jpg)<br><br>

    > You can also create a project from the terminal using Yeoman.

## Summary

You've now successfully completed the development of an SAP Fiori app using SAP Business Application Studio.

In this exercise, you learned about high productivity tools that are available out-of-the-box in SAP Business Applications Studio, such as: templates and wizards, command palette, and more.

Continue to - [Exercise 4 - Test the Application with Mock Data ](../ex4/README.md)
