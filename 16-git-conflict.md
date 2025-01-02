[< вернуться к содержанию](./readme.md)

## Конфликты в **GIT** и их решения

Бывают рабочие моменты когда в обоих ветках была изменена одна и та же часть файла, и **GIT** не может автоматически справиться со слиянием изменений.

Давайте смоделируем конфликт и попробуем его решить:

- _вернёмся в ветку_ **main** _и внесём измения в файл_ :

```
PS C:\Users\nadya\OneDrive\git-learning> git switch main
Already on 'main'
PS C:\Users\nadya\OneDrive\git-learning> cat second*
new text file
PS C:\Users\nadya\OneDrive\git-learning> add-content -path.\second* -value "changes in main branch"
```

- _добавим новый коммит_ :

```
PS C:\Users\nadya\OneDrive\git-learning> git status
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   second-text-file.txt

no changes added to commit (use "git add" and/or "git commit -a")
PS C:\Users\nadya\OneDrive\git-learning> git add second*
PS C:\Users\nadya\OneDrive\git-learning> git commit -m "Changes in main branch"
[main 1a7c5a2] Changes in main branch
 1 file changed, 0 insertions(+), 0 deletions(-)
```

- _посмотрим как сейчас выглядят наши ветки_ :

```
PS C:\Users\nadya\OneDrive\git-learning> git log --all --graph --pretty=oneline
* 1a7c5a2fa206a13a6279fc0041fbff57e55d48f9 (HEAD -> main) Changes in main branch
*   795e9dee736f8ca78e0fb72c516994f320716c17 (new-branch) Resolved merge conflict
|\
| * e2eae14374cc51bf4ec335508c0d83892b41bf1e changes on main branch
| * 020a057661162ffe72ad6dfc34246acaa521ec9d changes in second text file
| * 90aab7e793991ec0aafc834e3586e49c15066c2a second text file on second-branch
* | 0264918b12d1016f6f264a6afb31c2e5a93d20c5 added new file
|/
* 4b6183943fc71b43ea72fce2d9dc12b7e668f3ed chsnges in readme file in second-branch
* 02e9619158edb429b26fdd5b9165396924278285 changes on .gitignore in second-branch
* 405f1c531fca5a57896f91281de6a8546869bd8d changes on second-branch
* 34ff1d6769b1b6eaaf5d5b9fb6edd48a1e9c96c9 second changes in happy.txt
* ea173f5642c922ac939a8b4fc1a0d44f12bf6232 changes in .gitignore
* 53fc6ad6284619156b2e287acb174689aab17b25 changes in happy.txt
* c16a845d353fe085827ec2e90fc15b87c2434f01 new text file
* 8e4146a8b9971fb3a50c8ebd42f6112c217cc070 initial commit
```

Последнее изменение в **main** конфликтует с некоторыми изменениями в **new-branch**.

- _давайте вернёмся в ветку_ **new-branch** _и внесём в неё изменения из ветки_ **main**:

```
PS C:\Users\nadya\OneDrive\git-learning> git switch new-branch
Switched to branch 'new-branch'
PS C:\Users\nadya\OneDrive\git-learning> git merge main
warning: Cannot merge binary files: second-text-file.txt (HEAD vs. main)
Auto-merging second-text-file.txt
CONFLICT (content): Merge conflict in second-text-file.txt
Automatic merge failed; fix conflicts and then commit the result.
PS C:\Users\nadya\OneDrive\git-learning>
```

Как мы видим возникает конфликт.

- _посмотри как его видит_ **GIT** _а затем выполним команду_ `git merge` _с опцией_ `--abort`_, которая отменяет слияние_:

```
PS C:\Users\nadya\OneDrive\git-learning> git status
On branch new-branch
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   second-text-file.txt

no changes added to commit (use "git add" and/or "git commit -a")
PS C:\Users\nadya\OneDrive\git-learning> git merge --abort
PS C:\Users\nadya\OneDrive\git-learning> git status
On branch new-branch
nothing to commit, working tree clean
```

- _решением кофликта будет внесение нужных правок в наш документ, после мы его добавляем в индексацию и коммитим_ :

```
PS C:\Users\nadya\OneDrive\git-learning> git add second*
PS C:\Users\nadya\OneDrive\git-learning> git commit -m "Resolved merge conflict"
[new-branch 0e2f460] Resolved merge conflict
PS C:\Users\nadya\OneDrive\git-learning> git status
On branch new-branch
nothing to commit, working tree clean
```

- _а теперь посмотрим как выглядит наш репозиторий_ :

```
PS C:\Users\nadya\OneDrive\git-learning> git log --all --graph --pretty=oneline
*   0e2f460ae8a3a45d0f4e0b03564bd786e052138f (HEAD -> new-branch, main) Resolved merge conflict
|\
| * aa39c1351429904ba86cbcba9cd95a147b62f08a new changes
* | cad4b4266f83ffda2536f81bfd8b653a3d5ac8b2 changes second-text-file in new branch
|/
* 1a7c5a2fa206a13a6279fc0041fbff57e55d48f9 Changes in main branch
*   795e9dee736f8ca78e0fb72c516994f320716c17 Resolved merge conflict
|\
| * e2eae14374cc51bf4ec335508c0d83892b41bf1e changes on main branch
| * 020a057661162ffe72ad6dfc34246acaa521ec9d changes in second text file
| * 90aab7e793991ec0aafc834e3586e49c15066c2a second text file on second-branch
* | 0264918b12d1016f6f264a6afb31c2e5a93d20c5 added new file
```

---

[< Предыдущая страница](./15-tree-merge.md)...............[следующая страница >](./17-clone-repo.md)
