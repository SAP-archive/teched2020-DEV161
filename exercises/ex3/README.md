# Exercise 3 - Create a New Application from Template

- How to create an SAP Fiori application using an application template
- How to test-run the app locally in the dev space

## Exercise 3.1 - Launch Yeoman UI Generator

After completing these steps you will have created an SAP Fiori app that follows the SAP Fiori Worklist floorplan.

>The easiest way to develop an SAP Fiori freestyle app from scratch is to create it from a template. To continue developing an existing application, the best practice is to use git source code management and clone the repository.


1. From the menu bar select *View | Find Command* to open the *Command Palette*.
    <br><br>![](images/2020-10_BAS_Command_Palette_Open_.jpg)<br><br>

2. Type *yeo* in the Command Palette* dialog to filter the *Yeoman UI Generators* command. Press [ENTER] to execute the command.
    <br><br>![](images\2020-10_BAS_Command_Palette_Yeo_.jpg)<br><br>

## Exercise 3.2 - Install SAP Fiori tools for SAP Fiori freestyle app development

3. Click *Explore and Install Generators...* to find and istall the SAP Fiori freestyle app templates. You may need to accept the legal terms.
    <br><br>![](images\2020-10_BAS_Install_UI_Generators-1_.jpg)<br><br>

4. Search for *fiori* yeoman generators, locate the *@sap/generator-fiori-freestyle generator, and click *Install*. Wait until the installation is completed.
    <br><br>![](images\2020-10_BAS_Install_UI_Generators-2_.jpg)<br><br>

    installing:
    <br><br>![](images\2020-10_BAS_Install_UI_Generators-3_.jpg)<br><br>

    installation complete:
    <br><br>![](images\2020-10_BAS_Install_UI_Generators-4_.jpg)<br><br>

5. Close the *Explore and Install Generators* tab, and in the *Yeoman UI* tab scroll down to find the *SAP Fiori freestyle SAPUI5 application* generator, select it and click *Next*.
    <br><br>![](images\2020-10_BAS_Select_Generator_.jpg)<br><br>

    >To exit the wizard without generating the project, close the *Yeoman UI* tab.

    >Using the UI wizard you can click the `Back` button to go back to the previous step, or click the specific wizard step to go back to that step.

## Exercise 3.3 - Create Project Using SAP Fiori Worklist Application template

6. Select the *SAP Fiori Worklist Application* template, and click *Next*.
    <br><br>![](images\2020-10_BAS_Template_Selection_.jpg)<br><br>

7. As datasource select *Connect to an OData Service*, use the *https://services.odata.org/V2/Northwind/Northwind.svc/* OData v2 service URL, and click *Next*.
    <br><br>![](images\2020-10_BAS_Datasource_and_Service_Selection_.jpg)<br><br>

8. For *Template Customization*, select the following, and click *Next*.

    | Step | Parameter | Value |
    |:-----|:----------|:------|
    | A | Object Collection | **Products** |
    | B | Object Collection Key | **ProductID** |
    | C | Object Identifier | **ProductName** |
    | D | Object Number | **UnitPrice** |
    | E | Object Unit Of Measure | **QuantityPerUnit** |

    <br><br>![](images\2020-10_BAS_Datasource_and_Service_Selection_.jpg)<br><br>

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

10. Wait for the project to generate. Once it is generated, the *Yeoman UI* tab closes, and a popup notification appears at the bottom right of SAP Business Application Studio asking what would you like to do with it. Click *Open in New Workspace*.
    <br><br>![](images\2020-10_BAS_Project_Generated_.jpg)<br><br>
    >If the popup notification does not appear, in the main menu select *File | Open Workspace...*, select *products-inventory*, and click *Open*. Wait for SAP Business Application Studio to reload.

11. SAP Business Applications reloads with an open workspace containing the *products-inventory* project. You can click *>* / *V* in the *Explorer* pane to expand/collapse the folders and files display.
    <br><br>![](images\2020-10_BAS_Workspace_Open_.jpg)<br><br>

    > Tip: You can click the *Explorer* button, or any other pane button, e.g. Search, git, to expand/collapse its pane. This gives additional screen real-estate when needed. Only one pane can be open.
    > <br><br>![](images\2020-10_BAS_Pane_Closed_.jpg)<br><br>

    > You can also create a project from the terminal using Yeoman.

## Summary

You've now successfully completed the development of an SAP Fiori app using SAP Business Application Studio.

In this exercise, you learned about high productivity tools that are available out-of-the-box in SAP Business Applications Studio, such as: templates and wizards, command palette, and more.

Continue to - [Exercise 4 - Test the Application with Mock Data ](../ex4/README.md)
