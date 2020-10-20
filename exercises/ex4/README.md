# Exercise 4 - Exercise 2 Modify the app

In this exercise, we will create...

## Exercise 2.1 Sub Exercise 1 Open the layout editor

Open the layout editor in SAP Business Application Studio to easily make a few changes. In this case, you will make changes so that data from the backend service is displayed when the app is running.

1. Choose **`FioriDemo` > `BusinessPartners` > `webapp` > `view`** and right-click the `Suppliers.view.xml` file that you created with the template in a previous step.

2. Choose **Open With > Layout Editor**.

    ![Open with Layout Editor](images/04-01&#32;AppStudio&#32;Open&#32;Layout&#32;Editor_.jpg)

    >To have the Layout Editor option available after opening the workspace, you may need to wait a bit for the Layout Editor extension to be loaded.

    >The **Suppliers** view is opened in the **Layout Editor**.

    >![Layout Editor Opened](images/04-01-02&#32;AppStudio&#32;Open&#32;Layout&#32;Editor.jpg)

3. You can optionally choose to open it with the code editor and see how modifications in the Layout Editor are manifested in the code editor.

    ![Open code editor](images/04-03&#32;AppStudio&#32;Open&#32;Code&#32;Editor-XML_.jpg)

    >The **Suppliers** view is opened in the code editor in a tab next to the **Layout Editor**.

    >![Code editor opened](images/04-03-02&#32;AppStudio&#32;Open&#32;Code&#32;Editor-XML.jpg)

4. For convenience, place the code editor below the Layout Editor. Use the drag & drop functionality.

    ![Drag-Drop editor](images/04-04&#32;AppStudio&#32;Drag-Drop&#32;Code&#32;Editor.jpg)

    >The **Layout Editor** and code editor are stacked so you can see how making changes to one will be reflected on the other.

    >![Editor dropped](images/04-04-02&#32;AppStudio&#32;Drag-Drop&#32;Code&#32;Editor.jpg)



## Exercise 2.2 Sub Exercise 2 Make changes to the UI

Make some changes using the layout editor, with no need to do any coding.

1. In the **Controls** pane, enter `List` to filter the controls list in the search box.

    ![Filter List control](images/05-01&#32;AppStudio&#32;Layout&#32;Editor&#32;Filter&#32;Controls-List.jpg)

2. Drag the **List** control and drop it on the **View** control in the canvas.

    ![Drag and drop](images/05-02&#32;AppStudio&#32;Layout&#32;Editor&#32;List&#32;Dropped_.jpg)

3. Select the **Standard List Item** control by clicking it (the breadcrumb indicates which control is selected) and, in the **Entity Set** property in the **Properties** pane, click the Bind icon.

    ![Open entity set bind window](images/05-03&#32;AppStudio&#32;Layout&#32;Editor&#32;Bind&#32;to&#32;Entity&#32;Set_.jpg)

    >The **Select Entity Set** view is displayed.

4. Select the **Define entity set and set the selected control as template** option, and in the **Entity Set** dropdown list, choose the `BusinessPartnerSet` entity set. Click **Bind** to complete the operation.

    ![entity set bind window](images/05-04&#32;AppStudio&#32;Layout&#32;Editor&#32;Bind&#32;to&#32;Entity&#32;Set_.jpg)

    >The space of the **Select Entity Set** view may be to narrow to show all options. In case you do not see the **Define entity set and set the selected control as template** option, scroll down in the **Select Entity Set** view to make it available.

    >The bind operation is reflected in both the **Layout Editor** and the code editor.

    >![entity set bind window](images/05-04-02&#32;AppStudio&#32;Layout&#32;Editor&#32;Bind&#32;to&#32;Entity&#32;Set_.jpg)

5. In the **Properties** pane, in the **Title** property, click the **Bind** icon.

    ![open Title bind window](images/05-05&#32;AppStudio&#32;Layout&#32;Editor&#32;Bind&#32;Title_.jpg)

    >The **Data Binding** view is displayed.

6. Click the **Clear expression** (eraser) icon to clear the default text, and in the data fields double click  `CompanyName`. Click **Bind** to complete the operation.

    ![Title bound](images/05-06&#32;AppStudio&#32;Layout&#32;Editor&#32;Bind&#32;Title_.jpg)

7. Repeat the last two steps for the **Description** property in the **Properties** pane. Choose  `BusinessPartnerID`.

    ![Bind Description](images/05-07&#32;AppStudio&#32;Layout&#32;Editor&#32;Bind&#32;Description_.jpg)


## Exercise 2.2 Sub Exercise 2 Test run the application

Run your new application to test it.

1. Open the **Run Configurations** view.

    ![Open Run Configurations](images/06-01&#32;AppStudio&#32;Run&#32;Configurations_.jpg)

2. Click **+** to create a new **Run Configurations**.

    ![Create new run configuration](images/06-02&#32;AppStudio&#32;Run&#32;Configurations_.jpg)

    >Creating a new **Run Configuration** launches the command palette, a text-based mini wizard. The command palette is opened at the top-center of the SAP Business Application Studio window.

3. When "What would you like to run?" question appears, select **`BusinessPartners`**.

    >![run configuration select BusinessPartners](images/06-02-01&#32;AppStudio&#32;Run&#32;Configurations_.jpg)

4. For the next steps of the wizard, select the following:

    | Step | Parameter | Value |
    |:-----|:----------|:------|
    | A | Select a runnable file | **`index.html`** |
    | B | Select a UI5 version | **latest** |
    | C | Enter a name | `Run BusinessPartners (ES5)` |

    >A new run configuration is generated for the `FioriDemo` project.

5. Expand the run configuration to display the services that can be bound.

    ![Bindable objects](images/06-04&#32;AppStudio&#32;Run&#32;Configurations_.jpg)

    >SAP Business Application Studio allows you to test your app with resources.

6. To bind to the destination, click the **Bind** icon to the right of the destination resource to get a list of available destinations.

    ![Bind to Destination](images/06-05&#32;AppStudio&#32;Run&#32;Configurations&#32;Bind&#32;Destination_.jpg)

7. Select the `ES5` destination from the list.

    ![Select Destination](images/06-05-02&#32;AppStudio&#32;Run&#32;Configurations&#32;Bind&#32;Destination_.jpg)

    >Once the destination has been bound, the **Bind** icon turns green.

    >To unbind the destination, click the **Unbind** icon.

    >![Destination is bound](images/06-05-03&#32;AppStudio&#32;Run&#32;Configurations&#32;Bind&#32;Destination_.jpg)

8. Hover over the run configuration and click the Run Module icon.  

    ![Running the app locally](images/06-06&#32;AppStudio&#32;Run&#32;Configurations&#32;Run_.jpg)

9. Wait for the **A service is listening to port 6004** notification and then click the button to open the app.

    >The left side view changes to the debug view and the status bar color changes to orange to indicate that the app is running in debug mode.

    >If you are running the app for the first time, the button in the notification will say **Expose and Open**. Otherwise it will say **Open in New Tab**.

    ![App is running locally](images/06-07&#32;AppStudio&#32;Run&#32;Configurations&#32;Run_.jpg)

    >Some of the notifications appear on the screen for a short period of time.

    >You may optionally add a port description.

    >You may need to authenticate yourself to access the backend. Use your ES5 username and password.

    The app is opened in a new tab and a list of suppliers is displayed.

    ![SAP Fiori app is running](images/AppStudio&#32;Run&#32;Configurations-16.jpg)


## Exercise 2.2 Sub Exercise 2 Stop the running application

After completing these steps you will have...

1. Return to the SAP Business Application Studio tab.

2. In the **Debug** view click the Stop icon.

    ![Stop running app](images/05-02&#32;AppStudio&#32;Stop&#32;Running&#32;App_.jpg)

    >The status bar background color changes from orange to blue.

    >You can re-run the app clicking the Start Debugging icon in the **Debug** view or clicking the Run Module icon in the **Run Configurations** view.



## Summary

With this, you have successfully completed the development of an SAP Fiori app using SAP Business Application Studio, including test-running the app locally in the dev space. In this tutorial, you learned about high productivity tools that are available out-of-the-box in SAP Business Applications Studio, such as: templates and wizards, command palette, Layout Editor, local run, and more.

Continue to - [Exercise 3 - Excercise 3 ](images/../ex3/README.md)
