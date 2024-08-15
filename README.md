# SQL
### Нормальные формы
Нормализация - это метод проектирования баз данных, который позволяет привести БД к минимальной избыточности
Она нужна для:
- Устранения аномалий (одни и те же данные в разных местах не соответствуют друг другу)
- Повышения производительности
- Повышения удобства упрадления данными

Полный порядок нормальных форм:
1) Ненормализованная форма или нулевая нормальная форма (0NF)

Перед нормализацией БД, требуется привести ее к табличному виду
так, чтобы она отвечала базовым принципам реляционной модели.
То есть строки и столбцы не должны быть пронумерованы (порядок столбцов и строк не важен)

2)  Первая нормальная форма (1NF)

Таблицы должны соответствовать принципам реляционной модели и соблюдать следующие принципы:
- В таблице не должно быть строк-дублей
- В каждой ячейке таблицы хранятся атомарные значения
- В столбце хранятся данные одного типа
- Нет списков и массивов в любом виде
       
3) Вторая нормальная форма (2NF)

Таблицы должны соответствовать следующим принципам:
- Она должна находится в 1NF
- Таблица должна иметь ключ
- Все неключевые столбцы должны зависеть от полного ключа (в случае если ключ составной)

Декомпозиция - процесс разбиения одного отношения на несколько

4) Третья нормальная форма (3NF)

Таблицы должны соответствовать следующим принципам:
- Она должна находится в 2NF
- В таблицах должны отсутствовать транзитивные зависимости

Транзитивная зависимость - когда неключевые столбцы зависят от значений других неключевых столбцов


5) Нормальная форма Бойса-Кодда (BCNF)

Таблицы должны соответствовать следующим принципам:
- Она должна находится в 3NF
- Ключевые атрибуты составного ключа не должны зависеть от неключевых столбцов

Актуальна только для таблиц с составным ключом

6) Четвертая нормальная форма (4NF)

Таблицы должны соответствовать следующим принципам:
- Она должна находится в 3NF (BCNF)
- В таблицах должны отсутствовать нетривиальные многозначные зависимости

Пример многозначной зависимости:
Есть таблица со столбцами A, B, C. B и C между собой никак не связаны, но по отдельности они зависят от A. 
Причем для каждого значения A есть множество значений B и множество значений C.

7) Пятая нормальная форма (5NF)

Отношение находится в 5NF тогда и только тогда, когда каждая нетривиальная зависимость соединения в ней определяется
потенциальным ключом этого отношения.

8) Доменно-ключевая нормальная форма (DKNF)

Требование:
- Таблица находится в 5NF
- Каждое наложенное ограничение должно являться логическим следствием ограничений доменов и ограничений ключей,
которые накладываются на эту таблицу

9) Шестая нормальная форма (6NF)

Требование:
- Таблица находится в DKNF
- Таблица находится в 6NF, когда она неприводима, то есть не может быть подвергнута декомпозиции без потерь

### Индексы

Создание индекса:

            CREATE INDEX [index_name]
            ON [table_name] ([column_name]);

В инструкции where БД сначала будет искать по индексированному полю (в не зависимости от порядка в where)

План выполнения запроса - последовательность операций для полечения результата SQL-запроса в реляционной системе СУБД

Важно помнить:
- Индексам необходимо место для хранения
- При добавлении данных в таблицу или их обновлении, сначала обновляется исходная таблица, а затем все ее индексы

Типы индексов:
- Кластеризованный
- Некластеризованный
 
Индексы можно создавать для таблиц и представлений.

Рекомендации:
- Не применять индекусы в небольших таблицах
- Не применять индексы в таблицах которые часто обновляются
- Индексы желательно применять к тем столбцам, по которым наиболее часто ведется поиск
- Стоит планировать индексы, когда в таблице минимум 10000 тысяч строк.
- Не применять индекс с теми столбцами базы данных, с которыми будут производиться частые действия
- Большое количество индексов замедляют действия связанные с вставкой, обновлением и удалением строк в таблице
базы данных, так как происходит обновление самих индексов.
- Индексы потребляют дополнительный объем памяти. Так как зранятся отдельно от таблицы

# REST
# Rabbit
# Ассинхронность
# Git
# Операционные системы
