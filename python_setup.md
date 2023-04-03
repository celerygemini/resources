# Python Setup Instructions

## Python Setup

### Step 1

Install Homebrew <https://brew.sh>

### Step 2

Install **pyenv**.
In terminal:
```
brew update
brew install pyenv
```
More info: <https://github.com/pyenv/pyenv>

### Step 3

Install any version xx.xx.xx of Python.
In terminal:
```
pyenv install -l
```
Will show the available versions. To install:

```
pyenv install <xx.xx.xx>
```

### Step 4 (Optional)

List all versions of python.
In terminal:
```
pyenv versions
```

Set global version of python to whichever version:
```
pyenv global <xx.xx.xx>
```

### Step 5

Add the following:
```
eval "$(pyenv init --path)"
```
To the `.zprofile` file.

### Step 6

In terminal:
```
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init -)"' >> ~/.zshrc
```
Will add the required lines to the `.zshrc` file (and create it if it is not already there).

### Step 7

Install **pyenv-virtualenv**.
In terminal:
```
brew update
brew install pyenv-virtualenv
```
More info: <https://github.com/pyenv/pyenv-virtualenv>

### Step 8

Add the following:
```
eval "$(pyenv virtualenv-init -)"
```
To the `.zshrc` file.

## Project Setup

### Step 9

Create virtual environment.
In terminal:
```
pyenv virtualenv <xx.xx.xx> <virtual_environment_name>
```

### Step 10

Set local version in project directory.
In terminal:
```
cd <project_directory>
pyenv local <virtual_environment_name>
```
Navigating to the project directory in future should automatically activate the virtual environment. Check with `python --version`.

### Step 11

Update **pip** in virtual environment.
In terminal:
```
cd <project_directory>
pip install --upgrade pip
```

### Step 12

Install libraries using requirements.txt as normal:
```
pip install -r requirements.txt
```


