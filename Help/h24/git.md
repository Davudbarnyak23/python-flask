# GIT

---

### Ініціалізація та налаштування

- **`git init`:** Ініціалізує новий локальний репозиторій.
  - або **`git clone <repository-url>`:** Клонування віддаленого репозиторію на локальну машину.

- **`git config --global user.name "Ваше Ім'я"`:** Налаштовує глобальне ім'я користувача.
- **`git config --global user.email "ваш_email@приклад.com"`:** Налаштовує глобальну email-адресу користувача.

  - `git config --local user.email "імя"`
  - `git config --local user.name "пошта"`


### Робота з файлами

* **`git add <файл>`:** Додає зміни у файл до індексу.
* **`git add .`:** Додає всі змінені файли до індексу.


* **`git commit -m "Опис коміту"`:** Зберігає зміни з індексу в репозиторій.
* **`git status`:** Показує статус робочої директорії та індексу.

    ```bash
    git status
    ```

* **`git diff`:** Показує різницю між версіями файлів.
* **`git log`:** Показує історію комітів.
  -  `git log --oneline`: Перегляд скороченої історії комітів
* **`git reset --hard HEAD~1`:** Відкочує до попереднього коміту.


### Робота з Гілками в Git

#### Створення гілок

* **`git branch <ім'я_гілки>`:** Створює нову гілку, відгалужуючись від поточної.
* **`git checkout <ім'я_гілки>`:** Перемикається на іншу гілку.
* **`git checkout -b <ім'я_гілки>`:** Створює нову гілку та відразу перемикається на неї.

#### Перемикання між гілками
* **`git checkout <ім'я_гілки>`:** Перемикається на існуючу гілку.

#### Перегляд гілок
* **`git branch`:** Показує список локальних гілок.
* **`git branch -a`:** Показує список усіх гілок (локальних та віддалених).

#### Об'єднання гілок
* **`git merge <ім'я_гілки>`:** Об'єднує вказану гілку з поточною.
* **`git rebase <ім'я_гілки>`:** Переносить зміни з однієї гілки на іншу.

#### Видалення гілок
* **`git branch -d <ім'я_гілки>`:** Видаляє локальну гілку.

#### Робота з віддаленими гілками
* **`git fetch`:** Завантажує нові зміни з віддаленого репозиторію.
* **`git pull`:** Завантажує нові зміни з віддаленого репозиторію та об'єднує їх з локальною гілкою.
* **`git push`:** Відправляє локальні зміни на віддалений сервер.


### Робота з віддаленими репозиторіями
* **`git remote add origin <адреса>`:** Додає віддалений репозиторій (наприклад, на GitHub або GitLab) за вказаною URL.
    - origin зазвичай використовується як стандартне ім'я для головного віддаленого репозиторію, з якого ви спочатку клонували репозиторій або з яким працюєте як з основним. Проте це лише ім'я, і ви можете назвати віддалений репозиторій як завгодно.
  - _git remote add origin https://github.com/username/user-repo.git_ 
* `git remote -v`: 	Перевірити активний віддалений репозиторій
  - `git remote`: Побачити лише імена віддалених репозиторіїв без URL.
  - `git remote show <імя репозиторію>`: Переглянути детальну інформацію про віддалений репозиторій.
* `git remote set-url origin <new.git.url/here>`: Змінити віддалений репозиторій на новий


* **`git fetch <ім'я_віддаленого репозиторію>`:** Завантажує нові дані з віддаленого репозиторію.
* **`git pull <ім'я_віддаленого> <ім'я_гілки>`:** Завантажує дані з віддаленого репозиторію та об'єднує їх з локальною гілкою.
* **`git push <ім'я_віддаленого> <ім'я_гілки>`:** Відправляє локальні зміни на віддалений сервер.
  - `git push -u origin branch-name`: Відправка змін усіх гілок

* `git branch -r`: Отримайте список віддалених гілок

    - Ця команда покаже список всіх віддалених гілок, доступних у вашому репозиторії.

* `git fetch --all`: Завантажте всі віддалені гілки

  - Ця команда завантажить всі зміни з усіх віддалених гілок у ваш локальний репозиторій, але не об'єднає їх з вашими локальними гілками.


#### Локальні гілки:
Якщо ви хочете створити локальні гілки, які будуть відстежувати відповідні віддалені гілки, виконайте для кожної віддаленої гілки:

* `git checkout -b <ім'я_локальної_гілки>  origin/<ім'я_віддаленої_гілки>`
