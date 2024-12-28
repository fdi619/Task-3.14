[< вернуться к содержанию](./readme.md)

## Отмена коммитов

Иногда мы понимаем что новые коммиты являются неверными, и нам нужно их отменить. Здесь мы будем рассматривать безопасный способ отмены, с помощью создания нового коммита и второй способ с помощью команды `reset`.

Давайте посмотрим на примере:

_внесём изменения в файл и закоммитим его:_

```
PS C:\Users\Admin\Git-learning> cat happy*
Happy New Year

PS C:\Users\Admin\Git-learning> add-content -path.\happy* -value "new text"

PS C:\Users\Admin\Git-learning> cat happy*
Happy New Year
new text

PS C:\Users\Admin\Git-learning> git add happy*

PS C:\Users\Admin\Git-learning> git commit
[main fbfe77e] Changes in happy.txt file
 1 file changed, 0 insertions(+), 0 deletions(-)

PS C:\Users\Admin\Git-learning> git log
commit fbfe77e8407bafef732590e71927d79f8e635b1c (HEAD)
Author: Frolov Dmitriy <fdi_619@mail.ru>
Date:   2024-12-28

    Changes in happy.txt file
```

_отменяем последний наш коммит командой_`git revert`:

```
PS C:\Users\Admin\Git-learning> git revert HEAD
[main 0153811] Revert "Changes in happy.txt file"
 1 file changed, 0 insertions(+), 0 deletions(-)

PS C:\Users\Admin\Git-learning> git log
commit 015381178b9c131553f3fdfc3140bc0265195c3f (HEAD -> main)
Author: Frolov Dmitriy <fdi_619@mail.ru>
Date:   2024-12-28

    Revert "Changes in happy.txt file"

    This reverts commit fbfe77e8407bafef732590e71927d79f8e635b1c.

commit fbfe77e8407bafef732590e71927d79f8e635b1c
Author: Frolov Dmitriy <fdi_619@mail.ru>
Date:   2024-12-28

    Changes in happy.txt file

PS C:\Users\Admin\Git-learning> cat happy*
Happy New Year
```

_Так же мы можем отменять коммит с помощью команды_ `git reset`_. Для начала присвоим тэг последнему коммиту, чтобы не потерять его, и выполним команду:_

```
PS C:\Users\Admin\Git-learning> git tag v.1
PS C:\Users\Admin\Git-learning> git log
commit 015381178b9c131553f3fdfc3140bc0265195c3f (HEAD, tag: v.1, origin/main, main)
Author: Frolov Dmitriy <fdi_619@mail.ru>
Date:   2024-12-28

    Revert "Changes in happy.txt file"

    This reverts commit fbfe77e8407bafef732590e71927d79f8e635b1c.

commit fbfe77e8407bafef732590e71927d79f8e635b1c
Author: Frolov Dmitriy <fdi_619@mail.ru>
Date:   2024-12-28

    Changes in happy.txt file

commit 4a76afef499db41b169e62f23fd8387629d06a66 (tag: version1)
Author: Frolov Dmitriy <fdi_619@mail.ru>
Date:   2024-12-25

    created with VIM

commit 6306de0116509ade8464872261676f501df0ecc5 (tag: version2)
Author: Дмитрий Фролов <163974817+fdi619@users.noreply.github.com>
Date:   2024-12-20

    created on GitHub

PS C:\Users\Admin\Git-learning> git reset --hard version2
HEAD is now at 6306de0 created on GitHub

PS C:\Users\Admin\Git-learning> git log
commit 6306de0116509ade8464872261676f501df0ecc5 (HEAD -> main, tag: version2)
Author: Дмитрий Фролов <163974817+fdi619@users.noreply.github.com>
Date:   2024-12-20

    created on GitHub
```

[< Предыдущая страница](./reset-added-file.md)...............[следующая страница >](./commit-changes.md)
