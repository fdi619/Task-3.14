[< вернутьяс к содержанию](./readme.md)

## Внесение изменений в коммиты

Иногда возникают моменты когда мы забываем внести небольшие правки в наш файл.И чтобы не создавать новый коммит, мы можем внести в него правки.

В этом нам помогает опция `--amned` у команды `git commit`.

Рассмотрим на примере:

_Добавлем в наш фыйл немного контента и коммитим его:_

```
PS C:\Users\Admin\Git-learning> cat happy*
Happy New Year

PS C:\Users\Admin\Git-learning> add-content -path.\happy* -value "Merry Christmass"

PS C:\Users\Admin\Git-learning> cat happy*
Happy New Year
Merry Christmass

PS C:\Users\Admin\Git-learning> git add .
PS C:\Users\Admin\Git-learning> git commit
[detached HEAD 38d2531] changes in happy.txt
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 help

PS C:\Users\Admin\Git-learning> git log
commit 38d2531ce8e774f5028e5a3b7f9336d6244d77bc (HEAD)
Author: Frolov Dmitriy <fdi_619@mail.ru>
Date:   2024-12-28

    changes in happy.txt
```

_Давайте опять немного изменим файл и отреадактируем коммит который уже есть_

```
PS C:\Users\Admin\Git-learning> add-content -path.\happy* -value "My dear Friend"

PS C:\Users\Admin\Git-learning> git commit --amend
[detached HEAD 05e76bb] changes in happy.txt and new added sring
 Date: Sat Dec 28 17:54:08 2024 +0300
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 help

PS C:\Users\Admin\Git-learning> git log
commit 05e76bb539a63a180d4a0e0d36a5627556f54544 (HEAD)
Author: Frolov Dmitriy <fdi_619@mail.ru>
Date:   2024-12-28

    changes in happy.txt and new added sring
```

---

[< Предыдущая страница](./commit-reset.md)...............[следующая страница >](./commit-changes.md)
