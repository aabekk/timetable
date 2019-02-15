# Тестовое задание
## Расписание рейсов
**`Выполнено`**
Разработать клиентское приложение(сайт), где будет табло аэропорта. У табло должны быть следующие функции:
+ просмотр только вылетающий рейсов
+ просмотр только прилетающих рейсов
+ просмотр задержанных рейсов
+ поиск по номеру рейса
    
#### Результат
+ Приложение показывает табло аэропорта.
+ Данные для табло берутся из локальных файлов, но получены из публичного API.
+ Реализован поиск по номеру борта среди отображаемых рейсов.
+ Ипользовалась библиотека *jQuery*

**[Страница приложения](https://scofield001.github.io/timetable/)**
    
## Ticker
**`Выполнено`** Почему this._i не увеличивается. Как исправить?
```js
function Ticker() {
    this._i = 0
}
Ticker.prototype = {
    tick: function() {
        console.log(this._i++);
    }
};
var ticker = new Ticker();
setInterval(ticker.tick, 1000);
```
#### Ответ
`_i` не увеличивается, поскольку метод вызывается вне контекста его объявления. Для решения мы привязываем его к нужному контексту.
#### Варианты решения
1. Стрелочная функция «наследует» контекст той функции, в которой определена. Она не содержит собственный контекст this, а использует значение this окружающего контекста.
2. Метод bind() использовался до *ES6*. При вызове устанавливает в качестве контекста выполнения `this` предоставленное значение.
3. Поскольку мы именно вызываем функцию, то она сохраняет контекст. Но как написано в спецификации, такой способ рекомендуется избегать.

```js
'use strict';

function Ticker() {
    this._i = 0;
}

Ticker.prototype = {
    tick: function() {
        console.log(this._i++);
    }
};

// 1 способ: Стрелочная функция
let ticker2 = new Ticker();
setInterval(()=>ticker2.tick(), 1000);

// 2 способ: Метод bind
let ticker3 = new Ticker(),
    theTick = ticker3.tick.bind(ticker3);
setInterval(theTick, 1000);

// 3 способ: (не рекомендуемый)
let ticker = new Ticker();
setInterval("ticker.tick()", 1000);
```
