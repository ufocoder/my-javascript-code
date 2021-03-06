# Принципы именования

1. Конкретизация
2. Достаточность
3. Тождественность
4. Единообразие
5. Название = содержанию

Принципы ниже **применяются как отдельно так и дополняют друг друга**. Причем на практике могут возникнуть ситуации в крайних случаях, когда придется пожертвовать строгостью некоторого принципа в угоду удобству пользования кодом.

### Конкретизация <a id="abstraction"></a>

Представьте, что вы хотите рассмотреть насекомое, которое ползет по земле, при этому вас в распоряжении увеличительное стекло. Поднеся его крайне близко вы рассмотрите панцырь этого насекомого, удалив стекло далеко, вы ничего не рассмотрите и оно так и останется для вас неким насекомым.

Говоря об именовании, у нас происходит нечто подобное, мы также можем отдалять и приближать, или говоря другими словами, мы можем обобщать и конкретизировать понятие.

Например, мы хотим описать в нашем коде рептилию геккона, владельцы которого называют Петя:

```javascript
var animal;
var chord;
var scaly;
var reptile;
var gekko;
var petya;
```

Выше приведены способы именования по научной биологической классификации, упорядоченные по степени конкретизации. Но что же выбрать в качестве имени?

{% hint style="info" %}
Определитесь с вариантами возможного именования по степени обобщения, расположите их от общего к частному. Двигайтесь от частного к общему, отвечая на вопрос: присутствуют ли в коде сущности с таким же смыслом, когда ответ будет "нет", следующие общее имя будет именем переменной.
{% endhint %}

#### Применение правила

Возможно правило кажется запутанным, но на примере будет все понятно. Чтобы согласно правилу выше определиться с названием, нужно построить варианты именования по степени конкретизации, начиная с наиболее общих, благо ранее мы уже сделали это. 

Теперь двигаемся от частного к общему, начиная с "Пети", спрашивая себя, есть ли другие ящерицы, у которых есть собственное имя? Нету. Поэтому в качестве имени переменной берем следующие общее имя, тоесть `gekko`.

### Достаточность

// @TODO

Применение этого принципа продемонстрировано в разделе:

{% page-ref page="entities.md" %}

### Тождественность

{% hint style="info" %}
Если в коде описывается одна и та же сущность, но с разными именами, то эти имена есть одно и тоже, поэтому стоит использовать одно.
{% endhint %}

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

### Единообразие

// @TODO

### Соответствие названия содержанию

// @TODO

Применение этого принципа продемонстрировано в разделе:

{% page-ref page="functions.md" %}

### Единообразие

// @TODO







