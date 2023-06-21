# Global Script Setup Instructions

### Step 1

Ensure full Python [setup](https://github.com/celerygemini/resources/blob/main/python_setup.md) has been completed **including optional steps 8 and 9**.

### Step 2

Place the script/python file outside a project directory (e.g. User/Library/).

### Step 3

Add the following to the `.zprofile` file:

```
alias <run_command>="python <path_to_script>"
```

### Step 4

The script/file can now be executed in a (global) terminal by running the specified `<run_command>`.