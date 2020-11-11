# Exercise 5 - Add Data Filters

In this exercise, you will add filters to the app for the list of products, according to their inventory level: Shortage, Low, and Normal. This requires changes to the UI (view) and also to the view's logic (controller).

## Exercise 5.1 - UI Modifications

After completing these steps, you will have modified the Worklist view of the app to include filters. Some of the modifications are also needed for the logic to execute accordingly.

It is recommended that you type most of the code to experience the code editor's capabilities.

1. Choose *webapp > view* and click the `Worklist.view.xml` file.
    <br><br>![](images/2020-10_BAS_Worklist_View_Code_Editor_Open_.jpg)<br><br>
    >The `Worklist.view.xml` file is opened in a code editor tab.
    >![](images/2020-10_BAS_Worklist_View_Code_Editor_Opened_.jpg)<br><br>

    >Tip 1: You can get additional screen real estate for the code editor tab by closing the *Explorer* view. You can get even more real estate by double-clicking the tab's title.

    >Tip 2: Hovering over a control or a control property pops up a tooltip with information on it, as well as a link to its API Reference. Click the API Reference link to open it in a new browser tab.
    ><br>![](images/2020-10_BAS_Worklist_View_Code_Editor_Code_Completion_Control_.jpg)<br><br>

2. Add an *IconTabBar* control before the *Table* control.
```XML
            <IconTabBar id="iconTabBar" select=".onFilterSelect" class="sapUiResponsiveContentPadding">
                <items>
                </items>
            </IconTabBar>
```

3. Between `<items>` and `</items>`, enter `<`. The code completion is triggered.
    <br><br>![](images/2020-10_BAS_Worklist_View_Code_Editor_Code_Completion_Control_.jpg)<br><br>

    >Tip 1: You can select which control to use with the mouse or by using the arrow keys on the keyboard.

    >Tip 2: You can get more information on a control by clicking the (i) icon to the right of the control or using [CTRL] + [SPACE] on the keyboard.

4. Select the *IconTabFilter* control, and use [CTRL] + [SPACE] to view a list of its properties.
    <br><br>![](images/2020-10_BAS_Worklist_View_Code_Editor_Control_Properties_List_.jpg)<br><br>

    >Tip 1: Filter the list of properties by typing part of it.

    >Tip 2: You can select which property to use with the mouse or by using the arrow keys on the keyboard.

    >Tip 3: You can get more information on a property by clicking the (i) icon to the right of the control or using [CTRL] + [SPACE] on the keyboard.

5. Select the *showAll* property.
    <br><br>![](images/2020-10_BAS_Worklist_View_Code_Editor_Code_Completion_Property_showAll_.jpg)<br><br>

6. Control properties can also have their value selected from a list. Delete the *false* value and use [CTRL] + [SPACE] to present the list of available values.
    <br><br>![](images/2020-10_BAS_Worklist_View_Code_Editor_Code_Completion_Property_showAll_Values_.jpg)<br><br>

7. Proceed with entering the code until you have the following code in place:
```XML
            <IconTabBar id="iconTabBar" select=".onFilterSelect" class="sapUiResponsiveContentPadding">
                <items>
                    <IconTabFilter showAll="true" count="{worklistView>/productsCount}" text="{i18n>worklistFilterAllProducts}" key="all"></IconTabFilter>
                    <IconTabSeparator ></IconTabSeparator>
                    <IconTabFilter icon="sap-icon://complete" iconColor="Positive" text="{i18n>worklistFilterNormalStockProducts}" key="Normal"></IconTabFilter>
                    <IconTabFilter icon="sap-icon://message-warning" iconColor="Critical" text="{i18n>worklistFilterLowStockProducts}" key="Low"></IconTabFilter>
                    <IconTabFilter icon="sap-icon://message-error" iconColor="Negative" text="{i18n>worklistFilterShortageStockProducts}" key="Shortage"></IconTabFilter>
                </items>
            </IconTabBar>

```

   <br><br>![](images/2020-10_BAS_Worklist_View_Code_Editor_Filters_Added_.jpg)<br><br>

8. You probably noticed that the `Worklist.view.xml` file, including its folders hierarchy, is marked as error. The *Status Bar* will show error too.
   <br><br>![](images/2020-10_BAS_Worklist_View_Code_Editor_Error_Explorer_.jpg)<br><br>

   ![](images/2020-10_BAS_Worklist_View_Code_Editor_Error_Status_Bar_.jpg)<br><br>

9. Open the *Problems* tab by clicking the problems indication area in the status bar or by selecting *View | Problems* from the menu bar.
   <br><br>![](images/2020-10_BAS_Worklist_View_Problems_Pane_.jpg)<br><br>

