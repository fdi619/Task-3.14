[< вернуться к содержанию](./readme.md)

## Слияние веток

После внесения изменений в созданной нами ветки, её необходимо слить с основной веткой. Для этого мы применим команду `git merge`.

Посмотрим на примере:

- _Переключимся на ветку_ **main**:

```
PS C:\Users\nadya\OneDrive\git-learning> git switch second-branch
Already on 'second-branch'
```

- _соверишим слияние двух веток командой_ `git merge`:

```
PS C:\Users\nadya\OneDrive\git-learning> git checkout main
Switched to branch 'main'

PS C:\Users\nadya\OneDrive\git-learning> git merge second-branch
Updating 34ff1d6..4b61839
Fast-forward
 .gitignore | Bin 32 -> 54 bytes
 happy.txt  | Bin 108 -> 174 bytes
 readme.md  | Bin 34 -> 74 bytes
 3 files changed, 0 insertions(+), 0 deletions(-)


```

Теперь наша ветка **main** слита с веткой **second-branch**, и все изменения в файлах сделанные в ветке перенеслись.

---

[< Предыдущая страница](./14-tree-switch.md)...............[следующая страница >](./16-git-conflict.md)
