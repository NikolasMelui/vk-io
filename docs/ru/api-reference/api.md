# API

```js
const { api } = vk;
```

API предоставляет удобный интерфейс для взаимодействия без прямого вызова `api.call` с помощью алиасов `api.<method>`

Достаточно скопировать названия метода и вызвать

```js
api.wall.get();
```

## call
Выполняет метод, используется как альтернативный вызов методов

```js
api.call(method, params); // => Promise<Mixed>
```

| Параметр | Тип    | Описание          |
|----------|--------|-------------------|
| method   | string | Метод             |
| params   | Object | Список параметров |

Вместо прямого вызова `api.call` стоит использовать алиасы

```js
api.call('messages.send', {...});

// VS

api.messages.send({...});
```

В случае отсутствия алиаса или нужды прямой передачи метода, тогда подходит идеально

## callWithRequest
Вызов метода через объект `Request`

```js
api.callWithRequest(request); // => Promise<Mixed>
```

| Параметр | Тип                   | Описание       |
|----------|-----------------------|----------------|
| request  | [Request](request.md) | Объект запроса |

## procedure
Выполняет процедуру в приложении

```js
api.procedure(name, params); // => Promise<Mixed>
```

| Параметр | Тип    | Описание           |
|----------|--------|--------------------|
| name     | string | Название процедуры |
| params   | Object | Список параметров  |

## isMethod
Проверяет, является ли строка методом

```js
api.isMethod(method); // => boolean
```

| Параметр | Тип    | Описание            |
|----------|--------|---------------------|
| method   | string | Строка для проверки |