# Django-Commands
List of Django commands
1. First install Python in your machine and add path to your environment variables
2. Next install virtual env wrapper using "pip install virtualenvwrapper-win"
3. Then create a new folder in your machine, let's say on desktop "mkdir VirtualEnv"
4. Next "cd virtualEnv"
5. Next create virtual env "mkvirtualenv env_name"
6. Now to activate your venv on windows use this "workon env_name" then press enter.
7. To activate venv on git bash use this "source ./env_name/Scripts/activate" and press enter.
8. Now install Django using "pip install django"
9. Check django is installed using "django-admin --version"
10. Now create a new folder on desktop "mkdir projects"
11. Next "cd projects" then start a django project using "django-admin startproject project_name"
12. Next "cd project_name" now create an app "python manage.py startapp app_name"
13. Now your directory will be like
14. Projects
     1. project_name
        1.1 project_name
         1.11 __pycache__ # this is pycache folder
         1.12 __init__.py
         1.13 asgi.py
         1.14 settings.py
         1.15 urls.py
         1.16 wsgi.py
     1.2 app_name
         1.21 migrations # this is migration folder"
         1.22 __init__.py
         1.23 admin.py
         1.24 apps.py
         1.25 models.py
         1.26 tests.py
         1.27 views.py
        manage.py
15. Now to start django developement server use this "python manage.py runserver"
16. Then a development server start on this link http://127.0.0.1:8000/ if you want to change the server port number then do this "python manage.py runserver 5000" here 5000 is a port number.
17. To exit the server just press ctrl+c in command line
18. If you create any models in models.py then do this first register those models in admin.py and then do migrations using this "python manage.py makemigrations" after this do migrate by isng this "python manage.py migrate"
19. Then create super user using these "python manage.py createsuperuser", then fill details like Username, Email address, Passeord, and confirm password.
20. After this again start the development server and add admin at the end of the link http://127.0.0.1:8000/admin to access admin panel and use the super user credentials to login.






















CHATGPT SOLUTIONS FOR VIRTUAL ENV 

hey i use virtualenvwrapper-win to create a virtual env and whenever i create a new venv in particular folder it does'nt create rather it create on this "C:\Users\HI\Envs"  and if i try to activate using git bash or windows powershell with this command "$ source ./envs/djangoenv/Scripts/activate" it says this "$ source ./envs/djangoenv/Scripts/activate
bash: ./envs/djangoenv/Scripts/activate: No such file or directory"
and if i try to activate on cmd it just activate but i need to use this command for activating in cmd "workon venv" and if i just open the git bash normally and try to actovate my venv with this command "$ source ./envs/djangoenv/Scripts/activate" then it will activate 
ChatGPT
It sounds like you're experiencing a few issues with virtualenvwrapper-win and activating virtual environments in different terminals. Here are some steps to help you resolve these issues:

Changing Default Directory for Virtual Environments
By default, virtualenvwrapper-win creates virtual environments in the C:\Users\<YourUsername>\Envs directory. If you want to change this directory, you need to set the WORKON_HOME environment variable.

Open System Properties (right-click on This PC -> Properties -> Advanced system settings -> Environment Variables).
Under "User variables" or "System variables," click "New..."
Enter WORKON_HOME as the variable name.
Enter your desired directory (e.g., C:\path\to\your\desired\directory) as the variable value.
Click "OK" to save and close all dialogs.
After setting WORKON_HOME, restart your terminal or command prompt.

Activating Virtual Environments
Using Git Bash
In Git Bash, you should use the source command to activate the virtual environment, but make sure you provide the correct path. If your virtual environments are in C:\Users\HI\Envs, you should navigate to that directory or provide the full path.

Example:

bash
Copy code
$ source /c/Users/HI/Envs/djangoenv/Scripts/activate
Using PowerShell
In PowerShell, you can activate the virtual environment using the Scripts\Activate.ps1 script. Make sure to set the execution policy to allow scripts to run if you haven't already.

