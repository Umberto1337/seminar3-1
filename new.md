# Введение в Git: от установки до основных команд

1. Основы Git
2. Коммиты
3. Файловая система
4. Просмотр изменений
5. Удалённые репозитории
6. Работа с ветками

## Основы Git

## Коммиты

Основы работы с Git предполагают понимание коммитов. Команда git commit откроет текстовый редактор для ввода сообщения коммита. Также эта команда принимает несколько аргументов:

* -m позволяет написать сообщение вместе с командой, не открывая редактор. Например git commit -m "Пофиксил баг";
* -a переносит все отслеживаемые файлы в область подготовленных файлов и включает их в коммит (позволяет пропустить git add перед коммитом);
* --amend заменяет последний коммит новым изменённым коммитом, что бывает полезно, если вы неправильно набрали сообщение последнего коммита или забыли включить в него какие-то файлы.

 Советы для эффективного введения в Git:
 
* Коммитьте как можно чаще.
* Одно изменение — один коммит: не помещайте все не связанные между собой изменения в один коммит, разделите их, чтобы было проще откатиться.
* Формат сообщений: заголовок должен быть в повелительном наклонении, меньше 50 символов в длину и должен логически дополнять фразу this commit will ___(this commit will fix bugs — этот коммит исправит баги). Сообщение должно пояснять, почему был сделан коммит, а сам коммит показывает, что изменилось.
* Если у вас много незначительных изменений, хорошим тоном считается делать небольшие коммиты при разработке, а при добавлении в большой репозиторий объединять их в один коммит.

## Файловая система

## Просмотр изменений

## Удалённые репозитории
Пока что мы обсуждали использование Git только на локальной машине. Однако мы можем хранить историю коммитов удалённых репозиториев, которую можно отслеживать и обновлять. git remote -v выводит список удалённых репозиториев, которые мы отслеживаем, и имена, которые мы им присвоили.

При использовании команды git clone <url репозитория> мы не только загружаем себе копию репозитория, но и неявно отслеживаем удалённый сервер, который находится по указанному адресу и которому присваивается имя origin.

Наиболее употребляемые команды:

git remote add <имя> <url> — добавляет удалённый репозиторий с заданным именем;
git remote remove <имя> — удаляет удалённый репозиторий с заданным именем;
git remote rename <старое имя> <новое имя> — переименовывает удалённый репозиторий;
git remote set-url <имя> <url> — присваивает репозиторию с именем новый адрес;
git remote show <имя> — показывает информацию о репозитории.
Следующие команды работают с удалёнными ветками:

git fetch <имя> <ветка> — получает данные из ветки заданного репозитория, но не сливает изменения;
git pull <имя> <ветка> — сливает данные из ветки заданного репозитория;
git push <имя> <ветка> — отправляет изменения в ветку заданного репозитория. Если локальная ветка уже отслеживает удалённую, то можно использовать просто git push или git pull.

## Работа с ветками