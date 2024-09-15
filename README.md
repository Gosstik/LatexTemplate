# Template for latex projects

### Setup new project

```bash
mkdir <Project>
cd <Project>

# Create github repo
git init
# git commit --allow-empty -m "empty initial commit"
git remote add origin <repo>

git remote add template git@github.com:Gosstik/LatexTemplate.git
git remote set-url --push template DISABLE
git fetch template
git checkout template/master
# git rebase template/master
git submodule init
git submodule update
```

### Pull changes

```bash
# Option 1 (auto)
git pull --recurse-submodules

# Option 2 (after git pull)
git submodule update --init --recursive --merge
```

### Update submodules

```bash
# Option 1 (auto)
# --merge - merge current changes
# --rebase - ...
git submodule update --remote --merge Headings

# Option 4 (manual)
cd Headings
git fetch
git merge
```

### Publish submodule changes

```bash
# Set config
git config push.recurseSubmodules check

# Option 1 (push with submodules)
git push --recurse-submodules=on-demand

# Option 2 (check that submodules are pushed)
git push --recurse-submodules=check
```

### Set specific branch to track

```bash
git config -f .gitmodules submodule.Headings.branch stable
git config status.submodulesummary 1
```
