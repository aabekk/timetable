# Тестовое задание
## Расписание рейсов
**`Выполнено`** Разработать клиентское приложение(сайт), где будет табло аэропорта. У табло должны быть следующие функции:
+ просмотр только вылетающий рейсов
+ просмотр только прилетающих рейсов
+ просмотр задержанных рейсов
+ поиск по номеру рейса
    
#### Результат
+ Приложение показывает табо аэропорта.
+ Данные для табло берутся из локальных файлов, но получены из публичного API.
+ Реализован поиск по номеру борта среди отображаемых рейсов.
+ Ипользовалась библиотека *jQuery*

**[Страница приложения](https://scofield001.github.io)**
    
## Ticker
Почему this._i не увеличивается. Как исправить?
```js
function Ticker() {
    this._i = 0
};
Ticker.prototype = {
    tick: function() {
        console.log(this._i++);
    }
};
var ticker = new Ticker();
setInterval(ticker.tick, 1000);
```
#### Решение



