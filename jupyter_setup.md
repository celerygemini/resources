# Jupyter Setup

## Set default browser for Jupyter Notebook only

### Step 1

Install Jupyter with `pip`

### Step 2

Go into Jupyter.
In terminal:
```
cd ~/.jupyter/
```

### Step 3

Open the file `jupyter_notebook_config.py`.
If it doesn't exist, create it by running in the temrinal:
```
jupyter notebook --generate-config
```

### Step 4

Find the line in the `jupyter_notebook_config.py` file:
```
#c.NotebookApp.browser = ''
```

### Step 5

Uncomment the line and change to:
```
c.NotebookApp.browser = 'open -a /Applications/Google\ Chrome.app %s'
```
(For Chrome).

### Step 6

Save and exit.