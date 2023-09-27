# Тестирование API с Postman

## Activities: получение списка активностей

GET {{activities}}

URL https://fakerestapi.azurewebsites.net/api/v1/Activities/

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно. 
Тело ответа в формате JSON возвращается от сервера. 
Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```

Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 12:17:21 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
[
{
  "id": 1,
  "title": "Activity 1",
  "dueDate": "2023-06-10T12:55:12.550936+00:00",
  "completed": false
},
...
{
   "id": 30,
   "title": "Activity 30",
   "dueDate": "2023-06-10T12:55:12.5509481+00:00",
   "completed": true
 }
]
```

## Activities: создание новой активности (базовый позитивный сценарий)

POST {{activities}}

URL https://fakerestapi.azurewebsites.net/api/v1/Activities/

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно. 
Тело ответа в формате JSON возвращается от сервера. 
Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Content-Type: application/json
  Content-Length: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: 
```
{
 "id": 125,
 "title": "MyTitle",
 "dueDate": "2023-06-20T19:47:09.706Z",
 "completed": true
}
```

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 12:24:54 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
{
    "id": 125,
    "title": "MyTitle",
    "dueDate": "2023-06-20T19:47:09.706Z",
    "completed": true
}
```

## Activities: создание новой активности (базовый негативный сценарий)

POST {{activities}}

URL https://fakerestapi.azurewebsites.net/api/v1/Activities/

Ожидаемый результат: HTTP статус: код ответа 400.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Content-Type: application/json
  Content-Length: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: 
```
{
 "id": ,
 "title": "MyTitle",
 "dueDate": "2023-06-20T19:47:09.706Z",
 "completed": true
}
```

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 12:24:54 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-d338d17ca54a7749974e808012cfb8c2-f940512756fe3941-00",
    "errors": {
        "$.id": [
            "',' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 7."
        ]
    }
}
```

## Activities: создание новой активности (дополнительный негативный сценарий)

POST {{activities}}

URL https://fakerestapi.azurewebsites.net/api/v1/Activities/

Ожидаемый результат: HTTP статус: код ответа 400.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Content-Type: application/json
  Content-Length: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: 
```
{
 "id": -1,
 "title": "MyTitle",
 "dueDate": "2023-06-20T19:47:09.706Z",
 "completed": true
}
```

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 13:04:15 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
{
    "id": -1,
    "title": "MyTitle",
    "dueDate": "2023-06-20T19:47:09.706Z",
    "completed": true
}
```

## Activities: получение 1 активности (базовый позитивный сценарий)

GET {{activities}}{{positive_id}}

URL https://fakerestapi.azurewebsites.net/api/v1/Activities/{{positive_id}}

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно. 
Тело ответа в формате JSON возвращается от сервера. 
Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 13:17:23 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
{
    "id": 1,
    "title": "Activity 1",
    "dueDate": "2023-06-22T14:17:23.5553682+00:00",
    "completed": false
}
```

## Activities: получение 1 активности (базовый негативный сценарий)

GET {{activities}}{{negative_minus}}

URL https://fakerestapi.azurewebsites.net/api/v1/Activities/{{negative_minus}}

Ожидаемый результат: HTTP статус: код ответа 404 Error: Not Found.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 13:04:15 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
    "title": "Not Found",
    "status": 404,
    "traceId": "00-cdb05a93c24ce54fa7eddf0b2a2d855a-403b5ae262b8a846-00"
}
```

## Activities: редактирование 1 активности (базовый позитивный сценарий)

PUT {{activities}}{{positive_id}}

URL https://fakerestapi.azurewebsites.net/api/v1/Activities/{{positive_id}}

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно. 
Тело ответа в формате JSON возвращается от сервера. 
Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Content-Type: application/json
  Content-Length: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса:
```
{
 "id": {{positive_id}},
 "title": "string",
 "dueDate": "2023-06-20T20:13:50.614Z",
 "completed": false
}
```
Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 14:11:34 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
{
    "id": 1,
    "title": "string",
    "dueDate": "2023-06-20T20:13:50.614Z",
    "completed": false
}
```

## Activities: редактирование 1 активности (базовый негативный сценарий)

PUT {{activities}}/{{negative_null}}/

URL https://fakerestapi.azurewebsites.net/api/v1/Activities/{{negative_null}}

Ожидаемый результат: HTTP статус: 400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Content-Type: application/json
  Content-Length: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса:
```
{
 "id": {{negative_null}},
 "title": "string",
 "dueDate": "2023-06-20T20:13:50.614Z",
 "completed": false
}
```
Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 14:14:23 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
{
    "id": 0,
    "title": "string",
    "dueDate": "2023-06-20T20:13:50.614Z",
    "completed": false
}
```

## Activities: редактирование 1 активности (дополнительный негативный сценарий)

PUT {{activities}}/{{negative_minus}}/

URL https://fakerestapi.azurewebsites.net/api/v1/Activities/{{negative_minus}}

Ожидаемый результат: HTTP статус: 400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Content-Type: application/json
  Content-Length: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса:
```
{
 "id": {{negative_minus}},
 "title": "string",
 "dueDate": "2023-06-20T20:13:50.614Z",
 "completed": false
}
```
Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 14:23:13 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
{
    "id": -1,
    "title": "string",
    "dueDate": "2023-06-20T20:13:50.614Z",
    "completed": false
}
```

## Activities: удаление активности (базовый позитивный сценарий)

DELETE {{activities}}{{positive_id}}

URL https://fakerestapi.azurewebsites.net/api/v1/Activities/{{positive_id}}

Ожидаемый результат: HTTP статус: код ответа 200 OK.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 14:29:20 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: отсутствует

## Activities: удаление активности (базовый негативный сценарий)

DELETE {{activities}}/{{negative_null}}/

URL https://fakerestapi.azurewebsites.net/api/v1/Activities/{{negative_null}}/

Ожидаемый результат: HTTP статус: 400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 14:31:39 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: отсутствует

## Activities: удаление активности (дополнительный негативный сценарий)

DELETE {{activities}}//{{negative_minus}}/

URL https://fakerestapi.azurewebsites.net/api/v1/Activities/{{negative_minus}}/

Ожидаемый результат: HTTP статус: 400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 16:27:23 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: отсутствует

## Books: получение списка активностей

