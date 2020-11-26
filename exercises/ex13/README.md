# Exercise 13 - Add the Supplier Info to the Details Page

So far, you improved the view that presented the list of products and the key properties related to the business scenario at hand (inventory management). In the next few exercises, you'll improve the product's Details view.

## Exercise 13.1 - UI Modifications

After completing these steps, you will have added supplier info to the product's Details view. Some of the modifications are also needed for the logic to run accordingly.

It is recommended that you type most the code to experience the code editor's capabilities.

1. In the locally running app, click a product to view its details.

    <br><br>![](images/2020-10_BAS_App_Object_View_.jpg)<br><br>

2. In SAP Business Application Studio, open the file that contains the product's details, the `Object.view.xml` file in the `webapp` folder.

3. Add an XML namespace for "sap.ui.layout.form".
    ```xml
        xmlns:form="sap.ui.layout.form"
    ```

    <br><br>![](images/2020-10_BAS_Object_View_xmlns_form_.jpg)<br><br>

4. Below the `<semantic:headerContent>` section, add a `<semantic:content>` section, and, in it, a `<VBox>` element that contains a `SimpleForm` control which will contain the supplier details. 
    ```xml
            <semantic:content>
                <VBox>
                    <form:SimpleForm title="{i18n>objectSupplierInfo}" layout="ResponsiveGridLayout" singleContainerFullSize="false" columnsXL="1" columnsL="1" visible="{= ${objectView>/busy} ? false : true}">
                        <form:content>
                            <Label text="{i18n>objectSupplierID}"></Label>
                            <Text text="{Supplier/SupplierID}"></Text>
                            <Label text="{i18n>objectCompanyName}"></Label>
                            <Text text="{Supplier/CompanyName}"></Text>
                            <Label text="{i18n>objectContactName}"></Label>
                            <Text text="{Supplier/ContacName}"></Text>
                            <Label text="{i18n>objectContactTitle}"></Label>
                            <Text text="{Supplier/ContactTitle}"></Text>
                            <Label text="{i18n>objectAddress}"></Label>
                            <Text text="{Supplier/Address}, {Supplier/City}, {Supplier/PostalCode}, {Supplier/Country}"></Text>
                        </form:content>
                    </form:SimpleForm>
                </VBox>
            </semantic:content>

    ```

    <br><br>![](images/2020-10_BAS_Object_View_Supplier_Info_.jpg)<br><br>

## Exercise 13.2 - Run the App Locally in the Dev Space

After completing these steps, you will have tested the view's look and feel.

5.	Go to the tab where the app is running and refresh it (press [F5]). You can see the look and feel of how the supplier info will appear when you complete this exercise.
    <br><br>![](images/2020-10_BAS_App_Object_View_After_View_.jpg)<br><br>

## Exercise 13.3 - Logic Modifications (Controller)

After completing these steps, you will have modified the logic of the app's product's Details view to present the product's supplier info.

It is recommended that you type most the code to experience the code editor's capabilities.

6. In SAP business Application Studio, open the file that contains the product's details logic, the `Object.controller.js` file.

    <br><br>![](images/2020-10_BAS_Object_Controller-1_.jpg)<br><br>

7. Using the *Outline* view, locate the `_bindView` function.

    <br><br>![](images/2020-10_BAS_Object_Controller-2_.jpg)<br><br>

8. Use OData's `$expand` option to retrieve the product's supplier and order details. You'll use the `order_details` information in another exercise.
    ```javascript
                    parameters: {
                        expand: "Supplier, Order_Details/Order"
                    },
    ```

    <br><br>![](images/2020-10_BAS_Object_Controller-3_.jpg)<br><br>

## Exercise 13.4 - Run the App Locally in the Dev Space

After completing these steps, you will have tested the product's Details view with the product's supplier info included.

1.	Go to the tab where the app is running, and refresh it (press [F5]). You can see the result of adding the supplier info to the product's Details view.
    <br><br>![](images/2020-10_BAS_Object_Controller-4_.jpg)<br><br>


## Summary

With this, you have successfully completed adding the product's supplier info to the product's Details view using the OData `expand` option.

Continue to - [Exercise 14 - Add Breadcrumbs to the Details Page](../ex14/README.md)
