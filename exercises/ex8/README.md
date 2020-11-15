# Exercise 8 - Connect Your Project to SAP Cloud Platform Continuous Integration and Delivery - GitHub Setup

In the following exercises (exercises 8 - 11), you will create a project in a public GitHub repository to which you'll store your source code, enable SAP Cloud Platform Continuous Integration and Delivery, and configure and run a predefined continuous integration and delivery (CI/CD) pipeline that automatically tests, builds, and deploys your code changes.

## Exercise 8.1 Create a GitHub Repository

After completing these steps, you will have created a public GitHub repository to which you'll store the source code of your project.          
   >For this exercise, you need to have a GitHub user.

1. Open and sign in to [GitHub]( https://github.com/).

2. In the *Repositories* tab, choose *New*.
   <br><br>![Create GitHub Repo](./images/GH_newRepository.png)<br><br>
   
3. As *Repository name*, enter *products-inventory*. Don't select any of the *Initialize this repository with...* checkboxes.

4. Choose *Create repository*.
   <br><br>![Create GitHub Repo](./images/GH_createGitRepo.png)<br><br>

5. Copy the HTTPS URL of your newly created GitHub repository.
   <br><br>![Copy GitHub URL](./images/GH_copyGitHubURL.png)<br><br>


## Exercise 8.2 Create a Personal Access Token for GitHub

After completing these steps, you will have created a personal access token to authenticate against GitHub.

To create a personal access token, which you can use instead of a password, follow the steps described in [Creating a personal access token](https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token).


## Exercise 8.3 Connect Your GitHub Repository with Your SAP Fiori Project

After completing these steps, you will have added your SAP Fiori project sources to your GitHub repository.

6. In SAP Business Application Studio, open a new terminal, and navigate to your project's root folder.
   <br><br>![Open Terminal](./images/openTerminal.png)<br><br>

7. Configure your GitHub user information. Enter your email address and user name. You can use the email address that you used to register your GitHub account:
   ```
   git config --global user.email "you@example.com"
   git config --global user.name "Your Name"
   ```

7. Initialize a local GitHub repository and add the project sources to it. Run the following commands:

    ```
    git init
    git add .
    git commit -m "Push project content to GitHub"
    ```

8. Link the local git repository to the remote GitHub repository that you created in exercise 8.1. 
   ```
   git remote add origin <remote GitHub repository url>
   ```

8. Create the project's *main* branch in the remote repository:
   ```
   git branch -M main
   ```

9. Push the commit with your project content to the remote GitHub repository:
   ```
   git push -u origin main
   ```

10. When prompted, enter your GitHub user name and password (or your personal access token).

## Summary

You've created a project in GitHub and stored in it your app's source code.

Continue to - [Exercise 9 - Connect Your Project to SAP Cloud Platform Continuous Integration and Delivery Service - Setup the Service](../ex9/README.md).
