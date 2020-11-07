# Exercise 10 - Connect Your Project to SAP Cloud Platform Continuous Integration and Delivery - Update Internationalization (i18n)

In this exercise, we will create a project in a public GitHub repository in which to store your source code, enable SAP Cloud Platform Continuous Integration and Delivery, and configure and run a predefined continuous integration and delivery (CI/CD) pipeline that automatically tests, builds, and deploys your code changes.

## Exercise 10.1 Make a Change in Your Project

After completing these steps, you will have made a change in your project and thereby triggered SAP Cloud Platform Continuos Integration and Delivery. The change is to replace all hard-coded app strings with internationalization (i18n) strings.

1. Expand the *webapp > i18n* folder, and click the *i18n.properties* file to open it.
    <br><br>![Change Description](images/2020-10_BAS_i18n_Open_.jpg)<br><br>

2. Click the following [link](data/i18n.properties?raw=true) to access the *i18n.properties* file. this file contains all the changes you need to internationalize the app's strings.
    >When working with github, if you want to open a link in a new tab, press [CTRL] and click the link.

3. Press [CTRL] + A to copy the file's content to the clipboard.

4. Go back to SAP Business Application Studio and replace the content of the i18n.properties file with the content of the i18n.properties file from github. Press [CTRL] + A to select the file's content in SAP Business Application Studio, Press [DELETE], and then press [CTRL] + V to paste the content of the file from github.

2. Open the **Source Control: Git**.
![Git](./images/bas_git.png)

3. Stage the changed file to the commit.
![Stage File](./images/bas_add_file_commit.png)

4. Specify your commit message. 
![Changed File](./images/bas_commit_message.png)

5. Commit the change.
![Changed File](./images/bas_commit.png)

6. Push the changes to GitHub.
![Push Changes](./images/git_push_bas.png)
This push event automatically triggers SAP Cloud Platform Continuous Integration and Delivery.

## Summary

You've created a project in GitHub to store your source code and successfully configured and run a predefined continuous integration and delivery pipeline that automatically builds, tests and deploys your code changes.

Continue to - [Exercise 11 - Connect Your Project to SAP Cloud Platform Continuous Integration and - Pipeline Monitoring and Results](../ex11/README.md).