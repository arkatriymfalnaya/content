🛠 Если вызвать двойное отрицание, можно быстро привести любое выражение к логическому типу.

```js
const sum = 2 + 2
const truthy = !!sum

console.log(truthy)
// true
```

Работает это так:

1. Первое отрицание приводит значение к отрицательному логическому значению `!sum -> false`.
1. Второе отрицание инвертирует значение `!false -> true`.