10. According to the problem description: *The aggregation \"content\" has a cardinality of 0..1 and may only contain one element*. Therefore, wrap the *IconTabBar* and *Table* controls in a `<VBox>` element, and indent accordingly.
```XML
            <VBox>
                <IconTabBar id="iconTabBar" select=".onFilterSelect" class="sapUiResponsiveContentPadding">
                    <items>
                        <IconTabFilter showAll="true" count="{worklistView>/productsCount}" text="{i18n>worklistFilterAllProducts}" key="all"></IconTabFilter>
                        <IconTabSeparator ></IconTabSeparator>
                        <IconTabFilter icon="sap-icon://complete" iconColor="Positive" text="{i18n>worklistFilterNormalStockProducts}" key="Normal"></IconTabFilter>
                        <IconTabFilter icon="sap-icon://message-warning" iconColor="Critical" text="{i18n>worklistFilterLowStockProducts}" key="Low"></IconTabFilter>
                        <IconTabFilter icon="sap-icon://message-error" iconColor="Negative" text="{i18n>worklistFilterShortageStockProducts}" key="Shortage"></IconTabFilter>
                    </items>
                </IconTabBar>
                <Table
                    id="table"
                    width="auto"
                    items="{
                        path: '/Products',
                        sorter: {
                            path: 'ProductName',
                            descending: false
                        }
                    }"
                    noDataText="{worklistView>/tableNoDataText}"
                    busyIndicatorDelay="{worklistView>/tableBusyDelay}"
                    growing="true"
                    growingScrollToLoad="true"
                    updateFinished=".onUpdateFinished">

                    <headerToolbar>
                        <OverflowToolbar>
                            <Title
                                id="tableHeader"
                                text="{worklistView>/worklistTableTitle}"
                                level="H3"/>
                            <ToolbarSpacer />
                            <SearchField
                                id="searchField"
                                tooltip="{i18n>worklistSearchTooltip}"
                                search=".onSearch">
                                <layoutData>
                                    <OverflowToolbarLayoutData
                                        maxWidth="200px"
                                        priority="NeverOverflow"/>
                                </layoutData>
                            </SearchField>
                        </OverflowToolbar>
                    </headerToolbar>

                    <columns>
                        <Column id="nameColumn">
                            <Text text="{i18n>tableNameColumnTitle}" id="nameColumnTitle"/>
                        </Column>
                        <Column id="unitNumberColumn" hAlign="End">
                            <Text text="{i18n>tableUnitNumberColumnTitle}" id="unitNumberColumnTitle"/>
                        </Column>
                    </columns>

                    <items>
                        <ColumnListItem
                            type="Navigation"
                            press=".onPress">
                            <cells>
                                <ObjectIdentifier
                                    title="{ProductName}"/>
                                <ObjectNumber
                                    number="{
                                        path: 'UnitPrice',
                                        formatter: '.formatter.numberUnit'
                                    }"
                                    unit="{QuantityPerUnit}"/>
                            </cells>
                        </ColumnListItem>
                    </items>
                </Table>
            </VBox>
		</semantic:content>
```

11. Test - Refresh the tab where the app is running to see the UI changes.
   <br><br>![](images/2020-10_BAS_App_After_UI_Changes_.jpg)<br><br>

    >Clicking the filters has no impact as the logic was not implemented. This will be the next step in the exercise.


## Exercise 5.2 - Logic Modifications (Controller)

After completing these steps, you will have modified the logic of the Worklist view of the app to present the list of products according to the selected filter.

12. Choose *webapp > controller* and click the `Worklist.controller.js` file.
    <br><br>![](images/2020-10_BAS_Worklist_Controller_Code_Editor_Open_.jpg)<br><br>
    >The `Worklist.controller.js` file opens in a code editor tab.
    >![](images/2020-10_BAS_Worklist_Controller_Code_Editor_Opened_.jpg)<br><br>

13. Click *Outline* at the top-right corner of the page to open the outline view. Locate the *onUpdateFinished* function, and click it. The code editor focuses on this function.
    <br><br>![](images/2020-10_BAS_Worklist_Controller_Outline_.jpg)<br><br>

14. The following code will add the total product count as a property to the model. This property is presented at the top left corner of the view when clicking the *showAll* filter. Add it just below the end of the `variables` declaration section (*var* statement).
```javascript
            //set products count
            this.getModel("worklistView").setProperty("/productsCount", iTotalItems);
```

   <br><br>![](images/2020-10_BAS_Worklist_Controller_onUpdatedFinished_Updated_.jpg)<br><br>

15. Refresh the app to see the effect of this change.
   <br><br>![](images/2020-10_BAS_Worklist_Controller_onUpdatedFinished_Updated_App_.jpg)<br><br>

16. Now it's time to handle the user action of clicking the filters. In the Outline view, click the *onRefresh* function, and add the following code above it.

```javascript
        onFilterSelect: function(oEvent){
            var oTable = this.byId("table");
            var sKey = oEvent.getParameter("key");
            var oFilter = this._createFilterByTabKey(sKey);
            var oBinding = oTable.getBinding("items");
            oBinding.filter(oFilter);
        },

        _createFilterByTabKey: function(sKey){
            switch(sKey) {
                case "Normal":
                    return new Filter("UnitsInStock", FilterOperator.GT, 15);
                case "Low":
                    return new Filter("UnitsInStock", FilterOperator.BT, 1, 15);
                case "Shortage":
                    return new Filter("UnitsInStock", FilterOperator.LE, 0);
                default: 
                return [];
            }
        },

```

   <br><br>![](images/2020-10_BAS_Worklist_Controller_Filters_.jpg)<br><br>

## Exercise 5.3 - Run the App Locally in the Dev Space

15. Refresh the app's tab for the changes to take effect. Click the various filters and see how the list of products changes according to the selected filter.
   <br><br>![](images/2020-10_BAS_Worklist_Controller_Filters_Low_.jpg)<br><br>

16. Close the *Outline* view and all open tabs in the editors section, except the *Welcome* tab.

    >Tip: To close all open tabs except the *Welcome* tab, right-click the *Welcome* tab title and select *Close Others*. Explore this to see additional options.


## Summary

You have successfully completed the development of an SAP Fiori app using SAP Business Application Studio, including test-running the app locally in the dev space. In this exercise, you learned about high productivity tools that are available out-of-the-box in SAP Business Applications Studio, such as code completion, API reference, outline, problems view.

Continue to - [Exercise 6 - Connect to Backend](../ex6/README.md)
