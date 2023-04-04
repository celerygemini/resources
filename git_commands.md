# Useful Git Commands

### Create repo from existing local folder

**Step 1:** Create empty repo in GitHub

**Step 2:** Initialise the repo:
```
cd <folder to initialise>
git init
```

**Step 3:** Create `README.md` file:
```
touch README.md
```

**Step 4:** Stage `README.md` file:
```
git add README.md
git commit -m "initial commit"
```

**Step 4:** Synchronise local and remote:
```
git branch -M main
git remote add origin <URL to GitHub repo>
```

**Step 5:** Push:
```
git push -u origin main
```

### Uninitialise git repo from folder
```
cd <folder to uninitialise>
rm -rf .git
```

### Unstage previously tracked files
```
git rm -r --cached .
```

### Update login credentials
```
git config --global --edit
```
To edit: `i`
To quit: `:wq`

