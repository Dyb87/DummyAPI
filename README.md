# DummyAPI

Описание тестирование проекта DummyAPI
## Оглавление

## Описание проекта

https://dummyapi.io/ Это сервис для тестирования REST API, "песочница данных" для игры с реальными пользователями и почтовыми данными. Для выполнения тестирования необходим app-id, который можно получить автоматически после регистрации на сайте. В качестве тестирования взят объект **Post**.
**Базовый Url** https://dummyapi.io/data/v1/
 
### Post
---
#### GET /post (Get List)
Получение списка постов, отсортированных по дате создания
- Доступны параметры запроса пагинации
- Доступны параметры запроса создания

  **"Responce body":**
  
 "List"
  ```Javascript
  {
data: Array(Model)
total: number(total items in DB)
page: number(current page)
limit: number(number of items on page)
}
```
"User Preview"

  ```Javascript
{
id: string(autogenerated)
title: string("mr", "ms", "mrs", "miss", "dr", "")
firstName: string(length: 2-50)
lastName: string(length: 2-50)
picture: string(url)
}
```
---

#### POST /post/create (Create post)
Создание нового поста, получение информации о созданном посте
**Обязательные параметры: (owner, text)**

**"Request body":**
```Jacascript
{
text: string(length: 6-50, preview only)
image: string(url)
likes: number(init value: 0)
tags: array(string)
owner: string(User id)
}
```
  