GET {{Books}}

URL https://fakerestapi.azurewebsites.net/api/v1/Books/

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно. 
Тело ответа в формате JSON возвращается от сервера. 
Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```

Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 16:34:11 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
[
    {
        "id": 1,
        "title": "Book 1",
        "description": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",
        "pageCount": 100,
        "excerpt": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",
        "publishDate": "2023-06-21T16:34:12.1760425+00:00"
    },
...
    {
        "id": 200,
        "title": "Book 200",
        "description": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",
        "pageCount": 20000,
        "excerpt": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",
        "publishDate": "2022-12-04T16:34:12.184002+00:00"
    }
]
```

## Books: создание новой активности (базовый позитивный сценарий)

POST {{Books}}

URL https://fakerestapi.azurewebsites.net/api/v1/Books/

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно. 
Тело ответа в формате JSON возвращается от сервера. 
Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Content-Type: application/json
  Content-Length: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: 
```
{
 "id": 120,
 "title": "string",
 "description": "string",
 "pageCount": 0,
 "excerpt": "string",
 "publishDate": "2023-06-20T20:54:19.763Z"
}
```

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 16:35:11 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
{
 "id": ,
 "title": "string",
 "description": "string",
 "pageCount": 0,
 "excerpt": "string",
 "publishDate": "2023-06-20T20:54:19.763Z"
}
```

## Books: создание новой активности (базовый негативный сценарий)

POST {{Books}}

URL https://fakerestapi.azurewebsites.net/api/v1/Books/

Ожидаемый результат: HTTP статус: код ответа 400.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Content-Type: application/json
  Content-Length: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: 
```
{
 "id": ,
 "title": "string",
 "description": "string",
 "pageCount": 0,
 "excerpt": "string",
 "publishDate": "2023-06-20T20:54:19.763Z"
}
```

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 16:38:05 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-0670e4255539ac42a5c26db215e9b424-a98317ce81859b4b-00",
    "errors": {
        "$.id": [
            "',' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 7."
        ]
    }
}
```

## Books: создание новой активности (дополнительный негативный сценарий)

POST {{Books}}

URL https://fakerestapi.azurewebsites.net/api/v1/Books/

Ожидаемый результат: HTTP статус: код ответа 400.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Content-Type: application/json
  Content-Length: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: 
```
{
 "id": {{negative_text}},
 "title": "MyTitle",
 "dueDate": "2023-06-20T19:47:09.706Z",
 "completed": true
}
```

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 16:39:11 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-ec1e09ef2d60a34e9d9a0064a92fa76f-c628dc98ae1a9c4c-00",
    "errors": {
        "$.id": [
            "'test,\r\n \"title\": \"MyTitle\",\r\n \"dueDate\": \"2023-06-20T19:47:09.706Z\",\r\n \"completed\": true\r\n}' is an invalid JSON literal. Expected the literal 'true'. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."
        ]
    }
}
```

## Books: получение 1 активности (базовый позитивный сценарий)

GET {{Books}}{{positive_id}}

URL https://fakerestapi.azurewebsites.net/api/v1/Books/{{positive_id}}

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно. 
Тело ответа в формате JSON возвращается от сервера. 
Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 16:41:19 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
{
    "id": 1,
    "title": "Book 1",
    "description": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",
    "pageCount": 100,
    "excerpt": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",
    "publishDate": "2023-06-21T16:41:19.6627711+00:00"
}
```

## Books: получение 1 активности (базовый негативный сценарий)

GET {{Books}}{{negative_minus}}

URL https://fakerestapi.azurewebsites.net/api/v1/Books/{{negative_minus}}

Ожидаемый результат: HTTP статус: код ответа 404 Error: Not Found.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 16:42:32 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
    "title": "Not Found",
    "status": 404,
    "traceId": "00-addd8c31a679a44db0db9ce959ad2694-b72520e336f60440-00"
}
```

## Books: редактирование 1 активности (базовый позитивный сценарий)

PUT {{Books}}{{positive_id}}

URL https://fakerestapi.azurewebsites.net/api/v1/Books/{{positive_id}}

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно. 
Тело ответа в формате JSON возвращается от сервера. 
Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Content-Type: application/json
  Content-Length: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса:
```
{
 "id": {{positive_id}},
 "title": "string",
 "description": "string",
 "pageCount": 0,
 "excerpt": "string",
 "publishDate": "2023-06-20T21:09:17.579Z"
}
```
Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 16:44:37 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
{
    "id": 1,
    "title": "string",
    "description": "string",
    "pageCount": 0,
    "excerpt": "string",
    "publishDate": "2023-06-20T21:09:17.579Z"
}
```

## Books: редактирование 1 активности (базовый негативный сценарий)

PUT {{Books}}/{{negative_null}}/

URL https://fakerestapi.azurewebsites.net/api/v1/Books/{{negative_null}}

Ожидаемый результат: HTTP статус: 400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Content-Type: application/json
  Content-Length: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса:
```
{
 "id": {{negative_null}},
 "title": "string",
 "description": "string",
 "pageCount": 0,
 "excerpt": "string",
 "publishDate": "2023-06-20T21:09:17.579Z"
}
```
Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 16:46:58 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
{
    "id": 0,
    "title": "string",
    "description": "string",
    "pageCount": 0,
    "excerpt": "string",
    "publishDate": "2023-06-20T21:09:17.579Z"
}
```

## Books: редактирование 1 активности (дополнительный негативный сценарий)

PUT {{Books}}/{{negative_minus}}/

URL https://fakerestapi.azurewebsites.net/api/v1/Books/{{negative_minus}}

Ожидаемый результат: HTTP статус: 400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Content-Type: application/json
  Content-Length: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса:
```
{
 "id": {{negative_minus}},
 "title": "string",
 "description": "string",
 "pageCount": 0,
 "excerpt": "string",
 "publishDate": "2023-06-20T21:09:17.579Z"
}
```
Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 16:50:39 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
{
    "id": -1,
    "title": "string",
    "description": "string",
    "pageCount": 0,
    "excerpt": "string",
    "publishDate": "2023-06-20T21:09:17.579Z"
}
```

## Books: удаление активности (базовый позитивный сценарий)

DELETE {{Books}}{{positive_id}}

