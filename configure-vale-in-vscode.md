# How to enable Vale linting in VSCode

You must complete the following prerequisites before you begin to install Vale:

| Task | Reason |
|----|----|
| [Trust your workspace](https://code.visualstudio.com/docs/editing/workspaces/workspace-trust#_trusting-a-workspace) in VSCode. | This helps extensions work as desired in your workspace. |
| [Show file extensions in Windows Explorer](https://support.microsoft.com/en-us/windows/common-file-name-extensions-in-windows-da4a4430-8e76-89c5-59f7-1cdbbc75cb01). | It helps avoid confusion when copy-pasting file name or when dragging a file on a command window to get its path. |
| [Update VSCode](https://code.visualstudio.com/docs/supporting/FAQ#_vs-code-versions) to the latest version. | "Because it's there!" |

## Configure to use the Vale extension in VSCode

1. Clone the GitHub repository [https://github.com/ashishguptaiitb/koreaidocs-vale-rules](https://github.com/ashishguptaiitb/koreaidocs-vale-rules) locally. Let's assume that your local path is `C:\Users\X\Documents\GitHub\koreaidocs-vale-rules`.

1. Open the `.vale.ini` file in the above directory and change the value of the `StylesPath` variable to the path of the current folder. In our example, the value of the `StylesPath` variable becomes `C:\Users\X\Documents\GitHub\koreaidocs-vale-rules`. Save and close the `.vale.ini` file.  
    ![Style path variable value in the Vale INI file.](images/vale-ini-stylepath.png)

1. Open VSCode that's updated to the latest version. Select **File** > **Preferences** > **Settings**.

1. Install the [Vale extension](https://marketplace.visualstudio.com/items?itemName=ChrisChinchilla.vale-vscode) in VSCode. Restart VSCode editor.
 
1. Search for **Vale** in the search settings field. In the search results, select **Vale** from the left sidebar.

    ![Search vale in the VSCode settings.](images/vscode-vale-settings.png)

1. Select the **Vale: Do Not Show Warning For File To Be Saved Before Linting** option.

1. Select the **Vale: Enable Spellcheck** option.

1. Change the value of the **Vale: Max Number Of Problems** option to 500.

1. In the **Vale > Vale CLI: Config** field, enter the path of the .ini settings file. In our example, the file path is `C:\Users\X\Documents\GitHub\koreaidocs-vale-rules\.vale.ini`.

1. Relaunch VSCode to load the new settings.

## Use the extension in VSCode 

1. Open an MD file and select **View** > **Problems** to view the style issues. Report generation may take some time. Update the content to resolve these issues.

   ![Same problems report](images/sample-problems.png)

1. Select each issue and update the content to resolve it. Hover the pointer over the issue to view the option to fix the problem.

   ![Various options to resolve the issue.](images/options-to-resolve.png)

1. Optionally, if you choose **Quick Fix**, it provides an AI-generated explanation of the problem, fixes the problem, and then prompts you to accept the updates. Choose **Accept** if you approve of the fix.

   ![Option to accept the automatic fix.](images/accept-fix.png)

## Troubleshoot Vale usage and config

* If you see E100 error in VSCode in the lower-right corner, it indicates that VSCode Vale extension is not able to find the .ini settings file.
  * Make sure in the settings that you provide the path to the .ini file and not the folder.

* If you see fatal error when cloning the repo in GitHub desktop client, it indicates either a permissions issue or an incorrect path.
  * Make sure that you are cloning the repo in a folder where you have read-write permissions. For example, don't clone directly into C:\ but use a folder inside `C:\Users\X\*`, for example, the `Documents` folder or the 'Desktop' folder.
  * Make sure that you don't add any special characters in the URL or the local folder. Also, make sure that you don't copy an extra space in the URL of the GitHub repo.

