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

**Обязательные параметры: (owner, Post fields)**

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

**"Responce body":**
```Jacascript
{
id: string(autogenerated)
text: string(length: 6-1000)
image: string(url)
likes: number(init value: 0)
link: string(url, length: 6-200)
tags: array(string)
publishDate: string(autogenerated)
owner: object(User Preview)
}
```

## Майнд-карта

Данная майнд-карта представляет собой набор тестов для тестирования объекта **Post**.
Подробная проверка расписана для GET Post и Create Post.

![Alt-текст](https://s.iimg.su/s/01/TIjxBA2euK2h6dMhk1ZJlyU8uaQw8FYxQVCqxWaK.png "МК")



Можно [скачать](https://github.com/Dyb87/DummyAPI/blob/main/Dummy%20Api.xmind) Майнд-карту



  