URL https://fakerestapi.azurewebsites.net/api/v1/Books/{{positive_id}}

Ожидаемый результат: HTTP статус: код ответа 200 OK.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 16:54:00 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: отсутствует

## Books: удаление активности (базовый негативный сценарий)

DELETE {{Books}}/{{negative_null}}/

URL https://fakerestapi.azurewebsites.net/api/v1/Books/{{negative_null}}/

Ожидаемый результат: HTTP статус: 400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 16:54:22 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: отсутствует

## Books: удаление активности (дополнительный негативный сценарий)

DELETE {{Books}}//{{negative_minus}}/

URL https://fakerestapi.azurewebsites.net/api/v1/Books/{{negative_null}}/

Ожидаемый результат: HTTP статус: 400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 16:54:58 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: отсутствует


Тело ответа в формате JSON возвращается от сервера. 
Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:
```
User-Agent: PostmanRuntime/7.32.2
Accept: */*
Cache-Control: no-cache
Postman-Token: d281c835-d784-4d8c-9ce2-c2bb556f4104
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
```

Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 19:39:32 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
[
 {
        "id": 1,
        "idBook": 1,
        "firstName": "First Name 1",
        "lastName": "Last Name 1"
    },
    ...
    {
        "id": 581,
        "idBook": 200,
        "firstName": "First Name 581",
        "lastName": "Last Name 581"
    }
]
```

## Authors: создание нового автора(базовый позитивный сценарий)

POST {{authors}}

URL https://fakerestapi.azurewebsites.net/api/v1/Authors

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно. 
Тело ответа в формате JSON возвращается от сервера. 
Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:
```
Content-Type: application/json
User-Agent: PostmanRuntime/7.32.2
Accept: */*
Cache-Control: no-cache
Postman-Token: bada4f09-1236-4713-845b-ed214e38ed4c
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Length: 82
```
Тело запроса: 
```
{
  "id": 1,
  "idBook": 1,
  "firstName": "string",
  "lastName": "string"
}
```

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 19:43:25 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
{
    "id": 1,
    "idBook": 1,
    "firstName": "string",
    "lastName": "string"
}
```

## Authors: создание нового автора (базовый негативный сценарий)

POST {{Authors}}

URL https://fakerestapi.azurewebsites.net/api/v1/Authors

Ожидаемый результат: HTTP статус: код ответа 400.

Заголовки запроса:
```
Content-Type: application/json
User-Agent: PostmanRuntime/7.32.2
Accept: */*
Cache-Control: no-cache
Postman-Token: 3a4e3f21-3f98-4418-ab67-da2cd2ebe07a
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Length: 86
```
Тело запроса: 
```
{
  "id": ,
  "idBook": 20,
  "firstName": "string",
  "lastName": "string"
}
```

Заголовки ответа:
```
ontent-Type: application/problem+json; charset=utf-8
Date: Thu, 22 Jun 2023 20:30:17 GMT
Server: Kestrel
Transfer-Encoding: chunked
```

Тело ответа: 
```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-f80ec9ac6c4146428ff768ed9092834d-48f3c56bcfb91043-00",
    "errors": {
        "$.id": [
            "',' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."
        ]
    }
}
```

## Authors: создание нового автора (дополнительный негативный сценарий)

POST {{Authors}}

URL https://fakerestapi.azurewebsites.net/api/v1/Authors

Ожидаемый результат: HTTP статус: код ответа 400.

Заголовки запроса:
```
Content-Type: application/json
User-Agent: PostmanRuntime/7.32.2
Accept: */*
Cache-Control: no-cache
Postman-Token: 8887b2e3-b262-4764-b5ab-6b5268ed2ce4
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Length: 86
```
Тело запроса: 
```
{
  "id": test,
  "idBook": 20,
  "firstName": "string",
  "lastName": "string"
}
```

Заголовки ответа:
```
CContent-Type: application/problem+json; charset=utf-8
Date: Thu, 22 Jun 2023 20:30:52 GMT
Server: Kestrel
Transfer-Encoding: chunked
```

Тело ответа: 
```
{
    {
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-310ee0d87f411f4fa22bbd9f5154c78d-d918930e2247374f-00",
    "errors": {
        "$.id": [
            "'test,\r\n  \"idBook\": 20,\r\n  \"firstName\": \"string\",\r\n  \"lastName\": \"string\"\r\n}' is an invalid JSON literal. Expected the literal 'true'. Path: $.id | LineNumber: 1 | BytePositionInLine: 9."
        ]
    }
}
```

## Authors: получение книги автора (базовый позитивный сценарий)

GET {{Authors}}{{positive_id}}

URL https://fakerestapi.azurewebsites.net/api/v1/Authors/{{positive_id}}

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно. 
Тело ответа в формате JSON возвращается от сервера. 
Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:
```
Content-Type: application/json
User-Agent: PostmanRuntime/7.32.2
Accept: */*
Cache-Control: no-cache
Postman-Token: e23a296e-f95f-4246-aa51-b1681538fdc7
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Length: 86
```
Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 20:45:28 GMT
Server: Kestrel
Transfer-Encoding: chunked
```

Тело ответа: 
```
{
    "id": 1,
    "idBook": 1,
    "firstName": "First Name 1",
    "lastName": "Last Name 1"
  },
  {
    "id": 2,
    "idBook": 1,
    "firstName": "First Name 2",
    "lastName": "Last Name 2"
  },
  {
    "id": 3,
    "idBook": 1,
    "firstName": "First Name 3",
    "lastName": "Last Name 3"
  }
```

## Authors: получение книги автора (базовый негативный сценарий)

GET {{Authors}}{{negative_minus}}

URL https://fakerestapi.azurewebsites.net/api/v1/Authors/{{negative_minus}}

Ожидаемый результат: HTTP статус: код ответа 404 Error: Not Found.

Заголовки запроса:
```
User-Agent: PostmanRuntime/7.32.2
Accept: */*
Cache-Control: no-cache
Postman-Token: a50fc59f-bd0b-4448-86cb-50b6cf800827
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/problem+json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 20:53:06 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
 {
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
    "title": "Not Found",
    "status": 404,
    "traceId": "00-661da43489b9284b9dfb4635b4f0dec6-4f6e19be33b6be4f-00"
}
```


## Authors: получение книги автора (дополнительный негативный сценарий)

