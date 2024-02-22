# Урок 7: "Связи в Doctrine ч2 Многие ко многим" - Домашняя работа


## Правильная работа над проектом

Задание должно быть выполнено на отдельной ветке. После выполнения задания запуште эту ветку и создайте Merge Request. В рамках этого Merge Request будет осуществляться проверка домашней работы. Как только все замечания будут устранены - вы сольете его в ветку master.

## Доработка проекта

### Теги
создайте модель тегов **Tag**, со следующими полями:
- `name` - отображаемый тег
- `slug` - символьный код тега
- `createdAt` - дата создания тега
- `updatedAt` - дата изменения тега
- `deletedAt` - дата удаление тега

Для модели используйте трейт *Timestampable*, *SoftDeletable* из расширений *doctrine*.

Создайте миграцию, для генерации таблицы этой модели.

#### Связь
Создайте нужный тип связи между статьями и тегами. У статьи может быть сколько угодно тегов.

#### Фикстуры
Создайте фикстуры для тегов на сайте. Создайте не менее 50-ти тегов, с различной датой создания. А также с возможностью, что тег удалены.

К каждой статье привяжите 0 до 5 тегов.

#### Интеграция тегов
Реализуйте вывод тегов в списке статей на главной странице и на детальной странице статьи, вынеся общую часть в отдельный подключаемый twig шаблон

Не забудьте устранить проблему с N+1 запросами на главной странице

#### Управление тегами
Создайте новую страницу в административном разделе `/admin/tags`, на этой странице в виде таблицы выводите список всех тегов в порядке их добавления на сайт (сначала самые последние)

Для каждого тега выводите его название, символьный код и количество статьей, к которым привязан этот тег. Если тег удален, то рядом с его символьным кодом выводите отметку `DELETED`

Реализуйте работу фильтра на странице по символьному коду и названию тега. Также реализуйте работу переключателя "Показать удаленные"

Не забудьте устранить проблему с N+1 запросами на странице

### Постраничная навигация
Реализуйте постраничную навигацию на странице со списком комментариев и со списком тегов в административном разделе

На странице должно выводиться не более 20-ти комментариев (тегов). В случае если комментариев (тегов) больше, то должна выводиться постраничная навигация

Шаблон постраничной навигации, должен соответствовать сайту и использовать bootstrap-4 фреймворк

## *Задание со звездочкой
Веб-форму с фильтром на страницах списка комментариев и тегов административного раздела вынесите в один общий twig шаблон и подключайте его на этих страницах.

Добавьте в эту форму выпадающий список с вариантами выбора: `10`, `20`, `50`. Для постраничной навигации выводите то количество элементов на странице, которое указано в этом поле. Если ничего не указана, то по умолчанию используйте значение - `20`

Добавьте возможность фильтровать по названию статей. И выводите в виде списка названия всех статей, к которым привязан тег.