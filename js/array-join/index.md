---
title: "`.join()`"
description: "Возвращает значения всех элементов массива, объединённых в строку."
authors:
  - vitya-ne
related:
  - js/arrays
  - js/array-to-string
  - js/string
tags:
  - doka
---

## Кратко

Метод `join()` возвращает представление массива в виде строки, состоящей из значений всех элементов массива, разделённых запятой или другим указанным разделителем.

## Пример

Объединим массив в строку:

```js
const days = ['пн', 'вт', 'ср']
const daysStr = days.join()

console.log(daysStr)
// пн,вт,ср
```

Объединим массив в строку с использованием разделителя:

```js
const numbers = [2, 12, 85, '06']

console.log(numbers.join('-'))
// 2-12-85-06
```

## Как пишется

Метод `Array.join()` принимает один необязательный аргумент — разделитель значений. Если аргумент не указан, в качестве разделителя будет использован знак `,`. Если аргумент не является строкой, то будет использовано его строковое представление.

`Array.join()` возвращает строку, состоящую из строкового представления значений всех элементов массива, разделённых запятой.

## Как понять

В случае использования разделителя по умолчанию, `join()` возвращает тот же результат, что и метод `toString()`.

Значение элементов массива приводится к их строковому представлению. При этом `null`, `undefined`, а также незаполненные элементы будут представлены пустой строкой.

## Подсказки

💡 Метод `join()` — это удобный способ создания строки классов для элемента React в зависимости от условий:

```js
const className = [
  'menu-item',
  isSelected && 'selected',
  disabled && 'disabled'
].filter(Boolean).join(' ')
```
