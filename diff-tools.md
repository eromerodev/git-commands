# Diff Tools

- `KDiff3`
- `P4Merge`
- `WinMerge`
- `VSCode`

### Set VSCode

```bash
# set name
git config --global diff.tool vscode

# set launcher
git config --global difftool.vscode.cmd "code --wait --diff $LOCAL $REMOTE"

# use
git difftool
```
