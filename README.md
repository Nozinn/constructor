# Использование new Date, new Set и new Map в JavaScript

## new Date

Конструктор `new Date()` используется для создания объектов даты и времени. Даты в JavaScript основаны на временной метке Unix (количество миллисекунд, прошедших с 1 января 1970 года UTC). 

### Способы создания объекта `Date`:
- `new Date()` — создаёт объект с текущей датой и временем.
- `new Date(milliseconds)` — создаёт объект, основанный на количестве миллисекунд с 1 января 1970 года.
- `new Date(dateString)` — разбирает строку с датой и создаёт соответствующий объект.
- `new Date(year, month, day, hours, minutes, seconds, milliseconds)` — создаёт дату, используя числовые параметры.

### Примеры:
```javascript
let now = new Date(); // текущая дата и время
let specificDate = new Date("2023-10-15"); // создание даты из строки
let timestampDate = new Date(1700000000000); // дата из миллисекунд
let customDate = new Date(2022, 10, 25, 18, 30); // 25 ноября 2022 года, 18:30
```

### Методы `Date`
```javascript
let date = new Date();
console.log(date.getFullYear()); // Получить год
console.log(date.getMonth()); // Получить месяц (0-11)
console.log(date.getDate()); // Получить день месяца
console.log(date.getDay()); // День недели (0 - воскресенье, 6 - суббота)
console.log(date.getHours()); // Получить часы
console.log(date.getMinutes()); // Получить минуты
console.log(date.getSeconds()); // Получить секунды
console.log(date.toISOString()); // Преобразовать в строку ISO 8601
```

## new Set

Объект `Set` представляет собой коллекцию уникальных значений. `Set` не допускает дублирования элементов и сохраняет порядок вставки.

### Особенности `Set`:
- Позволяет хранить только уникальные значения.
- Поддерживает добавление, удаление, проверку наличия элемента.
- Можно перебирать элементы множества.

### Примеры:
```javascript
let mySet = new Set([1, 2, 3, 3, 4]); // {1, 2, 3, 4}
mySet.add(5); // Добавить элемент
mySet.delete(2); // Удалить элемент
console.log(mySet.has(3)); // Проверить наличие элемента
console.log(mySet.size); // Размер множества
```

### Итерация по `Set`
```javascript
for (let value of mySet) {
    console.log(value);
}
```

### Применение `Set`
- Удаление дубликатов из массива:
```javascript
let numbers = [1, 2, 3, 3, 4, 5, 5];
let uniqueNumbers = [...new Set(numbers)];
console.log(uniqueNumbers); // [1, 2, 3, 4, 5]
```

## new Map

Объект `Map` используется для хранения пар ключ-значение, где ключи могут быть любого типа.

### Отличия `Map` от обычного объекта:
- `Map` допускает любые значения в качестве ключей (объекты, числа, строки).
- `Map` сохраняет порядок добавления элементов.
- У `Map` есть свойство `size` для получения количества элементов.

### Примеры:
```javascript
let myMap = new Map();
myMap.set("name", "Alice");
myMap.set(42, "Number Key");
myMap.set(true, "Boolean Key");
console.log(myMap.get("name")); // "Alice"
console.log(myMap.has(42)); // true
console.log(myMap.size); // 3
```

### Итерация по `Map`
```javascript
for (let [key, value] of myMap) {
    console.log(`${key}: ${value}`);
}
```

### Применение `Map`
- Хранение настроек и конфигураций:
```javascript
let settings = new Map();
settings.set("theme", "dark");
settings.set("fontSize", 16);
console.log(settings.get("theme")); // "dark"
```

- Использование объектов в качестве ключей:
```javascript
let objKey = { id: 1 };
let userData = new Map();
userData.set(objKey, "User data");
console.log(userData.get(objKey)); // "User data"
```

