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
    
### Хэш - индификатор коммита:

1. При создании коммитов в сообщении коммита указывается хэш - индификатор коммита. Увидеть хэш - индификатор коммита можно выполнив команду git log
2. Используя команду git lot --oneline можно получить сокращенные логи коммита. В таком сообщении хэш индификатор коммита будет сокращен самостоятельно гитом до тех размеров, которые необходимы, что бы отображаелась уникальная часть хэш - индификатор коммита
3. Сокращенный хэш - индификатор коммита полезен, если в проекте тысячи коммитов. Можно быстрее найти необходимую информацию
4. При вызове команды git log отображаетя надпись HEAD. Эта надпись указывает на самые последний коммит и перезаписывается каждый раз, когда делается новый коммит. Файл HEAD хранится в .git
5. Если нужно обратится к последнему коммиту, то можно вместо хэш - индификатор коммита использовать HEAD

### Статусы коммитов:

1. Существует четыре статуса: **untracked**, **staged**, **tracked**, **modified**
- untracked - отображается у неотслеживаемых файлов. Git «видит», что такой файл существует, но не следит за изменениями в нём. У untracked-файла нет предыдущих версий, зафиксированных в коммитах или через команду git add
- staged - файлы, которые войдут в коммит, то есть добавленные с помощью команды git add
- tracked - в него попадают файлы, которые уже были зафиксированы с помощью git commit, а также файлы, которые были добавлены в staging area командой git add. То есть все файлы, в которых Git так или иначе отслеживает изменения
- modified - файлы отлича.тся от последней сохранненной версии

### Типичный жизненный цикл файла в Git:

1. Файл только что создали. Git ещё не отслеживает содержимое этого файла. Состояние: untracked.
2. Файл добавили в staging area с помощью git add. Состояние: staged (+ tracked).
3. Возможно, изменили файл ещё раз. Состояния: staged, modified (+ tracked).
    
    _Обратите внимание: staged и modified у одного файла, но у разных его версий._
    
4. Ещё раз выполнили git add. Состояние: staged (+ tracked).
5. Сделали коммит с помощью git commit. Состояние: tracked.
6. Изменили файл. Состояние: modified (+ tracked).
7. Снова добавили в staging area с помощью git add. Состояния: staged (+ tracked).
8. Сделали коммит. Состояния: tracked.
