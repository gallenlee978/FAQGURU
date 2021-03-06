## JavaScript
 
  [Что такое принуждение в JavaScript?](#что-такое-принуждение-в-javascript)
 
  [Что такое оператор typeof?](#что-такое-оператор-typeof)
 
  [Что такое тип объекта?](#что-такое-тип-объекта)
 
  [Что такое массивы в JavaScript](#что-такое-массивы-в-javascript)
   
  [Что такое равенство в JavaScript](#что-равенство-в-javascript)

  [Что такое область видимости в JavaScript?](#что-такое-область видимости-в-javascript)

  [Что означает ключевое слово let в JavaScript?](#что-означает-ключевое-слово-let-в-javascript)

  [Что такое функция обратного вызова, и приведите простой пример.](#что-такое-функция-обратного-вызова-и-приведите-простой-пример)
  
  ### Что такое принуждение в JavaScript?
 
  В JavaScript преобразование между двумя разными встроенными типами называется `принуждение`.  Принуждение в JavaScript бывает двух типов: *явное* и *неявное*.
 
  Вот пример явного принуждения:
 ```js
 var a = "42";
 
 var b = Number( a );
 
 a;				// "42"
 b;				// 42 -- число!
 ```
 А вот пример неявного принуждения:
 ```js
 var a = "42";
 
 var b = a * 1;	// "42" неявно принуждено к 42
 
 a;				// "42"
 b;				// 42 -- число!
 ``` 
 
  
  
  [[↑] Вернуться к началу](#JavaScript)
 ### Что такое оператор typeof?
 
  JavaScript предоставляет оператор `typeof` который может проверить значение и сказать, какой это тип:
 ```js
 var a;
 typeof a;				// "undefined"
 
 a = "hello world";
 typeof a;				// "string"
 
 a = 42;
 typeof a;				// "number"
 
 a = true;
 typeof a;				// "boolean"
 
 a = null;
 typeof a;				// "object" -- странно, ошибка
 
 a = undefined;
 typeof a;				// "undefined"
 
 a = { b: "c" };
 typeof a;				// "object"
 ```
 
  
  
  
  [[↑] Вернуться к началу](#JavaScript)
 ### Что такое тип объекта?
 
  Тип объекта относится к составному значению, где вы можете установить свойства (именованные местоположения), каждое из которых содержит свои собственные значения любого типа. 
 
  ```js
 var obj = {
 	a: "hello world", // свойство
 	b: 42,
 	c: true
 };
 
 obj.a;		// "hello world", обращение через нотацию с точкой
 obj.b;		// 42
 obj.c;		// true
 
 obj["a"];	// "hello world", обращение через нотацию со скобками
 obj["b"];	// 42
 obj["c"];	// true
 ```
 Обращение через нотацию со скобками также полезно, если вы хотите получить доступ к свойству / ключу, но имя хранится в другой переменной, например как:
 ```js
 var obj = {
 	a: "hello world",
 	b: 42
 };
 
 var b = "a";
 
 obj[b];			// "hello world"
 obj["b"];		// 42
 ```
 
  
  
  [[↑] Вернуться к началу](#JavaScript)
 ### Что такое массивы в JavaScript
 
  `Массив` - это объект, который содержит значения (любого типа) не в именованных свойствах / ключах, а в числовых индексированных позициях:
 
  ```js
 var arr = [
 	"hello world",
 	42,
 	true
 ];
 
 arr[0];			// "hello world"
 arr[1];			// 42
 arr[2];			// true
 arr.length;		// 3
 
 typeof arr;		// "object"
 ```
 
  
  
  
  [[↑] Вернуться к началу](#JavaScript)
  ### Что такое равенство в JavaScript

JavaScript имеет как строгие сравнения, так и сравнения типов: 
* **Строгое сравнение (===)** проверяет равенство значений, не применяя *принуждение*
* **Абстрактное сравнение (==)** проверяет равенство значений применяя *принуждение*

```js
var a = "42";
var b = 42;

a == b;			// true
a === b;		// false
```
Некоторые простые равенства:
* Eсли какое-либо значение в сравнении может иметь значение `true` или `false`, избегайте `==` и используйте `===`.
* Если какое-либо значение в сравнении может иметь эти конкретные значения (`0`, `""`, или `[]` -- пустой массив), избегайте `==` и используйте `===`.
* Во всех остальных случаях вы можете безопасно использовать `==`. Это не только безопасно, но и во многих случаях упрощает ваш код с точки зрения читаемости.



[[↑] Вернуться к началу](#JavaScript)
### Что такое область видимости в JavaScript?

В JavaScript каждая функция получает свою собственную *область видимости*. Область видимости - это в основном набор переменных, а также правила доступа к этим переменным по имени. Только код внутри этой функции может получить доступ к переменным области видимости этой функции.

Имя переменной должно быть уникальным в той же области видимости. Область видимости может быть вложена в другую область. Если одна область вложена в другую, код внутри самой внутренней области может получить доступ к переменным из любой внешней области видимости.



[[↑] Вернуться к началу](#JavaScript)
### Что означает ключевое слово let в JavaScript?

В дополнение к созданию объявлений для переменных на уровне функций, ES6 позволяет объявлять переменные, принадлежащие отдельным блокам (парам { .. }), используя ключевое слово `let`. 

###### Источник

* https://github.com/getify/You-Dont-Know-JS/blob/master/up%20%26%20going/ch2.md

[[↑] Вернуться к началу](#JavaScript)
### Что такое функция обратного вызова, и приведите простой пример.

`callback` является функцией, которая передается другой функции в качестве аргумента и выполняется после завершения какой-либо операции. Ниже приведен пример простой функции обратного вызова, которая регистрируется в консоли *после* завершения некоторых операций.

```js
function modifyArray(arr, callback) {
  // делаем что-то с массивом
  arr.push(100);
  // затем выполнияем функцию обратного вызова, которая была передана
  callback();
}

var arr = [1, 2, 3, 4, 5];

modifyArray(arr, function() {
  console.log("массив был изменен", arr);
});
```

###### Источник

* https://coderbyte.com/algorithm/10-common-javascript-interview-questions

[[↑] Вернуться к началу](#JavaScript)
  
