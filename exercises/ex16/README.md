# Exercise 16 - Useful CF Commands

In this exercise, you will go through a basic set of CF commands that are useful in the context of SAP Fiori development.

## Exercise 16.0 - Preparations

After completing these steps, you will know which CF commands are available, what they do and try out a few of the available commands.

1. Open a new terminal using *Terminal | New Terminal* or *[CTRL] + ~* keyboard shortcut.
<br><br>![](images/2020-10_BAS_Terminal_Open_.jpg)<br><br>

2. Double-click the terminal tab to maximize it.
<br><br>![](images/2020-10_BAS_Terminal_Maximize_.jpg)<br><br>

## Exercise 16.1 - cf help

3. Run *cf help* to get the list of all available commands.
<br><br>![](images/2020-10_BAS_CF_Help_.jpg)<br><br>

4. To show a list of all available commands with a single line description for each command run *cf help -a*.
<br><br>![](images/2020-10_BAS_CF_Help_-a_.jpg)<br><br>

    >Tip 1: Run the *clear* command to cealr the terminal

    >Tip 2: Instead of executing *cf help -a*, run *cf help -a | more. the commands will be printed to the terminal one screen at a time. To see the next line press the [ENTER] button. To see the next screen press the [SPACE] button.

5. Digging one level deeper, getting help for a spcific command, run *cf help [COMMAND]* e.g. *cf help login*.
<br><br>![](images/2020-10_BAS_CF_Help_Login_.jpg)<br><br>

## Exercise 16.2 - cf logout

6. In a previous exercise we saw how to log in to CF using the *command palette*. In the last step we saw how to log in to CF using the command line. To log out from CF use *cf logout*. You'll get indication of successful log out both in the terminal as well as in the *status bar* at the bottom left of the screen.
<br><br>![](images/2020-10_BAS_CF_Logout_.jpg)<br><br>

## Exercise 16.3 - cf html5-list

7. To get the list of SAP Fiori / SAPUI5 deployed to the CF space you're logged in to, run *cf html5-list*.
<br><br>![](images/2020-10_BAS_CF_html5-list_.jpg)<br><br>
    >You need to be logged in to your CF space to perform this command.

## Exercise 16.4 - cf mtas

*cf mtas* lists all deployed mluti-target apps. In the context of this exercise, it provides the *mta id* that is needed to undeploy a multi-target app.

## Exercise 16.5 - cf undeploy

Usually you should start with the deploy finctionality. However, since the appis laready deployed, you'll start with the undeploy functionality.

8. To undeploy a multi-target applications (MTA) deployed to the CF space you're logged in to, such as the app you've just deployed, run *cf undeploy [mta id] --delete-services --delete-service-keys -f*. The *mta id* of the app you've just deployed appear in the output of the command you performed in the previous step. Therefore, if you want to undeploy the app, run *cf undeploy products-inventory --delete-services --delete-service-keys -f*
<br><br>![](images/2020-10_BAS_CF_Undeploy_.jpg)<br><br>
    >In the SCP Cockpit, in the CF space, you can see that the app and all its bound sevice instances were removed.

    ><br><br>![](images/2020-10_SCP_CF_Space_After_Undeploy_Applications_.jpg)<br><br>

    ><br><br>![](images/2020-10_SCP_CF_Space_After_Undeploy_Service_Instances_.jpg)<br><br>

## Exercise 16.6 - cf deploy

9. To deploy (or re-deploy) your MTA, run *cf deploy MTA*. For this demo the MTA resides within the mta_archives folder. Therefore, run *cf deploy mta_archives/products-inventory-0.0.1.mtar*.
<br><br>![](images/2020-10_BAS_CF_Deploy_.jpg)<br><br>
    >In the SCP Cockpit, in the CF space, you can see that the app was deployed and all its sevice instances were created and binded.

    >![](images/2020-10_SCP_CF_Space_After_Deploy_Applications_.jpg)<br><br>

    >![](images/2020-10_SCP_CF_Space_After_Deploy_Service_Instances_.jpg)<br><br>

## Exercise 16.7 - Run the App on CF

10. You're welcome to test-run the app deployed on CF as you did in a previous exercise.

## Summary

Congratulations, you completed the [Useful CF Commands](#useful-cf-commands) exercise!

It is a set of powerful tools that lets you interact with SAP Business Technology Platform without leaving SAP Business Application Studio. This can save you a lot of time!

Return to [DEV161 - Extend SAP S/4HANA with a Custom UI on SAP Business Technology Platform](../../README.md).
