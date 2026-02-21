# Git Cheat Sheet
[← Return to Home](readMe.md)

---
## Submodules
Add
```bash
git submodule add <repo> <target_directory>
git commit
git push
```
Init Post Clone of main repo
```bash
git clone <main repo>
git submodule update --init --recursive
```
Remove
```bash
git rm path/to/submodule
git commit
```

```bash
git rm --cached path/to/submodule
rm -rf path/to/submodule
rm -rf .git/modules/path/to/submodule
git commit -m "Remove submodule"
```