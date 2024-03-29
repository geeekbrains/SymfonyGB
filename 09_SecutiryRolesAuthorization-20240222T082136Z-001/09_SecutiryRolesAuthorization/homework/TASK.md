# Урок 9: "Роли, уровни доступов и безопасность" - Домашняя работа

## Правильная работа над проектом

Задание должно быть выполнено на отдельной ветке. После выполнения задания запуште эту ветку и создайте Merge Request. В рамках этого Merge Request будет осуществляться проверка домашней работы. Как только все замечания будут устранены - вы сольете его в ветку master.

## Доработка проекта

### Аватарка пользователя
Добавьте пользователю вычисляемое свойство `avatarUrl`, которое будет формировать ссылку на аватарку. С возможностью указать размер аватарки.

**По желанию вы можете использовать любой другой сервис для автоматической генерации аватарки.* 

### Роли
Заведите следующие роли на сайте `ROLE_USER`, `ROLE_ADMIN`, `ROLE_ADMIN_COMMENT`, `ROLE_ADMIN_TAG`.

Роль администратора предполагает наличие ролей управления комментариями и тегами.

#### Администратор
В фикстурах создавайте предустановленного администратора со следующим email `admin@symfony.skillbox`

### Административный раздел
Создайте главную страницу в административном разделе. Адрес страницы: `/admin`.

В качестве контента страницы, выведите заголовок и сделайте простой ненумерованный список, состоящий из ссылок на страницы управления: комментариями и тегами.

Скорректируйте ссылку на административную страницу в шапке сайта. Эта ссылка должна отображаться только для администраторов. 

### Реализуйте ограничение доступов на сайте
Только админы могут зайти в административный раздел и увидеть ссылку в меню авторизованного пользователя.

При этом глобальный админ может зайти на любую страницу, пользователь с ролью `ROLE_ADMIN_COMMENT` - может зайти в раздел управления комментариями, а пользователь ролью `ROLE_ADMIN_TAG` - может зайти на страницу упроавления тегами.

#### Имперсонализация
Включите возможность имперсонализации и выдайте доступ админам.

В режиме имперсонализации отображайте соответствующее предупреждение со ссылкой на выход из этого режима. 

#### Навигационное меню
Выводите меню пользователя, только в том случае, если он авторизован. Не забудьте вывести аватарку этого пользователя.

Кнопки **Войти**, **Регистрация**, должны отображаться только если пользователь не авторизован. 

### Страница профиля 
Интегрируйте верстку страницы профиля пользователя. Адрес страницы: `/account`.

Скорректируйте ссылку на профиль в навигационном меню.

Ограничьте доступ к странице профиля, только авторизованный пользователь может зайти в свой профиль.

## *Задание со звездочкой
Создайте отдельную роль `ROLE_API` и ограничьте доступ к api маршруту `/api/v1/article_content`. Только пользователи с этой ролью могут посещать эту страницу.

При этом, если на страницу зашел авторизованный пользователь с другой ролью - добавьте в лог запись уровня "предупреждение" (`warning`), об этом пользователе. Для этого создайте отдельный логгер и назовите его apiLogger. Для dev окружения установить запись этого лога в файл `api.log`.

Создайте предустановленного пользователя с ролью `ROLE_API`, email: `api@symfony.skillbox` 