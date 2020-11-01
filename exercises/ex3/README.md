# Exercise 3 - Exercise 2 Description

- How to create an SAP Fiori application using an application template
- How to test-run the app locally in the dev space

## Exercise 2.1 Sub Exercise 1 Create new SAP Fiori project

After completing these steps you will have created an SAP Fiori app that follows the SAP Fiori Worklist floorplan.

>The easiest way to develop an SAP Fiori freestyle app from scratch is to create it from a template. To continue developing an existing application, the best practice is to use git source code management and clone the repository.


1. From the menu bar select *View | Find Command* to open the *Command Palette*.
    <br><br>![](images/2020-10_BAS_Command_Palette_Open_.jpg)<br><br>

2. Type *yeo* in the Command Palette* dialog to filter the *Yeoman UI Generators* command. Press [ENTER] to execute the command.
    <br><br>![](images\2020-10_BAS_Command_Palette_Yeo_.jpg)<br><br>

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
    | A | What is the module name for your application? | **productsinventory** |
    | B | What is the title for your application? | **product Inventory** |
    | C | What is the namespace for your application? | **products.inventory** |
    | D | Whart is the descripeiom for your application? | **An SAP Fiori freestyle app to manage products inventory (demo)** |
    | E | Choose your project folder  | **/home/user/projects/products-inventory** |
    | F | Do you want to cinfigure advacned options?  | **No** (default) |

10. Wait for the project to generate. Once it is generated, the *Yeoman UI* tab closes, and a popup notification appears at the bottom right of SAP Business Application Studio asking what would you like to do with it. Click *Open in New Workspace*.
    <br><br>![](images\2020-10_BAS_Project_Generated_.jpg)<br><br>

11. SAP Business Applications reloads with an open workspace containing the *products-inventory* project. You can click *>* / *V* in the *Explorer* pane to expand/collapse the folders and files display.
    <br><br>![](images\2020-10_BAS_Workspace_Open_.jpg)<br><br>

    > Tip: You can click the *Explorer* button, or any other pane button, e.g. Search, git, to expand/collapse its pane. This gives additional screen real-estate when needed. Only one pane can be open.
    > <br><br>![](images\2020-10_BAS_Pane_Closed_.jpg)<br><br>

    > You can also create a project from the terminal using Yeoman.

## Summary

You've now ...

Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
