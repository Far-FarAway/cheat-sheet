# Шпаргалка по командам Git и командной строке


## Навигация по директориям/папкам


Команда _cd_ позволяет перемещаться в любую точку диска


Основные символы перемещения:


* ~ - указывает на домашнюю директорию. То есть папку /users/username
* / - указывает ан корневую директорию. То есть на сам диск(на windows нужно указать какой именно диск)
* . - указывает на текущую директорию 
* .. - указывает на родительскую директорию. То есть	на ту, что на уровень выше текущей 


Таким образом _cd_ можно использовать с этими символами, чтобы перемещаться в указанные директории, а также самостоятельно указывать директории


Например, чтобы переместиться в предыдущую директорию _cd .._


Если на две назад _cd ../.._ или _cd ..._


Или перейти из домашней директории на рабочий стол _cd Desktop_


А также сразу в более удаленные папки _cd Desktop/movies_


Чтобы узнать, в какие директории можно переместиться при использовании команды _cd_, можно нажать _tab_ и ниже будет выведен список директорий, в которые можно переместиться 


Так же, чтобы узнать о содержимом папки существует команда _ls_, которую можно использовать с оператором -a и в данном случае будет выведено содержимое папки вместе со скрытыми файлами, названия которых начинаются с точки(например .git)


И последняя команда, это _pwd_, которая показывает полный путь к текущей директории 


## Работа с файлами и директориями 


Для создания текстовых файлов используется команда _touch имяФайла.txt_ 


Для создания директории используется команда _mkdir имяДиректории_


При создании что файлов, что директорий можно указать путь до нужной директории 


Например _mkdir Desktop/movies/имяДиректории_ и _touch Desktop/movies/имяФайла.txt_


Чтение файлов происходит путем вызова команды _cat имяФайла.txt_ (также можно указать путь к файлу, чтобы не переходить в директорию, а потом читать файл)


Удаление происходит тремя командами:


* _rm имяФайда.txt_ - для удаления файлов 
* _rmdir имяДиректории_ - для удаления пустых директорий
* _rm -r имяДиректории_ - для удаления директорий, содержащих что либо


## Приемы для удобства 


Для использования предыдущих команд можно использовать стрелки вверх и вниз 


Чтобы не писать каждую команду в новую строку можно использовать два амперсанда(&&) между командами

И уже затронутая клавиша _tab_, которая дописывает названия директорий и файлов, может показать папки, в которые можно перейти и возможные варианты названия файлов и команд 


## Команды git


Инициализация репозитория происходит через команду _git init_, которая создаст репозиторий в текущей директории 


Команда _git status_ показывает статус репозитория 


Команда _git add имяФайла_ добавляет/выделяет файл для фиксации/коммита(commit)


Команда _git add -all_ добавляет/выделяет весь репозитория


Команда _git add ._ добавляет/выделяет всю директорию


Команда _git commit -m "Текст"_ создает коммит с пользовательским сообщением


Команда _git log_ отображает историю коммитов


Команда _git remote add origin ssh-ключ_ связывает удаленный и локальный репозитории


Команда _git remote -v_ показывает связь между удаленным и локальным репозиторием 


Команда _git push_ отправляет коммиты на удаленный репозиторий 


Команда _git clone ссылкаНаРепозиторий_ клонируют репозитория с GitHub'а, важно то, что в таком случае изменения будут отображаться и в оригинальном репозитории


## Хеширование и коммиты


Хеш коммита является уникальным идентификационным набором символов, и одновременно ссылкой на коммит по которой можно узнать всю информацию о коммите


Хеш хранит информацию о коммите, а именно:


* Автора коммита
* Дату создания 
* Содержимое файлов в репозитории на момент коммита
* Ссылку на предыдущий коммит


Git хеширует коммиты по алгоритму SHA-1 и на выходе получает строка из 40 символов, состоящих из цифр 0-9 и латинских букв A-F


Так же имеет две особенности:


* Хеш всегда будет один и тот же для одинакового набора данных
* Если набор данных будет отличаться хотя бы на один символ, то результат хеширования изменится, при чем сильно


Git хранит таблицу соответствий _хеш -> информация о коммите_