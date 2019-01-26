This text Russian language.

Данные проект поддерживает pgAdmin3 v1.22
Поддержка добавляется по мере возникновения ошибок в оригинальной версии v1.22 или если эти возможности нужны мне.
На 10.10.2018 измененены около 70 исходных файлов.

Только 32 битная версия и только для Windows
для удобства последний скомпилированный исполняемый файл будет находиться в каталоге Release.
Для работы достаточно заменить оригинальный pgAdmin3.exe.

Будет поддерживаться только оригинальная версия PostgreSQL 11.

Полная версия pgAdmin3 находиться тут https://github.com/postgres/pgadmin3.git

Что добавлено:
 - Экспорт результата запроса в Excel
 - Добавлен выбор запроса на исполнение под курсором (Auto-Select)
 - Добавлена настраиваемая автозамена (в меню Правка -> Manage autoreplace)
 - Добавлено автосохранение содержимого закладки после выполнения запроса
 - Добавлена возможность задать имя для закладки и возможность сделать закладку автозагружаемой для конкретной БД

 - Добавлена поддержка процедур
 - Добавлена поддержка секционирования (только отображение в дереве объектов)

- Удалено отображение узлов имеющих статус (Never execute) на закладке графического плана, но в табличном виде они присутствуют.

01.11.2018
 - Добавлено отображение publications.
 - Добавлено изменение фона при при не закоммиченой транзакции.
 - У Commit/Rollback измененены горячие клавиши

11.12.2018
 - Добавлен поиск в дереве по F4 выделеного текста и если объект найден то его открытие.
   Если запрос длится более 2 минут то после завершения запроса окно будет мигать.
 - При открытия функции фокус устанавливается сразу на закладку Код.

05.12.2018
 - Добавлена поддержка расширения pgpro_scheduler
   В разделе Статистика отображается информация о последнем отработавшем задании.
   Инфомация берётся из лог таблицы pg_log при условии что таблица существуе и видна, установлен флаг "Enabled ASUTP style"
   выводиться результат запроса: select log_time,detail critical,message,application_name from pg_log l where l.log_time>'$Started'::timestamp - interval '1min' and l.log_time<'$Finised' and hint='$name'
 - В выводе результатов запроса ячейки со значениям содержащие символ перевода строки \n подсвечиваются
 * В экспорте результатов запроса в Excel исправлена ошибка при сохранении интервалов
 * При обновлении схемы не блокируется интерфейс если на таблице идет долгая операция cluster
   Но при F5 на самой таблице блокировка сохраняется (это связано с блокированием функций pg_def* при получинии информации от таблицах)
09.12.2018
 - autocomplite: добавлены имена функций, и возможность подставлять имена колонок таблиц из поля FROM
 - при наборе имени функции появляется перечень параметров этой функции

28.12.2010
 - выполнен переход на wxWidgets 3.0 версия exe файла будет находиться Release_(3.0)
 - в текстовом представлении плана можно сворачивать узлы
 - построении плана с замерами в заголовках строк указывается процент времени выполнения узла (только операции узла но не вложенных узлов)
 - 

11.01.2019
 - исправлены падения приложения при открытии таблицы по нажатию F4

26.01.2019
 - исправлены падения приложения при вводе ( в окне редактирования кода)
 - ускорено открытие диалога "новая функция", "новая таблицы".


