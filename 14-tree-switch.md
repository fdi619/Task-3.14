[< вернутья к содержанию](./readme.md)

## Переключение веток

Для перключения между ветками, как и в созддании, существуют две команды:

- `git checkout <имя ветки>` уже устаревший, но пока повсеместно используемый.
- `git switch <имя ветки>` более современный и проще в использовании.

Посмотрим на примере как это работает:

_Для начала посмотрим список произведённых изменений через команду_ `git log`:

```
PS C:\Users\Admin\Git-learning> git log --all --pretty=oneline
3ceb2fd9475258affc13de9853a97ac4bb9152bd (second-branch) Happy.txt file
05e76bb539a63a180d4a0e0d36a5627556f54544 changes in happy.txt and new added sring
015381178b9c131553f3fdfc3140bc0265195c3f (HEAD -> main, origin/main) Revert "Changes in happy.txt file"
fbfe77e8407bafef732590e71927d79f8e635b1c Changes in happy.txt file
```

_Как мы видим указатель_ **HEAD** _находится в ветке_ **main**. _Теперь командой_ `git checkout` _переключимся на ветку_ **second-branch** :

```
PS C:\Users\Admin\Git-learning> git checkout 'second-branch'
Switched to branch 'second-branch'

PS C:\Users\Admin\Git-learning> git log --all --pretty=oneline
3ceb2fd9475258affc13de9853a97ac4bb9152bd (HEAD -> second-branch) Happy.txt file
05e76bb539a63a180d4a0e0d36a5627556f54544 changes in happy.txt and new added sring
015381178b9c131553f3fdfc3140bc0265195c3f (origin/main, main) Revert "Changes in happy.txt file"
fbfe77e8407bafef732590e71927d79f8e635b1c Changes in happy.txt file
```

_После смены ветки указатель_ **HEAD** _, как мы видим, указывает на новую ветку. Давайте попробуем вернуться на ветку_ **main** _используя команду_ `git switch`:

```
PS C:\Users\Admin\Git-learning> git switch main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

PS C:\Users\Admin\Git-learning> git log --all --pretty=oneline
3ceb2fd9475258affc13de9853a97ac4bb9152bd (second-branch) Happy.txt file
05e76bb539a63a180d4a0e0d36a5627556f54544 changes in happy.txt and new added sring
015381178b9c131553f3fdfc3140bc0265195c3f (HEAD -> main, origin/main) Revert "Changes in happy.txt file"
fbfe77e8407bafef732590e71927d79f8e635b1c Changes in happy.txt file
```

---

[< Предыдущая страница](./13-new-tree.md)...............[следующая страница >](./14-tree-switch.md)
