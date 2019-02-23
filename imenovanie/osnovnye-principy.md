# Основные принципы

Напомню, что все предлагаемые принципы имеют только одну цель сэкономить ваше "мыслетопливо" - один из самых важных ресурсов разработчика.

### Тождественность

> Если в коде описывается одна и та же сущность, но с разными именами, то эти имена есть одно и тоже, поэтому стоит использовать одно.

Например, у нас есть блок кода, который создает пути до изображений:

```javascript
const pictures = ['dog', 'bmw', 'phone']

const addFolder = (photo) => '2019/' + photo
const addExtension = (picture) => picture + '.jpg'

const pathList = pictures
  .map(addFolder)
  .map(addExtension)

console.log(pathList) // ["2019/dog.jpg", "2019/bmw.jpg", "2019/phone.jpg"]
```

Это может показаться совсем незначительным и безобидным, но когда вы работаете с большими объемами кода, но голове придется постоянно держать два имени. Получается, что `picture` и `photo` описывают по сути одно и тоже, поэтому достаточно выбрать одно именование, например `picture`:

```javascript
const pictures = ['dog', 'bmw', 'phone']

const addFolder = (picture) => '2019/' + picture
const addExtension = (picture) => picture + '.jpg'

const pathList = pictures
  .map(addFolder)
  .map(addExtension)

console.log(pathList) // ["2019/dog.jpg", "2019/bmw.jpg", "2019/phone.jpg"]
```

### Абстракция

// @TODO

### Соответствие названия содержанию

// @TODO

### Единообразие

// @TODO







