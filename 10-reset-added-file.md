[< вернуться к содержанию](./readme.md)

## Отмена проиндексированных изменений (перед коммитом)

Отмена изменнений производитья с помощью команды `git reset`.

По умолчанию эта команда не изменяет рабочую директорию, поэтому она всеё еще будет содержжать нежелательные изменения. Чтобы их удалить мы будем использовать команду `git checkout`.

Рассмотрим на примере:

_добавим изменеия в файл и проиндексируем его_:

```
PS C:\Users\git-folder> cat happy*
Happy New Year

PS C:\Users\git-folder> add-content -path.\happy* -value "new text"

PS C:\Users\git-folder> cat happy*
Happy New Year
new text

PS C:\Users\git-folder> git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   happy.txt

no changes added to commit (use "git add" and/or "git commit -a")

PS C:\Users\git-folder> git add happy*

PS C:\Users\git-folder> git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   happy.txt
```

_а теперь приозведем отмену проиндексированных изменений_:

```
PS C:\Users\git-folder> git reset HEAD happy.txt
Unstaged changes after reset:
M       happy.txt

PS C:\Users\git-folder> git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   happy.txt

no changes added to commit (use "git add" and/or "git commit -a")

PS C:\Users\git-folder> git checkout happy*
Updated 1 path from the index

PS C:\Users\git-folder> git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

---

[< Предыдущая страница](./09-break-changes.md)...............[следующая страница >](./11-commit-reset.md)
