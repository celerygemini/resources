# Package Distribution Instructions

## Package Directory Structure

Before completing the instruction steps, ensure the source code is located in a directory as follows:
```
my_project
---package_name
   ---__init__.py
   ---module_1.py
   ---module_2.py
```

The `package_name` will be the name for the package on PyPI.

## Creating PyPI Package

### Step 1

Ensure `__init__.py` file exists in the package directory.
The file can be empty, or can contain import statements for the modules:

```
from package_name import module_1
from package_name import module_2
```

And so on.

### Step 2

Ensure the dev libraries are installed with `pip`:

- **black**
- **setuptools**
- **twine**

It is convenient to use a `requirements_dev.txt` file and `pip install` in the same way as the general requirements: `pip install -r requirements_dev.txt`.

### Step 3

Create `pyproject.toml` file for **black**.
Use and update the following template:

```
[tool.black]
line-length = 80
target-version = ['py39']
include = '\.pyi?$'
exclude = '''
/(
    \.eggs
  | \.git
  | \.hg
  | \.mypy_cache
  | \.tox
  | \.venv
  | \.python_version
  | _build
  | buck-out
  | build
  | dist
)/
'''
```

Save it in the project directory.

### Step 4

In terminal, navigate to the project directory and run: 

`black .`

### Step 5

Create `setup.py` file for **setuptools**.
Use and update the following template:

```
import setuptools

with open("README.md", "r") as fh:
    long_description = fh.read()

setuptools.setup(
    name="<>",
    version="<>",
    author="<>",
    description="<>",
    long_description=long_description,
    long_description_content_type="text/markdown",
    url="<>",
    packages=setuptools.find_packages(),
    classifiers=[
        "Programming Language :: Python :: 3",
        "License :: OSI Approved :: MIT License",
        "Operating System :: OS Independent",
    ],
    python_requires="<>",
)
```

Save it in the project directory.

Note that:
- `name` should be the same as the chosen `package_name`.
- `python_requires` can use inequality expressions like `">=3.9"`.
- The above configuration will use the linked repo README for the `long_description`.

### Step 6

Ensure the latest versions of pip and setuptools are installed.
In terminal (from the project directory), run: 
```
pip install --upgrade pip
pip install --upgrade twine
pip install --upgrade setuptools
```

### Step 7

Create the required distribution files.
In terminal (from the project directory), run: 
```
python setup.py sdist
```

### Step 8

Upload to PyPI.
In terminal (from the project directory), run: 
```
twine upload dist/*
```

Note that PyPY login crdentials will be required here.