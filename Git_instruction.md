# **Инструкция по Git**

# Раздел 1. *Подготовка к работе*

## Установка утилиты

Для установки Git необходимо скачать актуальную версию утилиты с сайта https://git-scm.com.

## Проверка наличия установленного Git
В терминале выполняем команду **git --version**. Если Git установлен, появится сообщение с информацией о версии файла. Иначе будет сообщение об ошибке.

## Настройка Git
Перед началом работы необходимо "*представиться*" и указать адрес электронной почты. В противном случае, в терминале появится сообщение "Please tell me who you are". 

## Инициализация репозитория
Команда **git init** инициализирует новый репозиторий GIT и начинает отслеживание существующего каталога.  

# Раздел 2. *Основные команды*

## Сохранение изменений в файле
Команда **git add** добавляет все файлы проекта в наш будущий Commit. Если необходимо добавить один конкретный файл, то вводим команду --**git add <имя_файла>--

## Запись изменений в репозиторий
Команда **git commit** записывает изменения в репозиторий. При этом необходимо указать комментарий, добавив к команде "-m" и обязательно использовать кавычки:
![скрин](Screen1.png)
В целях экономии времени можно объеденить команды "git add" и "git commit" введя следующую комманду: **git commit -am "message"**. 

## Получение информации о истории commit
С помощью команды **git log** откроем журнал изменений. В данном журнале отображаются все внеснные commit с указанием времени и автором изменений.
![скрин2](Screen2.png)

## Перемещение между сохранениями
Для перемещения между сохранениями используем комманду **git checkout** добавляя четыре первых знака названия сохранения. Для возвращения в самое актуальное сохранение вводим команду **git checkout master**

## Сравнение с последним commit
Команда **git diff** позволяет увидеть разницу между текущим состоянием файла и последним commit.

# Раздел 3. *Ветки в Git*

## Вывод всех веток
Команда **git branch** выводит все действующие ветки. При этом, текущая ветка отмечена в терминале зелёным цветом и знаком (*).

## Создание новой ветки
С помощью команды **git checkout (namemewbranch)** можно создать новую ветку. По сути, это будет актуальная на текущий момент копия ветки master.

## Переход к ветке
Команда **git checkout + (namebranch)** позволяет осуществить переход к выбранной ветке. Важно помнить, что перед тем как переходить на другую ветку, необходимо сделать commit изменений на текущей ветке. В противном случае переход не будет выполнен.

## Слияние с текущей веткой
С помощью команды **git marge (namebranch)** мы можем произвести слияние двух веток. В ветку, в которой находимся на момент выполнения команды, будет интегрирована ветка, указанная в команде. В случае, если данные в текущей ветки отличаются от ветки с которой планируется слияние, возникнет конфликт. Программой будет предложено несколько вариантов решения данной проблемы. 

Рассмотрим их ниже: 
![тут должен быть скрин конфликт](Screen3.png)


|**Вариант решения**| **Действие**|
|---|---|
| Accept Current Change| Оставить текущее значение
| Accept Incoming Change| Изменить на предложенное значение
| Accept Both Changes| Внести оба изменения
| Compare Changes| Сравнить изменения


## Удаление ветки
Команда **git branch -d (namebranch)** удаляет указанную ветку.

## Дерево веток
Команда **git log --graph** выводит дерево изменений с визуализацией между ветками. Команда **git log --grapf --oneline --all** практически идентична предыдущей, но имеет более удобное и наглядное представление.

# Работа с удалёнными репозиториями

## GitHub
**GitHub** — это сервис компании Microsoft, который позволяет интегрироваться с
программой Git и настроить удалённую работу с вашим репозиторием. Таким образом, вы можете работать локально или хранить свой репозиторий на GitHub,
используя команды, входящие в программу Git.

