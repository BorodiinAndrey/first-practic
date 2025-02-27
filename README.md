# Инструкция по Git:

### Работа с **локальным** репозиторием:

1. Создать локально папку на компьютере
2. Инициализировать git репозиторий с помощью команды git init

    _если репозиторий инициализирован ошибочно, можно ввести команду rm -rf .git, находясь в папке, в которой инициализирован "ошибочный" репозиторий, и он удалиться_

3. Добавить файлы проекта в папку с проектом с помощью GUI или команды touch
4. Добавить файлы в отслеживаемые в git репозитории с помощью команды  git add --all (добавятся все файлы, которые находятся в папке) или с помощью команды git add _название файла_
5. Закомитить изменения с помощью команды git commit -m "_Ввести название коммита_"

### Работа с **удаленным** репозиторием:

1. Зарегистрироваться на сайте [GitHub](https://github.com/)
2. Создать SSH токен и добавить его в свой профиль на GitHub
3. Создать удаленный репозиторий в GitHub:
- Тап на иконку профиля
- Тап на Your Repositories
- Тап на New
- Ввести имя создаваемоего удаленного репозитория
- Тап Create Repository
4. Скопировать ссылку на удаленный репозиторий в формате SSH

### Связывание **локального** и **удаленного** репозиториев:

1. В терминале ввести команду git remote add origin _ссылка на удаленный репозиторий_
2. Проверить что репозитории связались с помощью команды git remote -v

### Отправка изменений из локального репозитория в удаленный:
1. Для отправки закомиченных изменений, необходимо в терминале ввести команду git push -u origin master

    _Данную команду надо вводить только в первый раз, далее можно исподльзовать только команду git push_