# Exercise 10 - Connect Your Project to SAP Continuous Integration and Delivery - Update Internationalization (i18n)

In exercises 8 - 11, you will create a project in a public GitHub repository to which you'll store your source code, enable SAP Continuous Integration and Delivery, and configure and run a predefined continuous integration and delivery (CI/CD) pipeline that automatically tests, builds, and deploys your code changes.

In this exercise, you will make a simple change to your app and push the updated code to GitHub. This will trigger the pipeline that you configured previously. 

It is recommended that immediately after you push the code changes to GitHub, you proceed to the next exercise, where you'll be able to monitor the running build of the pipeline.

## Exercise 10.1 - Make a Change in Your Project

After completing these steps, you will have made a change in your project and thereby triggered SAP Continuous Integration and Delivery. The change is to replace all hard-coded app strings with internationalization (i18n) strings.

1. Expand the *webapp > i18n* folder, and click the *i18n.properties* file to open it.
    <br><br>![Change Description](images/2020-10_BAS_i18n_Open_.jpg)<br><br>

2. Click [here](data/i18n.properties?raw=true) to access the `i18n.properties` file. This file contains all the changes you need to internationalize the app's hard-coded strings.
    >When working with github, if you want to open a link in a new tab, press [CTRL] and click the link.

3. Press [CTRL] + [A] and then [CTRL] + [C] to copy the file's content to the clipboard.

4. Go back to SAP Business Application Studio and replace the content of the `i18n.properties` file with the content of the `i18n.properties` file from GitHub. Press [CTRL] + [A] to select the file's content in SAP Business Application Studio, press [DELETE], and then press [CTRL] + [V] to paste the content of the file from the clipboard.

## Exercise 10.2 - Update the Project's Git Repository

1. Open the *Source Control: Git* view.
    <br><br>![Git](./images/BAS_Git_View_After_Change_.png)<br><br>

2. Stage the changed file.
    <br><br>![Stage File](./images/BAS_Git_View_Stage_Change_.png)<br><br>

3. Specify your commit message. 
    <br><br>![Changed File](./images/BAS_Git_View_Commit_Message_.png)<br><br>

4. Commit the change.
    <br><br>![Changed File](./images/BAS_Git_View_Commit_.png)<br><br>

5. Push the changes to GitHub. This push event automatically triggers SAP Continuous Integration and Delivery.
    <br><br>![Push Changes](./images/git_push_bas.png)<br><br>

## Summary

You've successfuly made a code change to your app, pushed it to the GitHub repository, which triggered a build of the continuous integration and delivery pipeline you created previously.

Continue to - [Exercise 11 - Connect Your Project to SAP Continuous Integration and - Pipeline Monitoring and Results](../ex11/README.md).
