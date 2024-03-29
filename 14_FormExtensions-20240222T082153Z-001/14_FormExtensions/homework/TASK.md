# Урок 14: "Расширение полей и кастомная валидация" - Домашняя работа

## Правильная работа над проектом

Задание должно быть выполнено на отдельной ветке. После выполнения задания запуште эту ветку и создайте Merge Request. В рамках этого Merge Request будет осуществляться проверка домашней работы. Как только все замечания будут устранены - вы сольете его в ветку master.

## Доработка проекта

### Data Transfer Object
Примените подход с созданием DTO класса, для формы регистрации, создав такой класс `UserRegistrationFormModel`

При этом необходимо сохранить всю текущую валидацию.
- `email` - Обязательное поле. Email. Уникальное, нельзя зарегистрировать пользователей с одинаковым email.
- `Пароль` - Обязательное поле. Минимум 6 символов.
- `Согласен с условиями` - Обязательное поле.

## *Задание со звездочкой
### Фильтрация регистрации ботов
Создайте новое правило валидации `RegistrationSpam` и в нем примените сервис, созданные ранее: `App\Homework\RegistrationSpamFilter`.

### Поле email с иконкой
Создайте отдельный тип поля `CustomEmailExtension`.

Сделайте так, чтобы это поле отображалось с иконкой слева от поля:
 - [шаблон](https://getbootstrap.com/docs/4.0/components/forms/#auto-sizing),
 - [создание своих полей](https://symfony.com/doc/current/form/create_form_type_extension.html),
 - [создание тем](https://symfony.com/doc/current/form/form_themes.html).

Текст на иконке должен настраиваться параметром поля `symbol`, по умолчанию - это символ `@`.