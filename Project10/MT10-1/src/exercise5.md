# Что такое операторы в SQL?

Операторы SQL – это символы и слова, помогающие выполнить определенные операции, например, выбрать конкретные данные из большой базы. Такая опция широко востребована у маркетологов, программистов и разработчиков, а также руководителей.

## Арифметические операторы
Арифметические операторы SQL являются самыми простыми и наиболее популярными.

| Оператор | Описание | Пример |
| :---: | :---: | :---: |
| + | Бинарный оператор сложения. | p + q = a |
| - | Бинарный оператор вычитания. | a — b = с |
| * | Бинарный оператор умножения. | a * b = с |
| / | Бинарный оператор деления. | b / a = с |
| % | Оператор деления по модулю. Результатом будет целочисленный остаток. | b % a = с |

## Операторы сравнения SQL
Операторы сравнения SQL в результате своей работы позволяют выяснить, верна или нет запрашиваемая информация. По-английски эти значения определяются как true или false.

| Оператор | Описание | Пример |
| :---: | :---: | :---: |
| = | Этот SQL оператор не арифметическое «равно», известное со школы, а сравнение на равенство. Если равенство верное, то получится результат TRUE, если нет – FALSE. | (6 = 3 + 3) результат TRUE |
| != | SQL оператор не равно или сравнение на неравенство, TRUE система выдаст, если значения будут не равны. | (7 != 13) результат TRUE |
| <> | Аналогичный предыдущему SQL оператор. TRUE мы получим в том случае, если значения будут не равны. | (5 != 11) результат TRUE |
| > | SQL оператор больше. Если левая часть (ее еще называют левый операнд) больше правой, то результат TRUE. | (7 > 2) результат TRUE |
| < | SQL оператор меньше. Принимает значение TRUE, когда правый операнд больше левого. | (10 < 2) результат FALSE |
| >= | SQL оператор больше либо равно. Выдает значение TRUE, если правая часть больше либо равна левой. | (16 >= 16) результат TRUE |
| <= | SQL оператор меньше либо равно. Значение TRUE появляется тогда, когда правая часть больше либо равна левой. | (18<=90) результат TRUE |
| !< | SQL оператор не меньше. Приобретает значение TRUE, когда правая часть не меньше левой. | (11!<5) результат FALSE |
| !> | SQL оператор не больше. Принимает значение FALSE, когда правая часть не больше левой. | (12 !> 10) результат FALSE |

## Логические операторы

| Оператор | Описание |
| :---: | :---: |
| ALL | SQL оператор ALL осуществляет вывод всех значений из таблицы. |
| AND | SQL оператор AND представляет собой получение результата при соблюдении двух поставленных условий. |
| ANY | SQL оператор ANY (любой). Осуществляет сравнение текущего задания с дополнительным запросом. |
| BETWEEN | SQL оператор BETWEEN. Для этого оператора SQL условия можно установить в определённом диапазоне. Для корректной работы нужно задать минимальное и максимальное значение. |
| EXISTS | SQL оператор EXISTS. Применяется тогда, когда нужно обозначить, интересует ли пользователя результат подзапроса. |
| IN | Простой SQL оператор IN указывает, с какими значениями нужно вывести строки. |
| LIKE | Популярный SQL оператор LIKE. Данный оператор позволяет осуществлять поиск подстроки в тексте и, если подстрока найдена, то она выводится. |
| NOT | SQL оператор отрицания NOT. Аннулирует любые условия. |
| OR | SQL оператор «ИЛИ». Дает результат в том случае, когда значение TRUE есть хотя бы в одном из операндов. |
| IS NULL | SQL оператор IS NULL позволяет проверить значение поля на NULL. |
| UNIQUE | SQL оператор UNIQUE позволяет проверить уникальность каждой строки. |


# Каких типов бывают операторы SQL, для чего каждый из них используются?

SQL-операторы делятся на группы в зависимости от задач. Есть для определения данных или доступа к ним, а также арифметические, логические и для сравнения. 

## DDL (Data Definition Language)

Представляют собой группу операторов для определения данных. Они работают с целыми таблицами. Такие операторы SQL используются в тех случаях, когда нужно внести в базу новую таблицу или, напротив, удалить старую. Они включают в себя следующие командные слова:

**CREATE** — создание нового объекта в существующей базе.

**ALTER** — изменение существующего объекта.

**DROP** — удаление объекта из базы.

**USE** - выбрать базу данных.

## DML (Data Manipulation Language)
Эти операторы языка SQL предназначены для манипуляции данными. С их помощью меняется наполнение таблиц. Они позволяют изменять значение строк, столбцов и прочих атрибутов. Такие операторы SQL, например, позволяют удалить информацию о сотруднике, который больше не работает в компании, или исправить данные действующих специалистов. Эти операторы SQL представлены следующими командными словами:

**SELECT** — позволяет выбрать данные в соответствии с необходимым условием.

**INSERT** — осуществляют добавление новых данных.

**UPDATE** — производит замену существующих данных.

**DELETE** — удаление информации.

## DCL (Data Control Language)
Это операторы SQL, предназначенные для определения доступа к данным. С их помощью можно закрыть или открыть для пользователей работу с базой. Такие операторы необходимы, чтобы ограничить кого-либо из сотрудников в доступе к информации или, наоборот, позволить работать с базой новому специалисту.

**GRANT** — предоставляет доступ к объекту.

**REVOKE** — аннулирует выданное ранее разрешение на доступ.

**DENY** — запрет, который прекращает действие разрешения.

## TCL (Transaction Control Language)
Предназначен для управления транзакциями, то есть таким сочетанием команд, которые выполняются в определённом алгоритме. Транзакция проведена успешно, если все необходимые команды выполнены пошагово. Если же в какой-либо из них произошёл сбой, то вся операция, включая предыдущие команды, отменяется. Простым и понятным примером таких операторов SQL является проведение банковских платежей.

При этом вы сначала вводите сумму, а затем подтверждаете отправку платежа кодом, который вам присылает банк. Если операция не будет подтверждена, то транзакция отменится автоматически.

**BEGIN TRANSACTION** — начало транзакции.

**COMMIT TRANSACTION** — изменение команд транзакции.

**ROLLBACK TRANSACTION** — отказ в транзакции.

**SAVE TRANSACTION** — формирование промежуточной точки сохранения внутри операции.

# Часто ли применяется SQL?

**SQL остаётся самым распространённым лингвистическим средством для взаимодействия прикладного программного обеспечения с базами данных.**

## Примеры использования:
- https://sbermegamarket.ru/ - хранение информации о товарах;
- https://ru.wikipedia.org/ - хранение статей;
- https://vk.com/ - хранение информации о пользователях;
- https://www.shutterstock.com/ - хранение информации об изображениях;
- https://www.booking.com/ - хранение информации о партнерах-отельерах;