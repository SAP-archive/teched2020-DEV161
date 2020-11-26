# Exercise 12 - Add Columns to Worklist

In this exercise, you will add columns to the products list view. This requires changes to the UI (view) and also to the view's logic (controller).

## Exercise 12.1 UI Modifications

After completing these steps, you will have modified the Worklist view of the app to include filters. Some of the modifications are also needed for the logic to execute accordingly.

It is recommended that you type most the code to experience the code editor's capabilities.

1. This time, you'll use a new way of searching for a file using the command palette. From the main menu, select *View | Find Command*, delete the `>`, and type *Worklist*. A list of files whose name begins with *Worklist* is displayed.
    <br><br>![](images/2020-10_BAS_Command_Palette_Search_File_.jpg)<br><br>

2. Click `Worklist.view.xml productsinventory/webapp/view` to open the file in the code editor. 
    <br><br>![](images/2020-10_BAS_Command_Palette_Search_File_Opened_.jpg)<br><br>

3. Add the *Units Ordered* and *Units In Stock* columns to the table, and remove the `hAlign` property from the *unitNumberColumn* column (hover over the property to view its description). In the file, locate the `<columns>` section and add or modify the following code:
    ```xml
                    <columns>
                        <Column id="nameColumn">
                            <Text text="{i18n>tableNameColumnTitle}" id="nameColumnTitle"/>
                        </Column>
                        <Column id="unitNumberColumn">
                            <Text text="{i18n>tableUnitNumberColumnTitle}" id="unitNumberColumnTitle"/>
                        </Column>
                        <Column>
                            <Text text="{i18n>worklistTableUnitsOrderedColumnTitle}"/>
                        </Column>
                        <Column>
                            <Text text="{i18n>worklistTableUnitsInStockColumnTitle}"/>
                        </Column>
                    </columns>

    ```

    <br><br>![](images/2020-10_BAS_Worklist_Columns_Added_.jpg)<br><br>

4. So far, you added the columns titles. Now it's time to add the data. Locate the `<items>` section below the `<columns>` section, and add the following code.
    ```xml
                                <ObjectNumber number="{path: 'UnitsOnOrder', formatter: 'formatter.numberUnit'}" unit="PC"></ObjectNumber>
                                <ObjectNumber number="{path: 'UnitsInStock', formatter: 'formatter.numberUnit'}" unit="PC"></ObjectNumber>
                                
    ```

    <br><br>![](images/2020-10_BAS_Worklist_Cells_Added_.jpg)<br><br>

## Exercise 12.2 - Run the App Locally in the Dev Space

1. Refresh the app's tab that is running the app locally in the dev space for the changes to take effect. 
    >You have three tabs running the app: A tab where the app is running locally in the dev space fetching the data from OData org's Northwind service. A tab where the app is running locally in the dev space fetching the data from the mock server. A tab where the app is running in your Cloud Foundry space fetching the data from OData org's Northwind service. You should refresh the tab where the app is running locally in the dev space fetching the data from OData org's Northwind service. 

2. The Worklist page presents four columns: *Product Name*, *Unit Price*, *Units Ordered*, and *Units in Stock*.
    <br><br>![](images/2020-10_BAS_Preview_Application_Start-5_.jpg)<br><br>


## Summary

With this, you have successfully completed adding columns to an SAPUI5 *Table* control. 

Continue to - [Exercise 13 - Add the Supplier Info to the Details Page](../ex13/README.md)
