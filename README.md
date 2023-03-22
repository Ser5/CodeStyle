# Стиль написания кода

## Основное - единичные сущности и наборы

Объект:<br>
`$item`

Запись (хэш, ассоциативный массив). Относящаяся к какой-либо сущности:<br>
`$itemData`

Массив объектов:<br>
`$itemsList`

Массив записей:<br>
`$itemsDataList`

Карта сущностей [ID => сущность]:<br>
`$itemsHash`

Карта с более точным указанием ключей и значений:<br>
`$itemIdToCodeHash`


## Идентификация сущностей

Числовой ID сущности:<br>
`$itemId`

Строковой ID сущности:<br>
`$itemCode`

Название сущности:<br>
`$itemName`


## Файлы

Объект файла:<br>
`$file`

Путь к файлу:<br>
`$filePath`

Объект конкретного файла:<br>
`$logsFile`

Путь к конкретному файлу:<br>
`$logsFilePath`


## Строки

Строка:<br>
`$commentString`

Строка с кодом html:<br>
`$commentHtml`


## Дата и время

Текущие дата и время в виде timestamp:<br>
`$nowTs = time();`

Текущие дата и время в виде строки:<br>
`$nowString = strtotime('Y-m-d H:<br>i:<br>s', $nowTs);`

Текущие дата и время в виде объекта:<br>
`$now = new \DateTime($nowTs);`


## Передача значений в функции

Функция, принимающая объект:<br>
`function foo ($item) {}`

Функция, принимающая запись с данными сущности:<br>
`function foo ($data) {}`

Функция, принимающая параметры/настройки, не относящиеся к какой-либо сущности:<br>
`function foo ($params) {}`


## Выборка сущностей через вызов функции

Выборка по ID осущности:<br>
`getItem($itemId);`

Выборка по неопределённому указанию на сущность - в виде ID, символьного кода, объекта итд:<br>
`getItem($item);`

Выборка по ID нескольких сущностей в виде массива:<br>
`getItemsList($itemIdsList);`

Выборка по ID нескольких сущностей - в произвольном виде: число, массив, строка итд:<br>
```php
function getItemsList ($itemIds) {}

getItemsList(1);
getItemsList([1, 2, 3]);
getItemsList('1,2,3');
```


## Функции-обработчики

Функция-обработчик:<br>
`function itemEditHandler ($data) {}`

Предобработчик:<br>
`function onBeforeItemEditHandler ($data) {}`

Постобработчик:<br>
`function onAfterItemEditHandler ($data) {}`


## CRUD

`function create ($data) {}`

`function edit ($id, $data) {}`

`function delete ($id) {}`

`function deleteList ($idsList) {}`

`function get ($params) {}`

`function getList ($params) {}`


## Краткая запись

Результат, кратко:<br>
`$r = getStuffFromDatabase();`

Переменная, использующаяся для обхода в цикле, кратко:<br>
```php
foreach ($itemsList as $e) {
	doSomething($e);
}
```

Переменные ключ-значение для обхода в цикле, кратко:<br>
```php
foreach ($params as $k => $v) {
	//...
}
```
