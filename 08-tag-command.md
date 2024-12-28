[< вернуться к содержанию](./readme.md)

## Команда `git tag`

Работа с ХЭШами в **GIT** иногда очень сложна и запутана, для облегчения работы существует команда `git tag`. Она создаёт именнованный тэг к коммиту на который указывает _HEAD_.

Для выполнения команды в адресной строке вводим `git tag <tag name>`

После создания тэга появляется возможность быстрого переключени _HEAD_ с помощью команды `git checkout <tag name>^`

Можно создать тэги ко всем комитам, тем самым упращая перемещение между ними с помощью команды `git checkout <tag name>`

Пример

_Производим вызов списка изменений_

```
git log
commit 4a76afef499db41b169e62f23fd8387629d06a66 (HEAD -> main, origin/main)
Author: Frolov Dmitriy <my_e_mail@examle.com>
Date:   2024-12-25
```

_присваиваем последнему коммиту тэг_ **version1**

```
git tag version1
git log
commit 4a76afef499db41b169e62f23fd8387629d06a66 (HEAD -> main, tag: version1, origin/main)
Author: Frolov Dmitriy <my_e_mail@examle.com>
Date:   2024-12-25
```

_с помощью команды_ `git checkout <tag name>^` _переключаемся на предыдущий коммит_

```
git checkout version1^
Note: switching to 'version1^'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.
```

_теперь присваиваем тэг_ **version2** _данному коммиту_

```
git tag version2
commit 6306de0116509ade8464872261676f501df0ecc5 (HEAD, tag: version2)
Author: Дмитрий Фролов <my_e_mail@examle.com>
Date:   2024-12-20
```

_после всех манипуляций мы можем перемещать наш **HEAD** между тэгами_

```
git checkout version1
Previous HEAD position was 6306de0
HEAD is now at 4a76afe
```

---

[< Предыдущая страница](./07-checkout-command.md)...............[следующая страница >](./09-break-changes.md)
