# Работа с Git

## Работа с изображениями
![image](git_mem.jpg)

## Базовые команды Git

- <span style="color:orange">git clone [url]</span> - Клонирует репозиторий по указанному URL.

- <span style="color:orange">git status</span> - Показывает статус текущего репозитория, включая неотслеживаемые файлы, изменения, готовые для коммита, и текущую ветку.

- <span style="color:orange">git add [file]</span> - Добавляет файл в индекс для следующего коммита.

- <span style="color:orange">git commit -m "[message]"</span> - Фиксирует изменения, добавленные в индекс, с указанным сообщением коммита.

- <span style="color:orange">git push [remote] [branch]</span> - Пушит коммиты в удаленный репозиторий.

- <span style="color:orange">git pull [remote] [branch]</span> - Извлекает и автоматически сливает изменения из указанной удаленной ветки в текущую ветку.

- <span style="color:orange">git log</span> - Показывает историю коммитов текущей ветки.

- <span style="color:orange">git branch</span> - Показывает список всех локальных веток.

- <span style="color:orange">git checkout [branch]</span> - Переключает HEAD на указанную ветку.

- <span style="color:orange">git branch [branch_name]</span> - Создает новую ветку.

- <span style="color:orange">git checkout -b [branch_name]</span> - Создает новую ветку и переключает HEAD на нее.

- <span style="color:orange">git merge [branch]</span> - Сливает указанную ветку в текущую ветку. Возможны конфликты, которые придется разрешать вручную.

- <span style="color:orange">git init</span> - Инициализирует новый Git репозиторий в текущей директории.

<span style="color:orange">git log --pretty=oneline --abbrev-commit</span> - вывод


### Команды работы с файловой системой:

```bash
pwd - Показывает текущую рабочую директорию.

cd .. - Переходит на один уровень вверх в директории.

cd [directory] - Изменяет текущую рабочую директорию на указанную.
```

## Игнорирование файлов в Git

Файл **.gitignore** в Git используется для указания, какие файлы или каталоги должны быть игнорированы системой контроля версий. Это может быть полезно для предотвращения отслеживания файлов, которые не должны быть включены в репозиторий, таких как временные файлы, лог-файлы, папки с данными, которые генерируются при выполнении программы, или личная информация.

Вот как вы можете использовать .gitignore:

**Создание файла .gitignore**: В корне вашего репозитория создайте файл с именем .gitignore (внимание: имя начинается с точки).

**Указание игнорируемых файлов и папок**: Внутри файла .gitignore вы можете указать отдельные файлы, которые нужно игнорировать, например debug.log, или типы файлов, используя шаблоны, например *.log (что будет соответствовать всем файлам с расширением .log). Вы также можете игнорировать целые папки, добавив их имя в файл .gitignore, например /temp.

**Комментарии**: В файле .gitignore вы можете добавить комментарии, поместив символ # перед текстом комментария.

Вот пример файла .gitignore:

```bash
# Ignore all .log files
*.log

# Ignore the temp directory
/temp/

# Ignore the file debug.log
debug.log
```

Этот файл говорит Git игнорировать все файлы .log, игнорировать каталог temp и файл debug.log.

*Имейте в виду, что .gitignore работает только для неотслеживаемых файлов. Если вы уже добавили файл в репозиторий, и затем добавили его в .gitignore, Git продолжит отслеживать изменения этого файла. Чтобы Git прекратил отслеживание файла, который теперь находится в .gitignore, вам нужно будет использовать команду git rm --cached.*


# Удаленные репозитории

## Работа с удаленными репозиториями в Git включает в себя несколько ключевых команд и шагов:

### 1. Клонирование репозитория:

Если вы хотите создать локальную копию удаленного репозитория, вы можете использовать команду git clone:

```bash
git clone <url-of-the-repository>
```

### 2. Просмотр удаленных репозиториев:

Чтобы просмотреть все удаленные репозитории, связанные с вашим локальным репозиторием, используйте команду **git remote -v.**

### 3. Добавление удаленного репозитория:

Если вы хотите добавить новый удаленный репозиторий к вашему локальному репозиторию, вы можете использовать команду **git remote add:**

```php
git remote add <remote-name> <url-of-the-repository>
```

### 4. Получение обновлений из удаленного репозитория:

Если вы хотите получить обновления из удаленного репозитория без слияния, вы можете использовать команду **git fetch:**

```php
git fetch <remote-name>
```

Если вы хотите получить обновления и сразу смерджить их с вашей текущей веткой, используйте команду **git pull:**

```bash
git pull <remote-name> <branch-name>
```
### 5. Отправка изменений в удаленный репозиторий:

Чтобы отправить ваши коммиты в удаленный репозиторий, вы можете использовать команду git push:

```bash
git push <remote-name> <branch-name>
```

### 6. Удаление ссылки на удаленный репозиторий:

Если вы хотите удалить ссылку на удаленный репозиторий, вы можете использовать команду git remote remove:

```bash
git remote remove <remote-name>
```
*Запомните, что работа с удаленными репозиториями может потребовать учетных данных для аутентификации, в зависимости от того, как настроен удаленный репозиторий. В случае использования GitHub, вы можете использовать свой логин и пароль или настроить аутентификацию по SSH.*
