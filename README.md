LOLBOT
========

Чат-бот для ВКонтакте.
Идеально подходит как "Ассистент" в конференциях.

**ВНИМАНИЕ:**
Для работы бота необходим Python версии 2.7.x, с версией 3 бот **не работает**
Бот был написан с целью поближе изучить python, код местами может быть ужасающим.
Работоспособность проверена исключительно на ОС семейства Linux.

## Начальная настройка:
1. Вам понадобится `pip` для установки модулей к вашему Питону, так-же пакет `screen`, для запуска в отдельном окне.
2. Установить модуль vk_api: `pip install vk_api`
3. Установить модуль pytz: `pip install pytz` (Может понадобится для использования в плагинах)
4. В `settings.py` заменить `login` и `password` на логин и пароль аккаунта бота соответственно. 
5. При необходимости в `settings.py` можно указать (`vk_app_id =`) ID другого приложения вк вместо стандартного app_id из модуля vk_api. 
Значение `-1` указывает на использование app_id по умолчанию.
6. Запустить: `./start.sh` для запуска в screen с циклом перезапуска при краше. 
   Или `python lolbot.py` для запуска в основном окне (Для отладки, например).

## Смена префиксов:
По умолчанию бот отзывается на пять префиксов: `lolbot`, `лолбот`, `лб`, `файнбот`, `фб`
Сменить их можно в `lolbot.py` на строке 75

## Плагины:
* Приветствие (Плагин преветствия)
* Список плагинов (Список загруженный плагинов)
* Музыка (Список музыки из ваших рекомендаций в ВК)
* Случайное число (Случайное число в диапазоне от 1 до 6)
* Случайные сиськи (Берутся из паблика, указанного в плагине boobs.py)
* Случайные мемы (Берутся из паблика, указанного в плагине memes.py)
* Случайные картинки с Двача (Берутся из паблика, указанного в плагине 2ch.py)
* Случайные девушки (Берутся из паблика, указанного в плагине fur.py)
* Ближайшие дни рождения в группе (Берутся из паблика, указанного в плагине hday.py)
* Курс валют (Отображение основных курсов валют)
* Список команд (Список всех команд бота `! команды`)
* Шар восьмерка (Решает за вас)
* Время (Показывает текущую дату и время)
* Статистика бота (Показывает данные о счетчиках аккаунта)
* Онлайн серверов FineMine (По фану, чтобы на сайт не заходить)
* Случайные картинки из группы FineMine (Берутся из паблика, указанного в fmgroup.py)
* Случайные картинки со школьницами (Берутся из паблика, указанного в shk.py)
* Отправка смайла (Отправляется "Луна", moon.py)
* Отправка видео (Отправляется "Nope.avi", nope.py)

## Примечание:
Для того, чтобы узнать ID пользователя или паблика, используйте https://vk.com/linkapp

## Создание плагинов:
В папке plugins лежит пример плагина под именем example.py, отвечающий строкой на команду `лб примерплагина`
Так-же, там есть и другие плагины, в коде кодорых можно покопать, для просмотра реализации их функционала.

Каждый плагин обязательно должен иметь три метода:
1. Конструктор (ему передается экземпляр vk_api)
2. `getkeys`, возвращающий слова-триггеры для вызова плагина
3. `call`, вызываемый по слову-триггеру из getkeys

Плагины размещаются в папке `plugins`. В случае наличия одинакового триггера в двух плагинах, будет использоваться последний загруженный.
Плагины могут работать со всеми методами API вконтакте.

## Лицензия:
Код распространяется под лицензией [WTFPL](https://ru.wikipedia.org/wiki/WTFPL) (Do What The Fuck You Want To Public License) версии 2
