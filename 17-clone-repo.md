[< вернуться к содержанию](./readme.md)

## Клонирование репозитория

Для командной работы необоходимы навыки работы с удалёнными репозиотриями.
Для клонирования репозитория мы используем команду `git clone`:

```
PS C:\Users\nadya\OneDrive> git clone git-learning learning-remote
Cloning into 'learning-remote'...
done.
PS C:\Users\nadya\OneDrive> cd learni*
PS C:\Users\nadya\OneDrive\learning-remote> ls


    Каталог: C:\Users\nadya\OneDrive\learning-remote


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        02.01.2025     15:34             54 .gitignore
-a----        02.01.2025     15:34             36 first-text-file.txt
-a----        02.01.2025     15:34            174 happy.txt
-a----        02.01.2025     15:34             74 readme.md
-a----        02.01.2025     15:34            126 second-text-file.txt
```

Давайте посмотрим как **GIT** видит наши репозитори:

```
PS C:\Users\nadya\OneDrive\learning-remote> git remote show origin
* remote origin
  Fetch URL: C:/Users/nadya/OneDrive/git-learning
  Push  URL: C:/Users/nadya/OneDrive/git-learning
  HEAD branch: new-branch
  Remote branches:
    main       tracked
    new-branch tracked
  Local branch configured for 'git pull':
    new-branch merges with remote new-branch
  Local ref configured for 'git push':
    new-branch pushes to new-branch (up to date)
```

Мы видим, что имя по умолчанию (_origin_) удаленного репозитория — изначальное `git-learning`. Удаленные репозитории обычно размещаются на отдельной машине, возможно, централизованном сервере. Однако, как мы видим здесь, они могут с тем же успехом указывать на репозиторий на той же машине. Нет ничего особенного в имени _origin_, однако существует традиция использовать _origin_ в качестве имени первичного централизованного репозитория (если таковой имеется).

---

[< Предыдущая страница](./16-git-conflict.md)...............[следующая страница >](./17-clone-repo.md)
