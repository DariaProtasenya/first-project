# Bетки
* Ветка — это последовательность независимых изменений.
* Благодаря веткам несколько человек могут работать над одним репозиторием и не мешать друг другу. А ещё ветки помогают декомпозировать большую и страшную задачу на маленькие и понятные.
* Разные ветки в одном проекте существуют независимо. Изменения в одной не влияют на изменения в другой.
* Основная версия проекта хранится в главной ветке `main` (или `master`).
## Команды для работы с ветками
* Команда `git checkout <название_ветки>` позволяет переключаться на другую ветку.
* С помощью команды `git branch` можно посмотреть, какие в проекте есть ветки и в какой из них вы сейчас находитесь. Команда показывает только локальные ветки – те, которые существуют на вашем локальном компьютере.
* С помощью команды `git branch <название_ветки>` можно создать ветку.
* Команда `git checkout -b <название_ветки>` создаёт ветку и сразу переключается на неё.
* С помощью команды `git branch -a` можно просматривать все доступные ветки – хранящиеся как на вашем компьютере, так и на сервере GitHub:
  * Локальные ветки будут указываться как обычно при вызове `git branch`, например, `feature/add-branch-info`.
  * Удалённые – с префиксом `remotes/origin: remotes/origin/feature/add-branch-info`.
  * Отдельно будет указана основная ветка: строка с ней будет выглядеть как `remotes/origin/HEAD -> origin/main`. Прочитать эту строку можно как «Главной веткой является main».
## Сравнение веток — git diff
* Команда `git diff` показывает изменения в «рабочей зоне», то есть в `modified`-файлах.
* `git diff HEAD main` показывает разницу между коммитом, который сделан последним, и веткой `main`.
* `git diff` может сравнивать ветки по их названиям. Например, команда `git diff main feature/my-feature` выведет разницу между основной веткой и веткой `feature/my-feature`.
* Git поддерживает суффикс навигации `~`. С его помощью можно сослаться на предыдущие коммиты. Например, если вы находитесь в ветке `main` и хотите вывести разницу между тем коммитом, который был три коммита назад, и текущим, нужно выполнить `git diff main~3 main`.