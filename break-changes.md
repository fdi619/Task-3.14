[< вернуться к содержанию](./readme.md)

## Отмена локальных изменений (до индексации)

Как и говорилось ранее команда `git checkout` универсальна, помимо переключения на нужный комит с её помощью можно отменятьт локальные измения до индексации.

Посмотрим на примере:

_допустим у нас есть некий текстовой файл с текстом внутри:_

```=bash
PS C:\Users\folder> cat happy*
Happy New Year
```

_добавим изменения в этот файл:_

```
PS C:\Users\folder> add-content -path .\happy.txt -value "new added text"
PS C:\Users\folder> cat happy*
Happy New Year
new added text
```

_а теперь проверим статус рабочей директории_

```
PS C:\Users\folder> git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   happy.txt
```

_как мы видим, что у нас есть непроиндексированный изменный файл, и теперь при помощи команды_ `git checkout` _мы можем отменить данные изменения_

```
PS C:\Users\folder> git checkout happy.txt
Updated 1 path from the index

PS C:\Users\folder> git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

PS C:\Users\folder> cat happy*
Happy New Year
```

[< Предыдущая страница](./tag-command.md)...............[следующая страница >](./reset-added-file.md)