Set Execution Policy:

powershell
Copy code
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
Activate Virtual Environment:

powershell
Copy code
.\envs\djangoenv\Scripts\Activate.ps1
Using Command Prompt
In the Command Prompt, you can activate the virtual environment with the workon command or by directly running the activate script.

Using workon:

cmd
Copy code
workon djangoenv
Using the activate script:

cmd
Copy code
C:\Users\HI\Envs\djangoenv\Scripts\activate.bat
Summary
Change the default directory for virtual environments by setting the WORKON_HOME environment variable.
Use the correct commands to activate the virtual environment in different terminals:
Git Bash: source /c/Users/HI/Envs/djangoenv/Scripts/activate
PowerShell: .\envs\djangoenv\Scripts\Activate.ps1
Command Prompt: workon djangoenv or C:\Users\HI\Envs\djangoenv\Scripts\activate.bat
If you follow these steps, you should be able to create and activate your virtual environments more easily across different terminals.

hey i got this in windows powershell 
.\envs\djangoenv\Scripts\activate.ps1 : File C:\Users\HI\envs\djangoenv\Scripts\activate.ps1 cannot be loaded because
running scripts is disabled on this system. For more information, see about_Execution_Policies at
https:/go.microsoft.com/fwlink/?LinkID=135170.
At line:1 char:2
+  .\envs\djangoenv\Scripts\activate.ps1
+  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
ChatGPT
The error you're seeing is due to PowerShell's execution policy, which restricts the running of scripts for security reasons. You can resolve this by changing the execution policy to allow the running of scripts. Here’s how you can do it:

Changing the Execution Policy
Open PowerShell as Administrator:

Right-click the Start button and select "Windows PowerShell (Admin)" or "Command Prompt (Admin)".
Set Execution Policy:
Run the following command to allow local scripts to run:

powershell
Copy code
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
This command sets the execution policy for the current user, allowing scripts that are downloaded from the internet to run if they are signed by a trusted publisher, and allowing all local scripts to run.

Verify the Change:
You can verify the current execution policy by running:

powershell
Copy code
Get-ExecutionPolicy -List
This should show RemoteSigned under Scope CurrentUser.

Activating the Virtual Environment
After setting the execution policy, you should be able to activate your virtual environment in PowerShell:

powershell
Copy code
.\envs\djangoenv\Scripts\Activate.ps1
If you still face issues, make sure the path to the activate script is correct relative to your current working directory. You can always use the full path as well:

powershell
Copy code
C:\Users\HI\envs\djangoenv\Scripts\Activate.ps1
Summary
Open PowerShell as Administrator.
Run Set-ExecutionPolicy RemoteSigned -Scope CurrentUser.
Verify the policy with Get-ExecutionPolicy -List.
Activate your virtual environment with .\envs\djangoenv\Scripts\Activate.ps1.
By following these steps, you should be able to activate your virtual environment in PowerShell without running into execution policy issues.

so basically the virtualenvwrapper-win creates the virtual env in c:/users/username/Envs directory right?
why does it so?
and also tell me the difference in this command "python -m venv myenv"
ChatGPT
Why Virtualenvwrapper-win Creates Virtual Environments in C:\Users\username\Envs
virtualenvwrapper-win is designed to simplify the management of multiple virtual environments by providing a consistent location for them. By default, it creates virtual environments in the C:\Users\<username>\Envs directory because:

Consistency and Organization: Having a single directory for all virtual environments helps in organizing and managing them easily.
Ease of Use: It simplifies the commands for activating and switching between environments. You can use commands like workon myenv without specifying the full path.
Configuration: The location is configurable. If you prefer a different directory, you can set the WORKON_HOME environment variable to your desired path.
Setting a Custom Directory for Virtualenvwrapper-win
If you want virtualenvwrapper-win to create virtual environments in a different directory, you can set the WORKON_HOME environment variable:

