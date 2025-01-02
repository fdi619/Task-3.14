[< вернутья к содержанию](./readme.md)

## Синхронизация репозиоториев

Для наглядности давайте внесём небольшие изменения в оригинальном репозитории:

```
PS C:\Users\nadya\OneDrive\learning-remote> cd ../git*

PS C:\Users\nadya\OneDrive\git-learning> add-content -path.\secon* -value "origin change"

PS C:\Users\nadya\OneDrive\git-learning> git add secon*
PS C:\Users\nadya\OneDrive\git-learning> git commit -m "changes in second file"
[new-branch 2a26b66] changes in second file
 1 file changed, 0 insertions(+), 0 deletions(-)
```

Теперь в оригинальном репозитории есть более поздние изменения, которых нет в клонированной версии. Далее мы подтянем и сольем эти изменения в клонированный репозиторий.

```
PS C:\Users\nadya\OneDrive\git-learning> cd ../learn*

PS C:\Users\nadya\OneDrive\learning-remote> git fetch
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 294 bytes | 18.00 KiB/s, done.
From C:/Users/nadya/OneDrive/git-learning
   0e2f460..2a26b66  new-branch -> origin/new-branch

PS C:\Users\nadya\OneDrive\learning-remote> git log --all --pretty=oneline
2a26b66c7f2d292453e4d7e25bbc3117fb487a4f (origin/new-branch, origin/HEAD) changes in second file
0e2f460ae8a3a45d0f4e0b03564bd786e052138f (HEAD -> new-branch, origin/main) Resolved merge conflict
aa39c1351429904ba86cbcba9cd95a147b62f08a new changes
cad4b4266f83ffda2536f81bfd8b653a3d5ac8b2 changes second-text-file in new branch
1a7c5a2fa206a13a6279fc0041fbff57e55d48f9 Changes in main branch
795e9dee736f8ca78e0fb72c516994f320716c17 Resolved merge conflict
0264918b12d1016f6f264a6afb31c2e5a93d20c5 added new file
e2eae14374cc51bf4ec335508c0d83892b41bf1e changes on main branch
020a057661162ffe72ad6dfc34246acaa521ec9d changes in second text file
```

Как мы видим команда `git fetch` будет подтягивать новые коммиты из удаленного репозитория, но не будет сливать их с вашими наработками в локальных ветках.

С задачей синхронизацией справлется команда `git pull`:

```
PS C:\Users\nadya\OneDrive\learning-remote> git pull
From C:/Users/nadya/OneDrive/git-learning
   0e2f460..2a26b66  main       -> origin/main
You are not currently on a branch.
Please specify which branch you want to merge with.
See git-pull(1) for details.

    git pull <remote> <branch>

PS C:\Users\nadya\OneDrive\learning-remote> git log --all --pretty=oneline
2a26b66c7f2d292453e4d7e25bbc3117fb487a4f (HEAD, origin/new-branch, origin/main, origin/HEAD, new-branch, main) changes in second file
0e2f460ae8a3a45d0f4e0b03564bd786e052138f Resolved merge conflict
aa39c1351429904ba86cbcba9cd95a147b62f08a new changes
cad4b4266f83ffda2536f81bfd8b653a3d5ac8b2 changes second-text-file in new branch
1a7c5a2fa206a13a6279fc0041fbff57e55d48f9 Changes in main branch
795e9dee736f8ca78e0fb72c516994f320716c17 Resolved merge conflict
0264918b12d1016f6f264a6afb31c2e5a93d20c5 added new file
e2eae14374cc51bf4ec335508c0d83892b41bf1e changes on main branch
020a057661162ffe72ad6dfc34246acaa521ec9d changes in second text file
90aab7e793991ec0aafc834e3586e49c15066c2a second text file on second-branch
```

---

[< Предыдущая страница](./17-clone-repo.md)...............[следующая страница >](./19-github-repo.md)