GET {{Authors}}{{negative_text}}

URL https://fakerestapi.azurewebsites.net/api/v1/Authors/{{negative_text}}

Ожидаемый результат: HTTP статус: код ответа 400 Error: Bad Request.

Заголовки запроса:
```
User-Agent: PostmanRuntime/7.32.2
Accept: */*
Cache-Control: no-cache
Postman-Token: 3810fbc4-4afe-4c51-92e9-51ac1b51977c
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
CContent-Type: application/problem+json; charset=utf-8
Date: Thu, 22 Jun 2023 21:08:28 GMT
Server: Kestrel
Transfer-Encoding: chunked
```

Тело ответа: 
```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-8c3581e3cbfdab43ae6f45b1a4731a85-459c63609dfa9b41-00",
    "errors": {
        "id": [
            "The value 'test' is not valid."
        ]
    }
}
```

## Authors: получение 1 автора (базовый позитивный сценарий)

GET {{Authors}}{{positive_id}}

URL https://fakerestapi.azurewebsites.net/api/v1/Authors/{{positive_id}}

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно. 
Тело ответа в формате JSON возвращается от сервера. 
Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:
```
PUser-Agent: PostmanRuntime/7.32.2
Accept: */*
Cache-Control: no-cache
Postman-Token: 536e936a-8542-42be-9c85-f75d7779a79c
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 21:17:47 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
{
    "id": 1,
    "idBook": 1,
    "firstName": "First Name 1",
    "lastName": "Last Name 1"
}
```
# Authors: получение 1 автора (базовый негативный сценарий)

GET {{Authors}}{{negative_minus}}

URL https://fakerestapi.azurewebsites.net/api/v1/Authors/{{negative_minus}}

Ожидаемый результат: HTTP статус: код ответа 404 Error: Not Found.

Заголовки запроса:
```
User-Agent: PostmanRuntime/7.32.2
Accept: */*
Cache-Control: no-cache
Postman-Token: 7c9fcd27-fc78-4fef-a34d-24795ee8c710
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/problem+json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 21:39:26 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
 {
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
    "title": "Not Found",
    "status": 404,
    "traceId": "00-22f6f4ab01408d4c98bdca5b800ae56d-393636b754d84349-00"
}
```
## Authors: получение 1 автора (дополнительный негативный сценарий)

GET {{Authors}}{{negative_text}}

URL https://fakerestapi.azurewebsites.net/api/v1/Authors/{{negative_text}}

Ожидаемый результат: HTTP статус: код ответа 400 Error: Bad Request.

Заголовки запроса:
```
User-Agent: PostmanRuntime/7.32.2
Accept: */*
Cache-Control: no-cache
Postman-Token: f8e6da4f-eb90-40d2-a31e-dba8df4f6b55
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/problem+json; charset=utf-8
Date: Thu, 22 Jun 2023 21:43:55 GMT
Server: Kestrel
Transfer-Encoding: chunked
```

Тело ответа: 
```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-6bc1f9d7a235e84580ee6d92aa4162fd-76176e437243ff4b-00",
    "errors": {
        "id": [
            "The value 'test' is not valid."
        ]
    }
}
```

# Authors: создание нового автора(базовый позитивный сценарий)

PUT {{authors}}

