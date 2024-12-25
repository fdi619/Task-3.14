[< вернуться к содержанию](./readme.md)

## Команда `git add`

Команда `git add` осуществляет добавление новых файлов в очередь для прочтения.

Команду можно вызвать как явно (`git add <file name>`), так и можно добавлять всю директорию (`git add .`)

После добавления необходимо проверить состояние репозитория командой `git status`

Обычный вывод в этом случае в командной строке:

```
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:  <file>
```
