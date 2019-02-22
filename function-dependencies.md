# От чего зависит функция

 Сравните два блока кода





```text
const state = {
  items: [1, 2, 3]
}

const addItem = (item) => state.items.push(item)
const newItem = 4

addItem(newItem)

console.log(state) // { items: [ 1, 2, 3, 4 ] }
```

// @TODO

```text
const state = {
  items: [1, 2, 3]
}

const addItem = (state, item) => state.items.push(item)
const newItem = 4

addItem(state, newItem)

console.log(state) // { items: [ 1, 2, 3, 4 ] }
```

