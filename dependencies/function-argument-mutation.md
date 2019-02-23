# Функция влияет на аргумент

С этим блоком:

```javascript
const items = [1, 2, 3]

const addItem = (items, item) => items.push(item)
const newItem = 4

addItem(items, newItem)

console.log(items) // { items: [ 1, 2, 3, 4 ] }
```

А также с этим блоком:

```javascript
const items = [1, 2, 3]

const addItem = (items, item) => {
  const newItems = items.slice()
  newItems.push(item)
  return newItems
}

const newItem = 4
const newItems = addItem(items, newItem)

console.log(items) // { items: [ 1, 2, 3 ] }
console.log(newItems) // { items: [ 1, 2, 3, 4 ] }
```

// @TODO

