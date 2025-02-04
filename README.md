# OpexViewer

Модуль UI для алготрейдинга и бектестирования роботов.


## Требования
```
node >= 17
```

## Установка

```
npm i opexviewer
```

## NPM

https://www.npmjs.com/package/opexviewer


## Описание

OpexViewer является составной частью [торговой системы](https://github.com/pskucherov/OpexBot).

На данный момент работает только с одним коннектором. Но спроектирован с возможностью подключения к другим торговым роботам. Общение однонаправлено и вьювер посылает запросы к серверу. При этом сервер ничего не знает про UI. Соответственно возможно подсунуть сервер с торговым роботом на любом языке и сервер может работать автономно без запущенного UI.

## Возможности

### Настройки
http://localhost:3000/settings

* Добавление адреса сервера. Например, разные сервера с торговыми роботами будут размещены в ДЦ рядом с биржей, а UI будет лежать отдельно для мониторинга.
* Добавление и выбор токенов.
* QR код для быстрого доступа с телефона (если вьювер запущен не на localhost).

<img src="https://user-images.githubusercontent.com/3197868/169752115-09a47fef-afd8-4dd1-9370-2f96ef538535.png" height="300">


### Выбор счёта
http://localhost:3000/accounts

* При выборе счёта отображается портфель, баланс и статус (только для чтения или нет).
* При использовании sandbox токена автоматически создаётся счёт и пополняется на 100 тысяч рублей.
* После выбора счёта в шапке всегда отображается баланс и номер счёта.

<img src="https://user-images.githubusercontent.com/3197868/169753145-291f2db2-efea-43de-8843-dd441fe95a70.png" height="300">


### Инструменты
http://localhost:3000/instruments

* На выбор предоставлены голубые фишки и их фьючерсы

<img src="https://user-images.githubusercontent.com/3197868/169770721-4ba1dac6-01bf-4052-9c7e-c5ea0aa3a21b.png" height="300">


### Страница инструмента
http://localhost:3000/instruments/BBG004730N88

### Торговля в реальном времени
* Содержит график с выбором таймфреймов (1, 5, 15 мин и 1 час), объём, стакан.
* Селект для выбора робота, кнопки старт стоп для запуска и остановки робота
* Настройки робота: лоты, TS / SL, уровни поддержки и сопротивления. Уровни так же дублируются на графике и в стакане.
* Робота можно запускать только на одном инструменте. Когда робот запущен перейти на другой инструмент нельзя.
* На график наносятся заявки и сделки. Оранжевым и салатовым цветом заявки, зелёным и красным сделки. Они же дублируются внизу страницы в текстовом виде.


<img src="https://user-images.githubusercontent.com/3197868/169771755-566f5b31-ff8f-4c29-ab80-0dd079e7d554.png" height="300"><img src="https://user-images.githubusercontent.com/3197868/169774076-135fceb7-1168-4642-8628-5fdb52a3dd8e.png" height="300">


Во время торговли можно посмотреть страницы логов и информацию для дебага.
В логах содержится информация про сервер и api. На [дебаг странице](http://localhost:8000/robots/debug) все переменные робота на текущий момент.

<img src="https://user-images.githubusercontent.com/3197868/169775548-311085fe-678e-4346-af88-6cab5d5ea8f0.png" height="300"><img src="https://user-images.githubusercontent.com/3197868/169775924-1a9b1c64-e793-402a-b5a3-fd8219e02da2.png" width="300">


### Бектестирование

Чтобы попасть в режим бектестирования нужно в календаре выбрать прошедшую дату, на которой нужно провести бектест.
Панель бектестирования ничем не отличается от реальной торговли, кроме того что есть контролы для пошаговой работы, чтобы отлаживать работу робота.

<img src="https://user-images.githubusercontent.com/3197868/169777663-3f4f1c24-ba0f-4377-82d9-fc6fc5143505.png" height="300">

<img src="https://user-images.githubusercontent.com/3197868/169780431-d669cdbb-958c-46f7-9688-024706eae13d.png" height="300">

Обратите внимание, что там где робот уже торговал, он автоматически закешировал стакан и теперь в бектестировании стакан доступен тоже.


## Мобильная версия

Вся описанная выше функциональность адаптирована для мобильных устройств. Для быстрого перехода добавлен QR код, который содержит в себе адрес сервера, чтобы повтоно не указывать с телефона. Под стаканом добавлена кнопка скрыть, чтобы график и кнопки поместились на экран.

<img src="https://user-images.githubusercontent.com/3197868/169783296-c7869335-c1c3-4723-85cf-56b61bc6e609.png" height="300"><img src="https://user-images.githubusercontent.com/3197868/169783391-a1d3f4b8-ea97-4f0d-9e76-b5b186a1493e.png" height="300"><img src="https://user-images.githubusercontent.com/3197868/169783438-540a054f-2c50-4f83-8aa8-613b7ab3520d.png" height="300"><img src="https://user-images.githubusercontent.com/3197868/169783473-53477359-653c-43f7-a9cd-533cd0bc1e6d.png" height="300"><img src="https://user-images.githubusercontent.com/3197868/169783503-0c12d1e0-bdc0-46ca-b2cb-52a18881f61f.png" height="300"><img src="https://user-images.githubusercontent.com/3197868/169783538-8da01a92-a85f-43dc-a27a-a1a27e96d612.png" height="300"><img src="https://user-images.githubusercontent.com/3197868/169783562-d5cc8998-61bd-43ee-86b7-0fff3b94665d.png" height="300"><img src="https://user-images.githubusercontent.com/3197868/169783592-68b74d11-df0d-4939-881a-21045b1f1377.png" height="300"><img src="https://user-images.githubusercontent.com/3197868/169783639-85e1d9f7-3a81-4be5-8d18-80c28117fef1.png" height="300">











