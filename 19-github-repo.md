[< вернуться к содержанию](./readme.md)

## Добавление удалённого репозитория на **GitHub**

В предыдущих главах мы рассматривали работы с удаленным репозиторием, который находился локально на том же компьютере. А что если у нас осуществляется командная работа? Для этого существует сервис **GitHub**.

Перед началом работы нам необходимо будет зарегистриваться на сайте [**GitHub**](https://github.com/).

Теперь необходимо создать новый репозиторий который будет называться как и наш локальный:

![github-page](./images%20and%20other/githubstart.jpg)

Для инциализации удалённого репозотория в терминале вводим команду `git remote add origin <url-repozitori>`, и командой `git push` с опцией `-u` выполняем синхронизацию:

```
PS C:\Users\nadya\OneDrive\git-learning> git remote add origin https://github.com/fdi619/git-learning.git

PS C:\Users\nadya\OneDrive\git-learning> git push -u origin main

Enumerating objects: 52, done.
Counting objects: 100% (52/52), done.
Delta compression using up to 16 threads
Compressing objects: 100% (46/46), done.
Writing objects: 100% (52/52), 4.78 KiB | 816.00 KiB/s, done.
Total 52 (delta 19), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (19/19), done.
To https://github.com/fdi619/git-learning.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
```

Теперь мы можем одной командой `git push` синхронизировать наш локальный репозиторий с удалённым.

---

[< Предыдущая страница](./18-repo-sinc.md)
