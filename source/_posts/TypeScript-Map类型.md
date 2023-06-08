---
title: TypeScript-Map类型
date: 2023-06-08 09:48:04
tags: TypeScript
---


在TypeScript中，Map类型用于定义具有特定键和值类型的映射结构。它类似于JavaScript中的Map对象，可以存储键值对，并提供一系列操作方法。

要定义Map类型，需要使用泛型。泛型允许您指定键和值的类型。以下是创建Map类型的基本语法示例：

```typescript
let myMap: Map<KeyType, ValueType> = new Map<KeyType, ValueType>();
```

在上面的代码中，KeyType和ValueType是您希望在Map中使用的键和值的类型。

以下是一个具体的示例，演示如何使用Map类型：

```typescript
// 定义一个字符串到数字的映射
let numberMap: Map<string, number> = new Map<string, number>();

// 添加键值对
numberMap.set('one', 1);
numberMap.set('two', 2);
numberMap.set('three', 3);

// 获取值
console.log(numberMap.get('two')); // 输出: 2

// 检查键是否存在
console.log(numberMap.has('four')); // 输出: false

// 迭代所有键值对
numberMap.forEach((value, key) => {
  console.log(`${key}: ${value}`);
});
```



当涉及到 TypeScript 中的 Map 类型时，有许多可以用于操作和访问映射的方法和属性。以下是一些常用的 Map 方法函数的示例：

1. `set(key, value)`: 向 Map 中添加一个键值对。
```typescript
let myMap: Map<string, number> = new Map<string, number>();
myMap.set('one', 1);
myMap.set('two', 2);
```

2. `get(key)`: 获取给定键的值。
```typescript
console.log(myMap.get('one')); // 输出: 1
```

3. `has(key)`: 检查指定键是否存在于 Map 中。
```typescript
console.log(myMap.has('two')); // 输出: true
console.log(myMap.has('three')); // 输出: false
```

4. `delete(key)`: 删除指定键的值。
```typescript
myMap.delete('one');
console.log(myMap.has('one')); // 输出: false
```

5. `clear()`: 清空 Map 中的所有键值对。
```typescript
myMap.clear();
console.log(myMap.size); // 输出: 0
```

6. `size`: 获取 Map 中键值对的数量。
```typescript
console.log(myMap.size);
```

7. `forEach(callback)`: 迭代 Map 中的键值对，并对每个键值对执行回调函数。
```typescript
myMap.forEach((value, key) => {
  console.log(`${key}: ${value}`);
});
```

8. `keys()`: 返回一个包含 Map 中所有键的迭代器。可以使用 `for...of` 循环或 `Array.from()` 方法来遍历迭代器并访问键。
```typescript
let myMap: Map<string, number> = new Map<string, number>();
myMap.set('one', 1);
myMap.set('two', 2);

let keysIterator = myMap.keys();
for (let key of keysIterator) {
  console.log(key);
}
// 输出:
// one
// two

// 或者使用 Array.from() 方法将迭代器转换为数组
let keysArray = Array.from(myMap.keys());
console.log(keysArray); // 输出: ['one', 'two']
```

9. `values()`: 返回一个包含 Map 中所有值的迭代器。可以使用 `for...of` 循环或 `Array.from()` 方法来遍历迭代器并访问值。
```typescript
let valuesIterator = myMap.values();
for (let value of valuesIterator) {
  console.log(value);
}
// 输出:
// 1
// 2

// 或者使用 Array.from() 方法将迭代器转换为数组
let valuesArray = Array.from(myMap.values());
console.log(valuesArray); // 输出: [1, 2]
```

10. `entries()`: 返回一个包含 Map 中所有键值对的迭代器。每个键值对都表示为一个数组 `[key, value]`。可以使用 `for...of` 循环或 `Array.from()` 方法来遍历迭代器并访问键值对。
```typescript
let entriesIterator = myMap.entries();
for (let entry of entriesIterator) {
  console.log(entry[0], entry[1]);
}
// 输出:
// one 1
// two 2

// 或者使用 Array.from() 方法将迭代器转换为数组
let entriesArray = Array.from(myMap.entries());
console.log(entriesArray);
// 输出: [['one', 1], ['two', 2]]
```

请注意，迭代器方法返回的是一个迭代器对象，可以使用 `for...of` 循环来遍历其内容。或者，您可以使用 `Array.from()` 方法将迭代器转换为数组。

这些方法提供了一种遍历 Map 中键、值或键值对的方式，使您能够对它们进行进一步处理和操作。

希望这些说明对您有帮助！


