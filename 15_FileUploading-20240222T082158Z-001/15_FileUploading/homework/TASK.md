# Урок 15: "Загрузка файлов в Symfony" - Домашняя работа

## Правильная работа над проектом

Задание должно быть выполнено на отдельной ветке. После выполнения задания запуште эту ветку и создайте Merge Request. В рамках этого Merge Request будет осуществляться проверка домашней работы. Как только все замечания будут устранены - вы сольете его в ветку master.

## Доработка проекта

### Загрузка файлов
Реализуйте загрузку файлов для статей на странице создания и редактирования статьи. Поле должно располагаться самым первым и подпись к нему должна быть: *Изображение статьи*

Изображения должны помещаться в директорию `/public/uploads/articles`

Загрузка должна осуществляться с помощью отдельного сервиса `App\Service\FileUploader`

Доработайте фикстуры, для генерации корректных изображений.

#### Валидация загружаемых файлов

- Это должны быть изображения
- Объема не более 2 Мб
- Размера не менее, чем 480х300
- Это должны быть горизонтальные изображения

Если статья еще не создана, то изображение обязательно для заполнения. 

#### Вывод изображений
Подключите и настройте бандл: `liip/imagine-bundle`

Реализуйте вывод превью изображений, создавайте изображения размера 480х300 для списка статей и формы редактирования статьи.

Создавайте изображения размера 750x500 для вывода на детальной странице статьи.

#### Удаление изображений
Реализуйте удаление изображений, при загрузке нового изображения к статье. 
 
## *Задание со звездочкой
#### Компонент flysystem
Подключите бандл: `oneup/flysystem-bundle` И переделайте работу с изображениями статьи на использование этого бандла.