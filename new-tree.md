[< вернуться ксодержанию](./readme.md)

## Создание ветки

Создание нового функционала всегда связано с рисками, поэтому для удобства работы необходимо создавать ветки.

В них можно работать надо новым функционалом, а затем слить в одну ветку.

Для создания в **GIT** существует два пути. Первый через команду `git checkout -b <имя ветки>`, а второй более современный - через команду `git switch -c <имя ветки>`.

Посмотрим на примере:

_создаем новую ветку с помощью команды_`git switch`:

```
PS C:\Users\Admin\Git-learning> git switch -c second-branch
Switched to a new branch 'second-branch'
```

_проверяем статус репозитория, и видим что у нас есть один файл без индексации:_

```
PS C:\Users\Admin\Git-learning> git status
On branch second-branch
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   happy.txt

no changes added to commit (use "git add" and/or "git commit -a")
PS C:\Users\Admin\Git-learning> cat happy*
Happy New Year
Merry Christmass
My dear Friend
```

_Производим индексацию и создаём коммит:_

```
PS C:\Users\Admin\Git-learning> git add .
PS C:\Users\Admin\Git-learning> git commit
[second-branch 3ceb2fd] Happy.txt file
 1 file changed, 0 insertions(+), 0 deletions(-)
```

_Проверяем список произведённых изменений и видим что_ **HEAD** _указывает на новую ветвь:_

```
PS C:\Users\Admin\Git-learning> git log
commit 3ceb2fd9475258affc13de9853a97ac4bb9152bd (HEAD -> second-branch)
Author: Frolov Dmitriy <fdi_619@mail.ru>
Date:   2024-12-28

    Happy.txt file
```

---

[< Предыдущая страница](./commit-changes.md)...............[следующая страница >](./new-tree.md)
