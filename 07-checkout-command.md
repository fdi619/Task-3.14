[< вернуться к содержанию](./readme.md)

## Команда `git checkout`

Команда `git checkout` универсальна - она позволяет обновлять вашу рабочую директорию до любого предыдущего момента, переключать ветки, сбрасывать код и так далее.

Для корректной работы в качестве аргумента нужно будет указать ХЭШ коммита (`git checkout <HASH>`):

```
Note: switching to 'HASH'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at <HASH> (commit comment)
```

Чтобы вернуться к последней версии нашего кода, нам нужно переключиться на ветку по умолчанию, **main**. Для переключения между ветками можно воспользоваться командой `git switch`.

---

[< Предыдущая страница](./06-log-command.md)...............[следующая страница >](./08-tag-command.md)
