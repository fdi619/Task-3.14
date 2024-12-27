[< вернуться к содержанию](./readme.md)

## Команда `git commit`

Команда `git commit` создаёт коммит с ХЭШ (SHA1) адрессом.
При создании коммита мы обязаны его комментировать. Для этого можно воспользоваться меткой `-m`, которая делает комментарий в командной строке.

Если мы опускаем метку `-m`, то **Git** перенесет нас в редактор\* по выбору (в порядке приоритета):

- переменная среды `GIT_EDITOR`
- параметр конфигурации `core.editor`
- переменная среды `VISUAL`
- переменная среды `EDITOR`

###### \*_обычно это **VIM** редактор_

При выполнении команды `git commit` вы увидите в вашем редакторе:

```
|
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# On branch main
# Changes to be committed:
#       modified:   <file>
```

В первой строке вводим свой комментарий, затем жмем клавишу **ESC** и вводим команду `:wq` и нажимаем **Enter**. вы увидите:

```
[main <SHA1HASH>] changes in file commit-command
 1 file changed, 18 insertions(+)
```

[< Предыдущая страница](./add-command.md)...............[следующая страница >](./log-command.md)
