# Python Setup and Virtual Environment

In MacBook, open Terminal and run `python3-- version` to check Python 3. It is unlikely that Python 2 is installed, but you can check with `python-- version`. If no Python is installed, the prompt to install Xcode tools will appear, confirming that Python 3 is not preinstalled for user access by default.

## Install a Custom Python Version in MacBook:

Apple’s Python (from Xcode tools) is fine for basic use but may be outdated or restricted for development. Developers typically install a separate Python version using:

* Homebrew: `brew install python@3.12` installs Python 3.12 (or the latest available) in `/opt/homebrew/bin` (on Apple Silicon) or `/usr/local/bin` (on Intel).

* pyenv: A tool to manage multiple Python versions, e.g., `pyenv install 3.12.4.`

* Official Installer: Download Python from `python.org` for a specific version.
  These methods give you control over updates and avoid conflicts with system tools.

* Check Python path in Windows
  
  ```shell
  C:\Users\satish.karki>where python
  C:\Users\satish.karki\AppData\Local\Programs\Python\Python313\python.exe
  C:\Users\satish.karki\AppData\Local\Microsoft\WindowsApps\python.exe
  ```

## Virtual Environments:

### In Windows

Use `venv` (built-in) or `virtualenv` (third-party) to isolate project dependencies, e.g., `python3 -m venv myenv`.

```shell
python -m ensurepip # Check if pip is installed
python -m pip install --upgrade pip #upgrade pip
```

```shell
# In your project directory, run
python -m venv venv # It creates a venv folder in your project directory

#Using bat file
venv\Scripts\activate

#Using Powershell Script
.venv\Scripts\activate 

#Output
(venv) C:\Users\satish.karki\OneDrive\Notes\python\Projects\Project1>where python

C:\Users\satish.karki\OneDrive\Notes\python\Projects\Project1\venv\Scripts\python.exe

#Export installed package to a file
pip freeze > requirements.txt
```

### git work

```shell
#In Windows
git add .
git commit -m "Inital commit"
git remote add origin https://github.com/satishkarki/pythonplayground.git
git branch -M main
git push -u origin main

echo. > .gitignore # Creates .gitignore
notepad .gitignore

git status

git add .gitignore
git commit -m "Ignore venv in .gitignore
git push origin main

#In MacBook
git pull origin main
git status
rm -rf venv #remove venv if it appears (it appeared for me becasue of OneDrive)
```

### In MacBook

```bash
which python 
/usr/bin/python3 #System Python
```

Modifying it (e.g., installing global packages with `pip`) can break system functionality. Homebrew is a popular package manager for macOS that installs Python in a separate location (e.g., `/opt/homebrew/bin` on Apple Silicon or `/usr/local/bin` on Intel), leaving the system Python intact.

```bash
brew search python # Check the latest Python version available
brew install python@3.12 #Install the 3.12 version
which python3.12

Output: /usr/local/bin/python3.12
```

Optional Step to update the path to prioritize Homebrew's Python over system Python

```bash
echo 'export PATH="/opt/homebrew/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

For Intel Macs, use `usr/local/bin` instead of `/opt/homebrew/bin`

Now lets create a virtual  environment

```bash
python3.12 -m venv venv
source venv/bin/activate #Activate venv
# output ((venv)) macbook@MacMan Project1%


pip install -r requirements.txt
pip list #to check the packages



# For Windows
py -3.12 -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```