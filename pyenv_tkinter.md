# Configure Virtual Environments for Tkinter

If using `pyenv`/`virtualenv`, the following errors might appear when trying to use `tkinter`:

- `Python may not be configured for Tk on import tkinter`
- `import _tkinter # If this fails your Python may not be configured for Tk`
- `RuntimeError: tk.h version (8.6) doesn't match libtk.a version (8.5)`
- `ModuleNotFoundError: No module named '_tkinter'`

Note that the environment Python version may need to be reinstalled.

## Solution

### Step 1

Install `tcl-tk` with **homebrew**.
In terminal:

```
brew install tcl-tk
```

**Take note of the version installedby homebrew.**

### Step 2

Add to PATH in `.zshrc` file.
In terminal:

```
echo 'export PATH="/usr/local/opt/tcl-tk/bin:$PATH"' >> ~/.zshrc
```

### Step 3

Quit and reload terminal, and check by running: 

```
echo $PATH | grep --color=auto tcl-tk
```

`tcl-tk` should be highlighted.


### Step 4

In a new terminal, run the following commands:

```
export LDFLAGS="-L/usr/local/opt/tcl-tk/lib"
export CPPFLAGS="-I/usr/local/opt/tcl-tk/include"
export PKG_CONFIG_PATH="/usr/local/opt/tcl-tk/lib/pkgconfig"
```

### Step 5

Uninstall the Python version in question (if it has already been installed).
In terminal:

```
pyenv uninstall <version>
```

### Step 6

Set the environment variable that will be used by `python-build`. 
In terminal: 
```
export PYTHON_CONFIGURE_OPTS="--with-tcltk-includes='-I/usr/local/opt/tcl-tk/include' --with-tcltk-libs='-L/usr/local/opt/tcl-tk/lib -ltcl<tcl-tk_version_number> -ltk<tcl-tk_version_number>'"
```

Using the version number downloaded from **homebrew** (see step 1).

### Step 7

Install (or reinstall) the Python versions as usual - these should now work.
In terminal:

```
pyenv install <version>
```

### Step 8

Check by running:
```
python -m tkinter -c "tkinter._test()"
```

This should open a test app window.