Open System Properties: Right-click on "This PC" -> Properties -> Advanced system settings -> Environment Variables.
Add/Update Environment Variable:
Click "New" (if WORKON_HOME doesn't exist) or "Edit" (if it does exist).
Set the variable name to WORKON_HOME.
Set the variable value to your desired directory path (e.g., D:\VirtualEnvs).
Restart your terminal or command prompt to apply the changes.
Difference Between virtualenvwrapper-win and python -m venv
virtualenvwrapper-win
Purpose: virtualenvwrapper-win is a set of extensions to virtualenv for managing multiple virtual environments.
Features:
Centralized directory for all virtual environments.
Commands like mkvirtualenv, workon, rmvirtualenv, and lsvirtualenv to create, activate, remove, and list virtual environments.
Scripts that help with environment management and customization.
Usage: Typically used via commands like mkvirtualenv myenv, workon myenv.
python -m venv
Purpose: venv is a module that comes with Python (since Python 3.3) and provides support for creating lightweight, isolated Python environments.
Features:
Creates a self-contained directory tree that contains a Python installation for a particular version of Python, plus a number of additional packages.
Basic environment management without additional tools.
Usage: Directly using Python’s standard library module:
bash
Copy code
python -m venv myenv
Comparison
Installation:

venv is included with Python and does not require additional installation.
virtualenvwrapper-win requires installation via pip:
bash
Copy code
pip install virtualenvwrapper-win
Management:

venv provides basic environment creation and activation.
virtualenvwrapper-win provides additional tools and commands to simplify managing multiple environments.
Activation:

venv activation:
bash
Copy code
myenv\Scripts\activate  # Windows
source myenv/bin/activate  # Unix-based systems
virtualenvwrapper-win activation:
bash
Copy code
workon myenv
Summary
virtualenvwrapper-win is a tool for managing multiple virtual environments with added convenience and organizational features, creating them by default in C:\Users\username\Envs.
python -m venv is a built-in module for creating basic, isolated Python environments without additional dependencies.
By understanding these tools, you can choose the one that best fits your workflow and preferences for managing virtual environments.

so since i'm using virtualenvwrapper-win for my virtual env so pls tell me how to activate my env in cmd, git bash, and powershell and as my envs is in this folder c:/users/username/envs 
ChatGPT
To activate your virtual environment created using virtualenvwrapper-win in different terminals (Command Prompt, Git Bash, and PowerShell), you can follow these steps:

Command Prompt
In Command Prompt, you use the workon command provided by virtualenvwrapper-win:

Activate Environment:
cmd
Copy code
workon myenv
This will activate the virtual environment named myenv located in C:\Users\username\Envs.
Git Bash
In Git Bash, you can activate the virtual environment using the source command:

Activate Environment:
bash
Copy code
source /c/Users/username/Envs/myenv/Scripts/activate
Note that Git Bash uses Unix-style paths, so C:\Users\username\Envs becomes /c/Users/username/Envs.
PowerShell
In PowerShell, you need to run the Activate.ps1 script to activate the virtual environment. Make sure your execution policy allows running scripts:

Set Execution Policy (if not already set):
Open PowerShell as Administrator and run:

powershell
Copy code
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
Activate Environment:

powershell
Copy code
.\Envs\myenv\Scripts\Activate.ps1
Ensure you are in the directory where the Envs folder resides, or provide the full path:

powershell
Copy code
C:\Users\username\Envs\myenv\Scripts\Activate.ps1
Summary
Command Prompt:

cmd
Copy code
workon myenv
Git Bash:

bash
Copy code
source /c/Users/username/Envs/myenv/Scripts/activate
PowerShell:

powershell
Copy code
.\Envs\myenv\Scripts\Activate.ps1
With these commands, you should be able to activate your virtual environment in each of these terminals without issues.
