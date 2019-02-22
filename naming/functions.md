# Именование функций

### Содержание соответствует названию

В идеале название функции должно полностью отражать ее содержание, если функция делает больше, чем то, что указано в ее названии, значит вы обманываете или себя или читающего ваш код, например:

```javascript
const addItalic = text => `<i>${text}</i>`;
const addBold = text => `<i>${text}</i>`;
const saveToStorage = text => localStorage.setItem('text', text);

const processText = text => {
  const processedText = addItalic(addBold(text));

  saveToStorage(processedText);
  
  return processedText;
}
```

В примере выше функция `processText` помимо обработки текста занимаете также и сохранением его результат в `localStorage`, получается, что описание функции не соответсвует ее назначению, которое мы определяем из названия. Поэтому мы должны извлечь использование функции `saveToStorage`

Мы можем представить это как отдельный блок кода:

```javascript
const addItalic = text => `<i>${text}</i>`;
const addBold = text => `<i>${text}</i>`;
const saveToStorage = text => localStorage.setItem('text', text);

const processText = text => addItalic(addBold(text))

const text = processText('test')
saveToStorage(text)

// ..
```

Или выделить функцию,  которая объеденит эти две операции. Для этого, чтобы сжать несколько код, несколько модифицирую функцию `saveToStorage`  так, чтобы она отдавала в качестве результата получаемый аргумент, это позволит сделать цепочку вызовов функций.

Учитывая, что `localStorage` возвращает значение `undefined` , и учитывая то, что оператор `||` возвращает крайнее значение из условия, получаем:

```javascript
const addItalic = text => `<i>${text}</i>`;
const addBold = text => `<i>${text}</i>`;
const saveToStorage = text => localStorage.setItem('text', text) || text

const processText = text => addItalic(addBold(text))
const processWithSaving = text => saveToStorage(processText(text))

// ..
```

### Название отражает содержание

Необходимо верно вкладывать смысл в название функций, например:

```javascript
const getRandomNumber = (min, max) => { /*.. */ }
```

Глагол `get` подразумевает получить что-то, значит это что-то уже есть, но в функции выше происходит создание или генерация случайного числа в диапазоне, поэтому корректней использовать другой глагол, например `create` или `generate`:

```javascript
const createRandomNumber = (min, max) => { /*.. */ }
```



