# Exercise 11 - Add Breadcrumbs to the Details Page

So far we you improved the view that presented the list of products and thie key properties related to the business scenario at hand. in the next few exercises you'll improve the product's details view.

In this exercise, you will improve app navigation by adding breadcrumbs.

## Exercise 11.1 - UI Modifications - Breadcrumbs

After completing these steps you will have modified the worklist view of the app to include filters. Some of the modifications are also needed in order for the logic to execute accordingly.

It is recommended that you type in most the code in order to experience the code editor's capabilities.

2. In SAP business Application Studio, go to *Object.view.xml* editor tab.

3. Add a *Breadcrumbs* control right below the `<semantic:titleHeading>` element.
    ```xml
        <semantic:titleBreadcrumbs>
            <Breadcrumbs currentLocationText="{ProductName}">
                <Link press=".onNavBack" text="Products"></Link>
            </Breadcrumbs>
        </semantic:titleBreadcrumbs>

    ```

    <br><br>![](images\2020-10_BAS_Object_View_Breadcrumbs_.jpg)<br><br>

## Exercise 11.2 - Run the App Locally in the Dev Space

After completing these steps you will have tested the view look & feel.

4.	Go to the tab where the app is running and refresh it (press [F5]). You can see that the breadcrumbs appear in the view, and you can use them to navigate back to the products worklist view.
    <br><br>![](images\2020-10_BAS_App_Object_View_After_Breadcrumbs_.jpg)<br><br>


## Summary

With this, you have successfully completed adding breadcrumbs to the product's details view, improving user experience and satisfaction.

Continue to - [Exercise 12 - Add Orders List to Details Page](../ex10/README.md)
