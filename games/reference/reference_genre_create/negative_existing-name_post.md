POST negative existing name
===

Предварительные условия
--

1. [Информация по авторизации](https://github.com/victoretc/GSPOTtestingdocumentation/blob/main/games/Authorization_data.md).
2. В базе данных есть жанр с именем "Приключения".
3. Тестовые данные:

name = "Приключения"

id - не меняем.

Действия в Postman
--
1. Создать запрос
- метод - POST
- URL - games.alpha.g-spot.website/api/v1/reference/genre/

2. Вкладка Authorization
ввести данные по авторизации - см. информацию по авторизации в предварительных условиях.

3. Вкладка Body
- выбрать тип raw
- выбрать формат JSON
- тело запроса:

```json
{
  "name": "Приключения",
  "id": "<integer>"
}
```

4. Отправить запрос

Ожидаемый результат
--

1. Status ответа: 400 Bad Request.
2. Вернулся ответ:

```
{
    "name": [
        "genre с таким Genre уже существует."
    ]
}
```

Автор: Анастасия

Прохождение тест-кейса:
----------------

|**Дата**|**Время**|**Результат**|**Имя**|**Баг № Trello**|
| :-: | :-: | :-: | :-: | :-: |
|27.06.2023|19:15|Passed|negative_existing-name_post|-|