# Git rebasing workshop at Git Merge 2020

```bash
mkdir rebasing
cd rebasing
touch index.md
echo "Git merge" > index.md
cat index.md
git init
git add index.md
git status
git commit -m "Add index file"
git checkout -b em-fix-title
git branch -l
vi index.md (capitalise M)
git status
git diff
git add .
git commit -m "Capitalise Merge"
vi index.md (heading)
git status
git diff
git add .
git commit -m "Make title a heading"
git checkout master
git branch -l
git checkout -b em-add-year
vi index.md (add 2020)
git diff
git add .
git commit -m "Include year of operation"
vi index.md (change heading)
git status
git diff
git add -p
git commit -m "Begin with a heading"
git checkout master
git br -l
git config --list |grep merge
# merge.ff=only
git merge --no-ff em-add-year
git log
git log --oneline
lol
alias lol
# lol='git log --graph --decorate --pretty=oneline --abbrev-commit'
git merge --no-ff em-fix-title (error)
git diff
git status
git reset index.md
git checkout index.md
lol
git checkout em-fix-title
git rebase -i master
git status
git diff
vi index.md
git add .
git rebase --continue
git diff
git add .
git status
git rebase --continue
lol
git checkout master
git merge --ff-only em-fix-title
lol
```

```bash
git checkout -b em-add-copy
vi index.md (add lorem ipsum dolor and newline)
git diff
git add .
git commit -m "Add copy"
vi index.md (add links: about, speakers, schedule, venue)
git diff
git add .
git commit -m "Add main navigation"
vi index.md (remove newline and add home link)
git diff
git add -p (select `s` option to add different bits)
git status
git diff --staged
git commit -m "Forgot to add link to home page"
git diff
git add .
lol (grab sha)
git commit --fixup <sha>
lol
git config --list |grep rebase
# rebase.autosquash=true
# To set this option, use:
git config --global rebase.autosquash true
# show diffs when writing the commit message
# similar to `git commit -v`
git config --list |grep verbose
# commit.verbose=true
git rebase -i --autosquash master
lol
git checkout master
git merge --ff-only em-add-copy
lol
```
