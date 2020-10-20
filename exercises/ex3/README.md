# Exercise 3 - Exercise 2 Description

- How to create an SAPUI5 application for SAP Cloud Platform, Cloud Foundry environment
- How to test-run the app locally in the dev space

## Exercise 2.1 Sub Exercise 1 Create new SAP Fiori project

After completing these steps you will have created...

1. In the **Welcome Page** click **Create project from a template**.

    ![Open Dev Space](images/03-01-02&#32;AppStudio&#32;Welcome&#32;Tab&#32;withOUT&#32;Extensions&#32;Loaded&#32;Notification_.jpg)

    >If the Welcome Page does not appear, in the menu bar, select **View | Find Command** to open the **command palette** and select the command **SAP Business Application Studio: Welcome Page**. The command palette is opened at the top-center of the SAP Business Application Studio window.

    >![Welcome Page from command palette](images/03-01-03&#32;AppStudio&#32;Welcome&#32;Page&#32;from&#32;Command&#32;Palette_.jpg)

    >The easiest way to develop an SAP Fiori freestyle app from scratch is to create it from a template. To continue developing an existing application, the best practice is to use git source code management and clone the repository.

    >Using the UI wizard you can at any point click the `reset` button to reset the wizard at the top-right of the wizard screen, click the `Back` button to go back to the previous step, or click the specific wizard step to go back to that step.
    >For convenience, click the **Explorer** view button to close the `Explorer` view.

    > You can also create a project from the terminal using Yeoman.

2. Make sure that the target folder is `/home/user/projects`, select the **SAP Fiori Freestyle Project** template, and click **Next**.

    ![Fiori project template](images/03-03&#32;AppStudio&#32;Fiori&#32;Project&#32;Template_.jpg)

3. For **Target Running Environment**, select the following, and click **Next**.

    | Step | Parameter | Value |
    |:-----|:----------|:------|
    | A | Select the target running environment | **Cloud Foundry** |
    | B | Select the template you want to use | **SAPUI5 Application** |

    ![fiori project template](images/03-04&#32;AppStudio&#32;Fiori&#32;Project&#32;Template&#32;Target&#32;Running&#32;Environment_.png)

4. For **Project Name**, enter `FioriDemo`, and click **Next**.

    ![Fiori project template - project name](images/03-05&#32;AppStudio&#32;Fiori&#32;Project&#32;Template&#32;Project&#32;Name.jpg)

5. For **HTML5 Applications**, if you plan to integrate the app to a launchpad site, select **Managed by SAP Cloud Platform** and provide a unique service name. Otherwise, select **Standalone Approuter**, and click **Next**.

    ![Standalone Approuter](images/03-06-01&#32;AppStudio&#32;HTML5&#32;Applications&#32;Runtime.png)

    >The application router is the single point-of-entry for an application running in the Cloud Foundry environment on SAP Cloud Platform. The application router is used to serve static content, authenticate users, rewrite URLs, and forward or proxy requests to other micro services while propagating user information.

    >To simplify the tutorial the Standalone Approuter option is used.

6. For **Basic Attributes**, select the following, and click **Next**.

    | Step | Parameter | Value |
    |:-----|:----------|:------|
    | A | Enter an HTML5 module name | **`BusinessPartners`** |
    | B | Do you want to add authentication | **No** |
    | C | Enter a namespace | **`ns`** |
    | D | Do you want to enable Karma tests? | **No** |

    ![Fiori project template - basic attributes](images/03-06&#32;AppStudio&#32;Fiori&#32;Project&#32;Basic&#32;Attributes.jpg)

7. For **View Name**, select the following, and click **Next**.

    | Step | Parameter | Value |
    |:-----|:----------|:------|
    | A | Enter a view name | **`Suppliers`** |
    | B | Do you want to add a data service | **Yes** |

    ![Fiori project template - view name](images/03-07&#32;AppStudio&#32;Fiori&#32;Project&#32;View&#32;Name.png)

8. For **Consume Services**, select the following, and click **Next**.

    | Step | Parameter | Value |
    |:-----|:----------|:------|
    | A | Select a system | **My SAP systems** |
    | B | Select a source | **`ES5 [Catalog]`** |
    | C | Select a service | **`GWSAMPLE_BASIC`** |

    ![Fiori project template - consume services](images/03-08&#32;AppStudio&#32;Fiori&#32;Project&#32;Providers.jpg)

    >A notification that the project has been generated appears at the bottom right of the screen.

    ![Fiori project template - project generated](images/03-08-02&#32;AppStudio&#32;Fiori&#32;Project&#32;Project&#32;Generated.jpg)

9. Click **Open in New Workspace** in the notification or **File > Open Workspace**, and choose `FioriDemo`.

    ![AppStudio open workspace](images/03-09&#32;AppStudio&#32;Open&#32;Workspace_.jpg)

    >The **Explorer** view opens and you can see the `FioriDemo` project, its folder structure, and files. If not, you can click the **Explorer** view button at the top left of the screen.

    >The status bar color changes to blue, indicating that a workspace is open.



## Exercise 2.2 Sub Exercise 2 Description

After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc = 0.
    response->set_status( i_code = 200
                     i_reason = 'Everything is fine').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex2/images/02_02_0010.png)

## Summary

You've now ...

Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
