# От чего зависит функция

Сравните этот блок кода:

```javascript
const items = [1, 2, 3]

const addItem = (item) => items.push(item)
const newItem = 4

addItem(newItem)

console.log(items) // { items: [ 1, 2, 3, 4 ] }
```

С этим блоком:

```javascript
const items = [1, 2, 3]

const addItem = (items, item) => items.push(item)
const newItem = 4

addItem(items, newItem)

console.log(items) // { items: [ 1, 2, 3, 4 ] }
```

// @TODO

