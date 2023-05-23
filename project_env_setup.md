# Project Environment Setup Instructions

### Step 1

Ensure full Python [setup](https://github.com/celerygemini/resources/blob/main/python_setup.md) has been completed.

### Step 2

Ensure **pyenv** and **pyenv-virtualenv** are installed and up to date.

In terminal:
```
brew update
brew install pyenv
brew upgrade pyenv
brew install pyenv-virtualenv
brew upgrade pyenv-virtualenv
```

### Step 3

Choose Python version to install for environment.

In terminal:
```
pyenv install <xx.xx.xx>
```

To list available versions: `pyenv install -l`
To list previously installed versions: `pyenv versions`

### Step 4

Create virtual environment.
In terminal:
```
pyenv virtualenv <xx.xx.xx> <virtual_environment_name>
```

Using one of the installed versions.

### Step 5

Set local version in project directory.
In terminal:
```
cd <project_directory>
pyenv local <virtual_environment_name>
```
Navigating to the project directory in future should automatically activate the virtual environment. Check with `python --version`.

### Step 6

Update **pip** in virtual environment.
In terminal:
```
cd <project_directory>
pip install --upgrade pip
```

### Step 7

Install libraries using requirements.txt as normal:
```
pip install -r requirements.txt
```