## Клонирование репозитория с Github на локальный репозиторий в GIt
Ранее мы уже рассматривали способ создания репозитория с помощью команды *git init*, теперь мы научимся брать готовый репозиторий. Для этого необходимо перейти на сайт github.com и найти интересующего нас автора или репозиторий с помощью поиска. При открытии репозитория появится зеленая кнопка "Code". Нажимаем на неё и копируем ссылку во вкладке HTTPS. Далее переходим в Git и вводим в терминале команду "**git clone**" и указываем ранее скопированный адрес. После этого Git скопирует репозиторий, находящийся на сервисе GitHub, в наш локальный репозиторий. При этом, чтобы продолжить работу с данным репозиторием следует поменять местоположение с помощью команды **cd + название файла** — *change directory — поменять директорию*.

## Перемещение локального репозитория на GitHub
Созданный локальный репозиторий на Git можно отправить на удаленный репозиторий в GitHub. В первую очередь, необходимо создать на Git Hub свой аккаунт. Обратите внимание, что скачать чужой репозиторий можно и без создания
собственного аккаунта на этом сервисе. После регистрации в правом верхнем углу надо нажать плюсик, выбрать "новый репозиторий" и дать ему имя. Остальные параметры оставляем по умолчанию. Затем создаём новый репозиторий.
GitHub подсказывает, что можно сделать, чтобы начать работать с этим
репозиторием. У нас есть три варианта:
1. Можно создать новый репозиторий через терминал и начать с этим работать.
2. Уже существующий репозиторий привязать к удалённому репозиторию.
3. Импортировать код из другого репозитория.

Под каждым из этих вариантов GitHub подскажет команды, которые необходимо использовать в Git для начала работы. 
В данном случае нам необходимо переместить локальный репозиторий из Git в удаленный репозиторий на GitHub, действуем согласно инструкции под пунктом 2. Копируем команды и по очереди вводим их в терминал. Рассмотрим эти команды поподробнее:
- **git remote add origin <ссылка>** связывает наш локальный репозиторий с удалённым репозиторием. 
- **git branch -M main** - эта команда позволяет переименовать главную ветку. Как известно, ОС Windows использует название "master", тогда как в MacOS главная ветка называется "main". В случае, если работа ведется с ОС Windows, применять данную команду не нужно. 
- **git push -u origin main** "проталкивает" (выгружает) всю информацию с локального репозитория на наш связанный удалённый.

Соответственно, когда мы проведём какую-то работу в репозитории локально и вызовем команду git push, то Git протолкнёт всё, на наш удалённой репозиторий, который мы задали ранее.

## Синхронизация локального репозитория с удалённым
В случае, если мы (коллеги или другие пользователи) вносили какие-либо изменения в удалённый репозиторий, то в локальном эти действия отображаться не будут до тех пор, пока мы не "подтянем" их с помощью команды "**git pool**". Стоит отметить, что данная команда является составной. Она не только подгрузит все изменения, но и попытается смержить наши ветки. То есть указанная команда попытается произвести слияние состояния, которое было на GitHub, с состоянием, происходящим локально.

## Работа с чужими проектами
Напрямую работать с чужими репозиториями не получится, т.к. нет прав. Но в GitHub предусмотрена возможность скопировать чужой проект на свой удалённый репозиторий с помощью кнопки "**Fork**". С помощью уже знакомой нам команды "**git clone**" копируем проект на наш локальный репозиторий. Теперь мы можем вносить все наши изменения в проект, обязательно используя отдельную ветку. По итогу работы отправляем эти изменения на свой аккаунт командой **git push**. И теперь можем предложить внесенные нами изменения изначальному хозяину репозитория кнопкой **Compare & pull request**. GitHub при этом проанализирует изменения и предложит добавить описание. После этого направим pull request в изначальный аккаунт. Затем в аккаунте, копию которого мы делали, появляется новое поле. С ним будет работать уже хозяин этого аккаунта. Он посмотрит на изменения, которые мы сделали. Если
произведённые изменения его устроят, он может влить эту ветку в основной репозиторий.