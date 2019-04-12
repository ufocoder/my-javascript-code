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

И с этим:
```js
class Collection extends Array {
  add (item) {
    return this.push(item)
  }
  
  remove (item) {
    return this.splice(this.findIndex(item), 1)
  }
}

const items = new Collection(1, 2, 3) // Collection(3) [1, 2, 3]

items.add(5) // 4 (length)
items // Collection(4) [1, 2, 3, 5]
items.remove(3) // Collection [3]
items // Collection(3) [1, 2, 5]
```
