# Visual Studio Code Setup

### Step 1

Download and install [VSCode](https://code.visualstudio.com).

### Step 2

Drag **VSCode** into **applications** folder.

### Step 3

Add the following line to `.zprofile`:

```
export PATH="$PATH:/Applications/Visual Studio Code.app/Contents/Resources/app/bin"
```

This will allow the opening of folders in **VSCode** from a terminal window. To do so:

```
cd project folder
code .
```

If python and the virtual environment has been set to automatic activation on opening the folder (see **Step 5** in instructions [here](https://github.com/celerygemini/resources/blob/main/project_env_setup.md)), the session in **VSCode** will open at the folder and activate the appropriate environment automatically.