URL https://fakerestapi.azurewebsites.net/api/v1/Authors

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно. 
Тело ответа в формате JSON возвращается от сервера. 
Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:
```
Content-Type: application/json
User-Agent: PostmanRuntime/7.32.2
Accept: */*
Cache-Control: no-cache
Postman-Token: d87a4ee5-76b8-40ae-8fe5-2e817ac3c0a8
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Length: 82
```
Тело запроса: 
```
{
  "id": 1,
  "idBook": 1,
  "firstName": "string",
  "lastName": "string"
}
```

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 21:48:25 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
{
    "id": 1,
    "idBook": 1,
    "firstName": "string",
    "lastName": "string"
}
```

## Authors: обновление автора (базовый негативный сценарий)

PUT {{Authors}}/{{negative_minus}}/

URL https://fakerestapi.azurewebsites.net/api/v1/Authors/{{negative_minus}}

Ожидаемый результат: HTTP статус: 400 Bad requset / 415 (Unsupported Media Type)

Заголовки запроса:
```
Content-Type: text/plain
User-Agent: PostmanRuntime/7.32.2
Accept: */*
Cache-Control: no-cache
Postman-Token: b641f8c6-48ee-4757-b608-8a4d36c179ee
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Length: 83
```
Тело запроса:
```
{
  "id": -1,
  "idBook":10,
  "firstName": "string",
  "lastName": "string"
}
```
Заголовки ответа:
```
Content-Type: application/problem+json; charset=utf-8
Date: Thu, 22 Jun 2023 21:56:03 GMT
Server: Kestrel
Transfer-Encoding: chunked
```

Тело ответа: 
```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-330cc4f5fb3f314398b31ff9213ee2ab-9fbfa7bd1529a549-00"
}
```

## Authors: редактирование 1 активности (дополнительный негативный сценарий)

PUT {{Authors}}/{{negative_text}}/

URL https://fakerestapi.azurewebsites.net/api/v1/Authors/{{negative_text}}

Ожидаемый результат: HTTP статус: 400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
```
Content-Type: application/json
User-Agent: PostmanRuntime/7.32.2
Accept: */*
Cache-Control: no-cache
Postman-Token: 5e8011ea-d5d2-419e-833b-78f8930b3aca
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Length: 85
```
Тело запроса:
```
{
  "id": test,
  "idBook":10,
  "firstName": "string",
  "lastName": "string"
}
```
Заголовки ответа:
```
Content-Type: application/problem+json; charset=utf-8
Date: Thu, 22 Jun 2023 22:03:43 GMT
Server: Kestrel
Transfer-Encoding: chunked
```

Тело ответа: 
```
{
   {
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-1ac11daec877a842ad7de328cab8991d-1d98e08b220d3f4b-00",
    "errors": {
        "id": [
            "The value 'test' is not valid."
        ],
        "$.id": [
            "'test,\r\n  \"idBook\":10,\r\n  \"firstName\": \"string\",\r\n  \"lastName\": \"string\"\r\n}' is an invalid JSON literal. Expected the literal 'true'. Path: $.id | LineNumber: 1 | BytePositionInLine: 9."
        ]
    }
}
```

## Authors: удаление автора (базовый позитивный сценарий)

DELETE {{Authors}}{{positive_id}}

URL https://fakerestapi.azurewebsites.net/api/v1/Authors/{{positive_id}}

Ожидаемый результат: HTTP статус: код ответа 200 OK.

Заголовки запроса:
```
User-Agent: PostmanRuntime/7.32.2
Accept: */*
Cache-Control: no-cache
Postman-Token: 0651570a-e30f-430f-9afd-d3307d7411a3
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
Content-Length: 0
Date: Thu, 22 Jun 2023 23:31:13 GMT
Server: Kestrel
api-supported-versions: 1.0
```

Тело ответа: отсутствует

## Authors: удаление автора (базовый негативный сценарий)

DELETE {{Authors}}/{{negative_minus}}/

URL https://fakerestapi.azurewebsites.net/api/v1/Authors/{{negative_minuse}}/

Ожидаемый результат: HTTP статус: 400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
```
User-Agent: PostmanRuntime/7.32.2
Accept: */*
Cache-Control: no-cache
Postman-Token: d4851c4b-9884-451d-a4e3-c48afdd9fa42
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
Content-Length: 0
Date: Thu, 22 Jun 2023 23:34:43 GMT
Server: Kestrel
api-supported-versions: 1
```

Тело ответа: отсутствует

## Authors: удаление автора (дополнительный негативный сценарий)

DELETE {{Authors}}//{{negative_text}}/

URL https://fakerestapi.azurewebsites.net/api/v1/Authors/{{negative_text}}/

Ожидаемый результат: HTTP статус: 400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
```
User-Agent: PostmanRuntime/7.32.2
Accept: */*
Cache-Control: no-cache
Postman-Token: 8612fc4f-56ee-4e9e-ba24-118f271d7116
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/problem+json; charset=utf-8
Date: Thu, 22 Jun 2023 23:43:29 GMT
Server: Kestrel
Transfer-Encoding: chunked
```

Тело ответа: 
```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-30c7913121112d4999023d3583780965-f67056740d5bf640-00",
    "errors": {
        "id": [
            "The value 'test' is not valid."
        ]
    }
}
```

# CoverPhotos:получение списка фото с обложки

GET {{CoverPhotos}}
URL https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно.

Тело ответа в формате JSON возвращается от сервера.

Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:

User-Agent: PostmanRuntime/7.32.3
Accept: */*
Postman-Token: 8398ca88-05f8-4540-a682-20a4c522bfa9
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

Тело запроса: отсутствует

Заголовки ответа:

Content-Type: application/json; charset=utf-8; v=1.0
Date: Thu, 22 Jun 2023 09:20:02 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

Тело ответа: 
```
    },
    {
        "id": 136,
        "idBook": 136,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 136&w=250&h=350"
    },
    {
        "id": 137,
        "idBook": 137,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 137&w=250&h=350"
    },
    {
        "id": 138,
        "idBook": 138,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 138&w=250&h=350"
    },
    {
        "id": 139,
        "idBook": 139,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 139&w=250&h=350"
    },
    {
        "id": 140,
        "idBook": 140,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 140&w=250&h=350"
    },
    {
        "id": 141,
        "idBook": 141,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 141&w=250&h=350"
    },
    {
        "id": 142,
        "idBook": 142,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 142&w=250&h=350"
    },
    {
        "id": 143,
        "idBook": 143,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 143&w=250&h=350"
    },
    {
        "id": 144,
        "idBook": 144,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 144&w=250&h=350"
    },
    {
        "id": 145,
        "idBook": 145,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 145&w=250&h=350"
    },
    {
        "id": 146,
        "idBook": 146,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 146&w=250&h=350"
    },
    {
        "id": 147,
        "idBook": 147,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 147&w=250&h=350"
    },
    {
        "id": 148,
        "idBook": 148,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 148&w=250&h=350"
    },
    {
        "id": 149,
        "idBook": 149,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 149&w=250&h=350"
    },
    {
        "id": 150,
        "idBook": 150,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 150&w=250&h=350"
    },
    {
        "id": 151,
        "idBook": 151,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 151&w=250&h=350"
    },
    {
        "id": 152,
        "idBook": 152,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 152&w=250&h=350"
    },
    {
        "id": 153,
        "idBook": 153,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 153&w=250&h=350"
    },
    {
        "id": 154,
        "idBook": 154,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 154&w=250&h=350"
    },
    {
        "id": 155,
        "idBook": 155,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 155&w=250&h=350"
    },
    {
        "id": 156,
        "idBook": 156,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 156&w=250&h=350"
    },
    {
        "id": 157,
        "idBook": 157,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 157&w=250&h=350"
    },
    {
        "id": 158,
        "idBook": 158,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 158&w=250&h=350"
    },
    {
        "id": 159,
        "idBook": 159,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 159&w=250&h=350"
    },
    {
        "id": 160,
        "idBook": 160,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 160&w=250&h=350"
    },
    {
        "id": 161,
        "idBook": 161,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 161&w=250&h=350"
    },
    {
        "id": 162,
        "idBook": 162,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 162&w=250&h=350"
    },
    {
        "id": 163,
        "idBook": 163,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 163&w=250&h=350"
    },
    {
        "id": 164,
        "idBook": 164,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 164&w=250&h=350"
    },
    {
        "id": 165,
        "idBook": 165,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 165&w=250&h=350"
    },
    {
        "id": 166,
        "idBook": 166,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 166&w=250&h=350"
    },
    {
        "id": 167,
        "idBook": 167,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 167&w=250&h=350"
    },
    {
        "id": 168,
        "idBook": 168,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 168&w=250&h=350"
    },
    {
        "id": 169,
        "idBook": 169,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 169&w=250&h=350"
    },
    {
        "id": 170,
        "idBook": 170,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 170&w=250&h=350"
    },
    {
        "id": 171,
        "idBook": 171,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 171&w=250&h=350"
    },
    {
        "id": 172,
        "idBook": 172,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 172&w=250&h=350"
    },
    {
        "id": 173,
        "idBook": 173,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 173&w=250&h=350"
    },
    {
        "id": 174,
        "idBook": 174,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 174&w=250&h=350"
    },
    {
        "id": 175,
        "idBook": 175,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 175&w=250&h=350"
    },
    {
        "id": 176,
        "idBook": 176,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 176&w=250&h=350"
    },
    {
        "id": 177,
        "idBook": 177,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 177&w=250&h=350"
    },
    {
        "id": 178,
        "idBook": 178,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 178&w=250&h=350"
    },
    {
        "id": 179,
        "idBook": 179,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 179&w=250&h=350"
    },
    {
        "id": 180,
        "idBook": 180,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 180&w=250&h=350"
    },
    {
        "id": 181,
        "idBook": 181,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 181&w=250&h=350"
    },
    {
        "id": 182,
        "idBook": 182,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 182&w=250&h=350"
    },
    {
        "id": 183,
        "idBook": 183,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 183&w=250&h=350"
    },
    {
        "id": 184,
        "idBook": 184,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 184&w=250&h=350"
    },
    {
        "id": 185,
        "idBook": 185,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 185&w=250&h=350"
    },
    {
        "id": 186,
        "idBook": 186,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 186&w=250&h=350"
    },
    {
        "id": 187,
        "idBook": 187,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 187&w=250&h=350"
    },
    {
        "id": 188,
        "idBook": 188,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 188&w=250&h=350"
    },
    {
        "id": 189,
        "idBook": 189,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 189&w=250&h=350"
    },
    {
        "id": 190,
        "idBook": 190,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 190&w=250&h=350"
    },
    {
        "id": 191,
        "idBook": 191,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 191&w=250&h=350"
    },
    {
        "id": 192,
        "idBook": 192,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 192&w=250&h=350"
    },
    {
        "id": 193,
        "idBook": 193,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 193&w=250&h=350"
    },
    {
        "id": 194,
        "idBook": 194,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 194&w=250&h=350"
    },
    {
        "id": 195,
        "idBook": 195,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 195&w=250&h=350"
    },
    {
        "id": 196,
        "idBook": 196,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 196&w=250&h=350"
    },
    {
        "id": 197,
        "idBook": 197,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 197&w=250&h=350"
    },
    {
        "id": 198,
        "idBook": 198,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 198&w=250&h=350"
    },
    {
        "id": 199,
        "idBook": 199,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 199&w=250&h=350"
    },
    {
        "id": 200,
        "idBook": 200,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 200&w=250&h=350"
    }
]
```
# CoverPhotos: создание нового фото с обложки (базовый позитивный сценарий)
POST {{CoverPhotos}}
URL https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно.

Тело ответа в формате JSON возвращается от сервера.

Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:

Content-Type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Postman-Token: 6fa718f5-fd04-4df4-8170-6a438ffedf25
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Length: 57

Тело запроса:
```
 {
  "id": 1,
  "idBook": 0,
  "url": "string"
}
```

Заголовки ответа:

Content-Type: application/problem+json; charset=utf-8
Date: Thu, 22 Jun 2023 09:24:03 GMT
Server: Kestrel
Transfer-Encoding: chunked

Тело ответа: 
```
{
  "id": 1,
  "idBook": 0,
  "url": "string"
}
```

# CoverPhotos:создание нового фото с обложки (базовый негативный сценарий) 
POST {{CoverPhotos}}
URL https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos

Ожидаемый результат: HTTP статус: 400 Bad requset / 405 (Method Not Allowed)
Заголовки запроса:
Content-Type: text/plain
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Postman-Token: f0e5f95d-187f-45df-9f46-c48c4a02f4e6
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Length: 51


Тело запроса: 
```
{
  "id": 0,
  "idBook": 0,
  "url": "string"
}
```
Заголовки ответа:
Content-Type: application/problem+json; charset=utf-8
Date: Fri, 23 Jun 2023 08:56:18 GMT
Server: Kestrel
Transfer-Encoding: chunked


Тело ответа: 
```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-8d648bf348728848aad8e5c4a7fd0d0b-be1e4e436ad9b14c-00"
}
```

# CoverPhotos:создание нового фото с обложки (дополнительный негативный сценарий)
POST {{CoverPhotos}}
URL https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos

Ожидаемый результат: HTTP статус: 400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
Content-Type: text/plain
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Postman-Token: 13962f62-40cf-4bd2-b9eb-00cf15f8b858
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Length: 52


Тело запроса: 
```
{
  "id": -1,
  "idBook": 0,
  "url": "string"
}
```

Заголовки ответа:
Content-Type: application/problem+json; charset=utf-8
Date: Fri, 23 Jun 2023 08:59:14 GMT
Server: Kestrel
Transfer-Encoding: chunked


Тело ответа: 
```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-66d832516275fb499de6e74e3b374761-fa8104d3da4a1f43-00"
}
```

# CoverPhotos:получение 1 фото с обложки (базовый позитивный сценарий)
GET {{CoverPhotos}}
URL https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно.

Тело ответа в формате JSON возвращается от сервера.

Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Postman-Token: 5832bf1e-230c-4525-9171-946279997fe4
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive


Тело запроса: отсутствует

Заголовки ответа:
Content-Type: application/json; charset=utf-8; v=1.0
Date: Fri, 23 Jun 2023 08:08:54 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0


Тело ответа: 
```
{
    "id": 1,
    "idBook": 1,
    "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 1&w=250&h=350"
}
```

# CoverPhotos:запрос фото с обложки (базовый негативный сценарий){0}
GET {{CoverPhotos}}
URL https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos

Ожидаемый результат:  HTTP статус: 400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Postman-Token: e79adfdf-3539-405e-9882-d10628924722
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive


Тело запроса: отсутствует

Заголовки ответа:
Content-Type: application/problem+json; charset=utf-8; v=1.0
Date: Fri, 23 Jun 2023 08:13:52 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0


Тело ответа: 
```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
    "title": "Not Found",
    "status": 404,
    "traceId": "00-b2722a8dfa1aa449bd5c73034ec141c5-1abbfed40127484a-00"
}
```
# CoverPhotos:запрос фото с обложки (базовый негативный сценарий){-1}
GET {{CoverPhotos}}
URL https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos

Ожидаемый результат: HTTP статус: 400 Bad requset / 405 (Method Not Allowed)
Заголовки запроса:
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Postman-Token: c6e04d09-65e1-40a3-a26d-08642ced1aa7
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive


Тело запроса: отсутствует

Заголовки ответа:
Content-Type: application/problem+json; charset=utf-8; v=1.0
Date: Fri, 23 Jun 2023 08:16:58 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0


Тело ответа: 
```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
    "title": "Not Found",
    "status": 404,
    "traceId": "00-ba4c7988829e5944818ec243bb340c12-9754394aa0834c40-00"
}
```

# CoverPhotos:Запрос на полное обновление данных фото с обложки(позитивный базовый сценарий){1}
PUT {{CoverPhotos}}
URL https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно.

Тело ответа в формате JSON возвращается от сервера.

Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:
Content-Type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Postman-Token: 02ef5fff-829f-47c5-b707-76074f1e2f59
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Length: 56


Тело запроса: 
```
{

 "id": 1,

 "idBook": 0,

 "url": "string"

}
```

Заголовки ответа:
Content-Type: application/json; charset=utf-8; v=1.0
Date: Fri, 23 Jun 2023 08:25:24 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0


Тело ответа:
```
{
    "id": 1,
    "idBook": 0,
    "url": "string"
}
```
# CoverPhotos:Запрос на полное обновление данных фото с обложки(негативный базовый сценарий){0}
PUT {{CoverPhotos}}
URL https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos

Ожидаемый результат: HTTP статус: 400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
Content-Type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Postman-Token: 71fb6361-b893-4884-bf17-0d4c3cea7980
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Length: 98


Тело запроса: отсутствует

Заголовки ответа:
Content-Type: application/json; charset=utf-8; v=1.0
Date: Fri, 23 Jun 2023 08:27:36 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0


Тело ответа: 
```
{
    "id": 0,
    "idBook": 0,
    "url": null
}
```
# CoverPhotos:Запрос на полное обновление данных фото с обложки(негативный базовый сценарий){-1}
PUT {{CoverPhotos}}
URL https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos

Ожидаемый результат: HTTP статус: 400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
Content-Type: application/json
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Postman-Token: 85195353-7435-4ee7-b5c5-d9042978915c
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Length: 99


Тело запроса: отсутствует

Заголовки ответа:
Content-Type: application/json; charset=utf-8; v=1.0
Date: Fri, 23 Jun 2023 08:30:50 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0


Тело ответа: 
```
{
    "id": -1,
    "idBook": 0,
    "url": null
}
```
# CoverPhotos:удаление фото с обложки (базовый позитивный сценарий)
DELETE {{CoverPhotos}}
URL https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно.

Тело ответа в формате JSON возвращается от сервера.

Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Postman-Token: f6b5a7ed-a971-4d2b-8d9e-f7bd46fd8315
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive


Тело запроса: отсутствует

Заголовки ответа:
Content-Type: application/problem+json; charset=utf-8
Date: Fri, 23 Jun 2023 08:32:06 GMT
Server: Kestrel
Transfer-Encoding: chunked


Тело ответа: 
```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-0f6666c33b4f7647a34994fbf70037a3-087fb5bc4850af4b-00",
    "errors": {
        "id": [
            "The value '}15' is not valid."
        ]
    }
}
```
# CoverPhotos: удаление фото с обложки (базовый негативный сценарий){0}
DELETE {{CoverPhotos}}
URL https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos

Ожидаемый результат: 400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Postman-Token: e8b2ce69-918e-42b4-97c2-94aa6673c233
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive


Тело запроса: отсутствует

Заголовки ответа:
Content-Length: 0
Date: Fri, 23 Jun 2023 08:34:02 GMT
Server: Kestrel
api-supported-versions: 1.0


Тело ответа: отсутствует
# CoverPhotos: удаление фото с обложки (базовый негативный сценарий){-1}
DELETE {{CoverPhotos}}
URL https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos

Ожидаемый результат:400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
User-Agent: PostmanRuntime/7.32.3
Accept: */*
Postman-Token: c7b0ad0f-da54-498d-acd5-22d6e0e36f40
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive


Тело запроса: отсутствует

Заголовки ответа:
Content-Length: 0
Date: Fri, 23 Jun 2023 08:36:11 GMT
Server: Kestrel
api-supported-versions: 1.0


Тело ответа: отсутствует

## Users: получение списка активностей

GET {{users}}

URL https://fakerestapi.azurewebsites.net/api/v1/Users

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно. 
Тело ответа в формате JSON возвращается от сервера. 
Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```

Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Fri23 Jun 2023 06:10:34 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: 
```
[
  {
    "id": 1,
    "userName": "User 1",
    "password": "Password1"
  },
...
  {
    "id": 10,
    "userName": "User 10",
    "password": "Password10"
  }
]
```

## Users: создание новой активности (базовый позитивный сценарий)

POST {{users}}

URL https://fakerestapi.azurewebsites.net/api/v1/Users/

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно. 
Тело ответа в формате JSON возвращается от сервера. 
Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Content-Type: application/json
  Content-Length: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: 
```
{
  "id": 1,
  "userName": "string",
  "password": "string"
}
```

Заголовки ответа:
```
 access-control-allow-origin: * 
 api-supported-versions: 1.0 
 content-type: application/json; charset=utf-8; v=1.0 
 date: Fri23 Jun 2023 06:19:19 GMT 
 server: Kestrel 
 transfer-encoding: chunked 
```

Тело ответа: 
```
{
  "id": 1,
  "userName": "string",
  "password": "string"
}
```

## Users: создание новой активности (базовый негативный сценарий)

POST {{users}}

URL https://fakerestapi.azurewebsites.net/api/v1/Users/

Ожидаемый результат: HTTP статус: код ответа 400.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Content-Type: application/json
  Content-Length: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: 
```
{
  "id": ,
  "userName": "string",
  "password": "string"
}
```

Заголовки ответа:
```
 access-control-allow-origin: * 
 content-type: application/problem+json; charset=utf-8 
 date: Fri23 Jun 2023 06:30:21 GMT 
 server: Kestrel 
 transfer-encoding: chunked 
```

Тело ответа: 
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-ceea3a6469b6cf43901ce7fb2cbf360f-aaed23599d023442-00",
  "errors": {
    "$.id":   [
      "',' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."
              ]
            }
}
```

## Users: создание новой активности (дополнительный негативный сценарий)

POST {{users}}

URL https://fakerestapi.azurewebsites.net/api/v1/Users/

Ожидаемый результат: HTTP статус: код ответа 400.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Content-Type: application/json
  Content-Length: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: 
```
{
  "id": -1,
  "userName": "string",
  "password": "string"
}
```

Заголовки ответа:
```
 access-control-allow-origin: * 
 api-supported-versions: 1.0 
 content-type: application/json; charset=utf-8; v=1.0 
 date: Fri23 Jun 2023 06:35:59 GMT 
 server: Kestrel 
 transfer-encoding: chunked
```

Тело ответа: 
```
{
  "id": -1,
  "userName": "string",
  "password": "string"
}
```

## Users: получение 1 активности (базовый позитивный сценарий)

GET {{users}}{{positive_id}}

URL https://fakerestapi.azurewebsites.net/api/v1/Users/{{positive_id}}

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно. 
Тело ответа в формате JSON возвращается от сервера. 
Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
 api-supported-versions: 1.0 
 content-type: application/json; charset=utf-8; v=1.0 
 date: Fri23 Jun 2023 06:40:14 GMT 
 server: Kestrel 
 transfer-encoding: chunked
```

Тело ответа: 
```
{
  "id": 1,
  "userName": "User 1",
  "password": "Password1"
}
```

## Users: получение 1 активности (базовый негативный сценарий)

GET {{users}}{{negative_minus}}

URL https://fakerestapi.azurewebsites.net/api/v1/Users/{{negative_minus}}

Ожидаемый результат: HTTP статус: код ответа 404 Error: Not Found.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
 api-supported-versions: 1.0 
 content-type: application/problem+json; charset=utf-8; v=1.0 
 date: Fri23 Jun 2023 06:43:47 GMT 
 server: Kestrel 
 transfer-encoding: chunked
```

Тело ответа: 
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
  "title": "Not Found",
  "status": 404,
  "traceId": "00-52906cba78f7904cab044df82aa4504e-d9538130bef86247-00"
}
```

## Users: редактирование 1 активности (базовый позитивный сценарий)

PUT {{users}}{{positive_id}}

URL https://fakerestapi.azurewebsites.net/api/v1/Users/{{positive_id}}

Ожидаемый результат: HTTP статус: код ответа 200. Запрос выполнен успешно. 
Тело ответа в формате JSON возвращается от сервера. 
Схема JSON отображена корректно, имена и типы полей соответствуют ожидаемым. Каждое поле JSON объекта соответствует аргументу метода сервиса.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Content-Type: application/json
  Content-Length: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса:
```
{
  "id": 1,
  "userName": "string",
  "password": "string"
}
```
Заголовки ответа:
```
 access-control-allow-origin: * 
 api-supported-versions: 1.0 
 content-type: application/json; charset=utf-8; v=1.0 
 date: Fri23 Jun 2023 06:56:26 GMT 
 server: Kestrel 
 transfer-encoding: chunked
```

Тело ответа: 
```
{
  "id": 1,
  "userName": "string",
  "password": "string"
}
```

## Users: редактирование 1 активности (базовый негативный сценарий)

PUT {{users}}/{{negative_null}}/

URL https://fakerestapi.azurewebsites.net/api/v1/Users/{{negative_null}}

Ожидаемый результат: HTTP статус: 400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Content-Type: application/json
  Content-Length: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса:
```
{
  "id": 0,
  "userName": "string",
  "password": "string"
}
```
Заголовки ответа:
```
 api-supported-versions: 1.0 
 content-type: application/json; charset=utf-8; v=1.0 
 date: Fri23 Jun 2023 07:11:30 GMT 
 server: Kestrel 
 transfer-encoding: chunked
```

Тело ответа: 
```
{
  "id": 0,
  "userName": "string",
  "password": "string"
}
```

## Users: редактирование 1 активности (дополнительный негативный сценарий)

PUT {{users}}/{{negative_minus}}/

URL https://fakerestapi.azurewebsites.net/api/v1/Users/{{negative_minus}}

Ожидаемый результат: HTTP статус: 400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Content-Type: application/json
  Content-Length: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса:
```
{
  "id": -2,
  "userName": "string",
  "password": "string"
}
```
Заголовки ответа:
```
 access-control-allow-origin: * 
 api-supported-versions: 1.0 
 content-type: application/json; charset=utf-8; v=1.0 
 date: Fri23 Jun 2023 07:13:19 GMT 
 server: Kestrel 
 transfer-encoding: chunked
```

Тело ответа: 
```
{
  "id": -2,
  "userName": "string",
  "password": "string"
}
```

## Users: удаление активности (базовый позитивный сценарий)

DELETE {{users}}{{positive_id}}

URL https://fakerestapi.azurewebsites.net/api/v1/Users/{{positive_id}}

Ожидаемый результат: HTTP статус: код ответа 200 OK.

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Fri23 Jun 2023 07:16:51 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: отсутствует

## Users: удаление активности (базовый негативный сценарий)

DELETE {{users}}/{{negative_null}}/

URL https://fakerestapi.azurewebsites.net/api/v1/Users/{{negative_null}}/

Ожидаемый результат: HTTP статус: 400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
Content-Type: application/json; charset=utf-8; v=1.0
Date: Fri23 Jun 2023 07:18:30 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
```

Тело ответа: отсутствует

## Users: удаление активности (дополнительный негативный сценарий)

DELETE {{users}}//{{negative_minus}}/

URL https://fakerestapi.azurewebsites.net/api/v1/Users/{{negative_null}}/

Ожидаемый результат: HTTP статус: 400 Bad requset / 405 (Method Not Allowed)

Заголовки запроса:
```
  Postman-Token: <calculated when request is sent>
  Host: <calculated when request is sent>
  User-Agent: PostmanRuntime/7.32.3
  Accept: */*
  Accept-Encoding: gzip, deflate, br
  Connection: keep-alive
```
Тело запроса: отсутствует

Заголовки ответа:
```
 access-control-allow-origin: * 
 api-supported-versions: 1.0 
 content-length: 0 
 date: Fri23 Jun 2023 07:40:02 GMT 
 server: Kestrel
```
Тело ответа: отсутствует


