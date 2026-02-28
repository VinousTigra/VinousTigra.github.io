# Отчет по заданию "Основы Git и GitHub Desktop"

**Студент:** [Шулепова Виктория]

## 1. Цель работы
Целью работы является знакомство с системой контроля версий Git, выполнение базовых команд в командной строке Windows, а также исследование возможностей десктопного клиента **GitHub Desktop** для выполнения аналогичных операций.

## 2. Подготовка к работе
Было выполнена установка и авторизация в клиенте GitHub Desktop.

## 3. Часть 1. Выполнение команд в командной строке

В данной части были повторены основные команды Git. Был создан локальный репозиторий и выполнены базовые операции.

# Создание папки и переход в нее

C:\Users\Vika>mkdir C:\git-lab

C:\Users\Vika>cd C:\git-lab


# Инициализация репозитория

C:\git-lab>git init

Initialized empty Git repository in C:/git-lab/.git/


# Настройка имени и email пользователя (для коммитов)

C:\git-lab>git config user.name "Vika"

C:\git-lab>git config user.email "vikishul@yandex.ru"


# Создание файла через echo и проверка статуса

C:\git-lab>echo "test" > README.md

C:\git-lab>git status

On branch master
No commits yet
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md
nothing added to commit but untracked files present (use "git add" to track)


# Добавление файла в индекс 

C:\git-lab>git add README.md

C:\git-lab>git status

On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   README.md


# Создание первого коммита

C:\git-lab>git commit -m "Init: добавила README.md"

[master (root-commit) 3fae99e] Init: добавила README.md
 1 file changed, 1 insertion(+)
 create mode 100644 README.md


# Просмотр истории коммитов

C:\git-lab>git commit -m "Init: добавила README.md"

[master (root-commit) 3fae99e] Init: добавила README.md
 1 file changed, 1 insertion(+)
 create mode 100644 README.md

C:\git-lab>git log --oneline

3fae99e (HEAD -> master) Init: добавила README.md


# Создание и переход в новую ветку

C:\git-lab>git branch feature-desc

C:\git-lab>git checkout feature-desc
Switched to branch 'feature-desc'


# Внесение изменений 

C:\git-lab>echo "Это тестовый проект." >> README.md


# Коммит изменений в ветке

C:\git-lab>git add README.md

C:\git-lab>git commit -m "Добавил описание проекта"

[feature-desc 7162deb] Добавил описание проекта
 1 file changed, 1 insertion(+)


# Возврат в основную ветку

C:\git-lab>git checkout master

Switched to branch 'master'


# Слияние изменений из ветки feature-desc

C:\git-lab>git merge feature-desc

Updating 3fae99e..7162deb
Fast-forward
 README.md | 1 +
 1 file changed, 1 insertion(+)


# Просмотр финальной истории

C:\git-lab>git log --oneline --graph

* 7162deb (HEAD -> master, feature-desc) Добавил описание проекта
* 3fae99e Init: добавила README.md
