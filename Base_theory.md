1. ТЕОРИЯ
   Теория. Типы данных
   JavaScript является языком программирования со слабой динамической типизацией. Это означает, что типы данных переменных могут меняться в процессе выполнения программы.

1. Числа (Numbers)
   В JavaScript числа могут быть целыми или дробными, положительными или отрицательными.

Примеры:

const age = 30;
const pi = 3.14; 2. Строки (Strings)
Строки представляют собой последовательность символов и заключаются в одинарные или двойные кавычки.

Примеры:

const name = 'John';
const message = "Hello, World!"; 3. Булевый тип (Boolean)
Булевый тип может принимать только два значения: true (истина) или false (ложь). Обычно используется для условных операций.

Примеры:

const isRaining = true;
const isLoggedIn = false; 4. Объекты (Objects)
Объекты - это сложные структуры данных, представляющие собой наборы пар "ключ-значение". Ключи - это строки (или символы), а значения могут быть любого типа данных, включая другие объекты.

Пример:

const person = {
name: 'Alice',
age: 25,
isAdmin: false
}; 5. Массивы (Arrays)
Массивы - это упорядоченные списки элементов, которые могут содержать различные типы данных.

Пример:

const numbers = [1, 2, 3, 4, 5];
const fruits = ['apple', 'banana', 'orange']; 6. Null и Undefined
null и undefined - это специальные значения, обозначающие отсутствие значения. null используется для явного указания на отсутствие значения, а undefined - когда значение не было присвоено.

Примеры:

let x = null;
let y; // не присвоено значение, по умолчанию будет undefined 7. Символы (Symbols)
Символы представляют собой уникальные и неизменяемые значения, которые могут использоваться как ключи для свойств объектов.

Пример:

const idSymbol = Symbol('id');
const user = {
[idSymbol]: 123,
name: 'Bob'
}; 8. Функции (Functions)
Функции - это подпрограммы, которые могут быть вызваны для выполнения определенной задачи. Они также являются объектами в JavaScript.

Пример:

function add(a, b) {
return a + b;
} 9. Особенности типизации
Оператор typeof позволяет определить тип переменной:

const name = 'John';
console.log(typeof name); // выводит 'string'
JavaScript имеет нестрогую типизацию, что позволяет выполнять операции между различными типами данных без явного преобразования.

Преобразование типов может быть явным (с помощью функций Number(), String(), Boolean()) и неявным (при использовании операторов, например, чисел и строк).

Это основы типов данных в JavaScript. Изучив эти типы, вы сможете эффективно работать с данными в своих программных проектах. Удачи!

Теория. Строки в JS
Строки представляют собой последовательность символов в JavaScript. Они являются неизменяемыми, что означает, что после создания строки ее нельзя изменить. В этой методичке мы рассмотрим основы работы со строками в JavaScript.

Создание строки
Строки в JavaScript можно создавать с помощью одинарных или двойных кавычек:

const singleQuotes = 'Это строка с одинарными кавычками.';
const doubleQuotes = "Это строка с двойными кавычками.";
Также можно использовать обратные кавычки для создания шаблонных строк (template literals) с вставкой значений переменных:

const name = 'John';
const age = 30;

const message = `Привет, меня зовут ${name} и мне ${age} лет.`;
console.log(message); // Выведет: "Привет, меня зовут John и мне 30 лет."
Экранирование символов
Если в строке нужно использовать специальные символы, их можно экранировать обратным слешем:

const text = 'Это "строка" с кавычками и символом \\';
Длина строки
Длину строки можно узнать с помощью свойства length:

const text = 'Пример строки';
console.log(text.length); // Выведет: 13
Доступ к символам
Символы в строке можно получить, используя индекс (начиная с 0):

const text = 'Hello';

console.log(text[0]); // Выведет: "H"
console.log(text.charAt(1)); // Выведет: "e"
Объединение строк
Строки можно объединять с помощью оператора +:

const firstName = 'John';
const lastName = 'Doe';

const fullName = firstName + ' ' + lastName;
console.log(fullName); // Выведет: "John Doe"
Также можно использовать шаблонные строки для объединения:

const firstName = 'John';
const lastName = 'Doe';

const fullName = `${firstName} ${lastName}`;
console.log(fullName); // Выведет: "John Doe"
Методы работы со строками
JavaScript предоставляет множество методов для работы со строками, таких как:

toUpperCase(): Преобразует строку к верхнему регистру.
toLowerCase(): Преобразует строку к нижнему регистру.
trim(): Удаляет начальные и конечные пробелы из строки.
substring(startIndex, endIndex): Возвращает подстроку с startIndex до endIndex (не включая endIndex).
indexOf(substring, startIndex): Возвращает индекс первого вхождения substring в строку, начиная с индекса startIndex. Если подстрока не найдена, возвращает -1.
lastIndexOf(substring, startIndex): Возвращает индекс последнего вхождения substring в строку, начиная с индекса startIndex. Если подстрока не найдена, возвращает -1.
split(separator): Разделяет строку на массив подстрок, используя separator как разделитель.
Замена подстроки
Для замены подстроки в строке можно использовать метод replace():

const text = 'Привет, мир!';
const newText = text.replace('мир', 'JavaScript');
console.log(newText); // Выведет: "Привет, JavaScript!"
Сравнение строк
Для сравнения строк можно использовать операторы сравнения (==, ===, !=, !==) или методы сравнения (localeCompare()):

const str1 = 'apple';
const str2 = 'banana';

console.log(str1 === str2); // Выведет: false
console.log(str1.localeCompare(str2)); // Выведет: -1

Теория. Функции в JS
Функции в JavaScript являются основными строительными блоками программы. Они позволяют группировать и повторно использовать код, делая код более организованным и удобным для работы.

Создание функции
Функции в JavaScript можно создавать с помощью следующих способов:

Функциональное выражение:
const add = function(a, b) {
return a + b;
};
Стрелочные функции (ES6+):
const add = (a, b) => a + b;
Использование ключевого слова function:
function add(a, b) {
return a + b;
}
Вызов функции
Вызов функции происходит с помощью ее имени и круглых скобок с аргументами (если они есть):

const sum = add(2, 3);
console.log(sum); // Выведет: 5
Аргументы функции
Функции могут принимать аргументы, которые используются внутри функции для выполнения операций:

function greet(name) {
console.log('Hello, ' + name + '!');
}

greet('Alice'); // Выведет: "Hello, Alice!"
greet('Bob'); // Выведет: "Hello, Bob!"
Возврат значения
Функции могут возвращать значения с помощью ключевого слова return:

function multiply(a, b) {
return a \* b;
}

const result = multiply(5, 3);
console.log(result); // Выведет: 15
Если в функции не указан оператор return, она вернет undefined.

Значения по умолчанию для аргументов
Функции могут иметь значения по умолчанию для аргументов:

function greet(name = 'Guest') {
console.log('Hello, ' + name + '!');
}

greet(); // Выведет: "Hello, Guest!"
greet('Alice'); // Выведет: "Hello, Alice!"
Функции как аргументы
Функции могут быть переданы как аргументы другим функциям:

function add(a, b) {
return a + b;
}

function subtract(a, b) {
return a - b;
}

function calculate(operation, a, b) {
return operation(a, b);
}

const sum = calculate(add, 5, 3);
console.log(sum); // Выведет: 8

const difference = calculate(subtract, 10, 5);
console.log(difference); // Выведет: 5
Замыкания (Closures)
Функции в JavaScript могут образовывать замыкания, позволяющие сохранять состояние между вызовами функции:

function counter() {
let count = 0;

return function() {
count++;
console.log(count);
};
}

const increment = counter();

increment(); // Выведет: 1
increment(); // Выведет: 2
increment(); // Выведет: 3
Анонимные функции
Анонимные функции - это функции без имени, которые можно присваивать переменным или использовать как аргументы других функций.

const add = function(a, b) {
return a + b;
};

const result = add(2, 3);
console.log(result); // Выведет: 5
Самовызывающиеся функции (Immediately Invoked Function Expressions, IIFE)
IIFE - это анонимные функции, которые вызываются сразу после объявления:

(function() {
console.log('Эта функция вызывается сразу после объявления.');
})();

Теория. Массивы в JS
Массивы - это упорядоченные коллекции элементов в JavaScript. Они могут содержать любые типы данных, включая числа, строки, объекты и другие массивы.

Создание массива
Существует несколько способов создания массивов в JavaScript:

С помощью литералов:
const array1 = []; // пустой массив
const array2 = [1, 2, 3]; // массив с элементами 1, 2 и 3
const array3 = ['apple', 'banana', 'orange']; // массив строк
С помощью конструктора Array():
const array4 = new Array(); // пустой массив
const array5 = new Array(1, 2, 3); // массив с элементами 1, 2 и 3
Основные методы работы с массивами

1. Добавление и удаление элементов
   push(element1, element2, ..., elementN): Добавляет один или несколько элементов в конец массива.
   pop(): Удаляет последний элемент из массива и возвращает его.
   unshift(element1, element2, ..., elementN): Добавляет один или несколько элементов в начало массива.
   shift(): Удаляет первый элемент из массива и возвращает его.
2. Доступ к элементам
   array[index]: Получение элемента по индексу. Индексы начинаются с 0.
   indexOf(element, startIndex): Возвращает индекс первого вхождения элемента в массиве, начиная с определенного индекса. Если элемент не найден, возвращает -1.
   lastIndexOf(element, startIndex): Возвращает индекс последнего вхождения элемента в массиве, начиная с определенного индекса. Если элемент не найден, возвращает -1.
3. Изменение массива
   splice(startIndex, deleteCount, item1, item2, ..., itemN): Изменяет содержимое массива, удаляя или заменяя существующие элементы и/или добавляя новые.
   slice(startIndex, endIndex): Возвращает новый массив, содержащий копию части исходного массива, начиная с startIndex и заканчивая endIndex (не включая элемент с этим индексом).
4. Объединение и разделение массивов
   concat(array1, array2, ..., arrayN): Объединяет два или более массивов.
   join(separator): Преобразует массив в строку, соединяя элементы с помощью разделителя separator.
5. Проверка и изменение размера массива
   length: Свойство массива, содержащее количество элементов в массиве. Может быть использовано для изменения размера массива.
6. Итерация по массиву
   forEach(callbackFunction): Выполняет указанную функцию callbackFunction один раз для каждого элемента массива.
   map(callbackFunction): Создает новый массив, содержащий результат вызова функции callbackFunction для каждого элемента исходного массива.
   filter(callbackFunction): Создает новый массив, содержащий только элементы, для которых функция callbackFunction возвращает true.
   reduce(callbackFunction, initialValue): Применяет функцию callbackFunction к аккумулятору и каждому значению массива слева направо для свертки массива в единое значение.
7. Проверка наличия элементов
   includes(element, startIndex): Проверяет, содержится ли элемент в массиве. Возвращает true, если элемент найден, и false в противном случае.
   some(callbackFunction): Проверяет, удовлетворяет ли хотя бы один элемент условию, заданному в функции callbackFunction. Возвращает true, если хотя бы один элемент проходит проверку, и false в противном случае.
   every(callbackFunction): Проверяет, удовлетворяют ли все элементы условию, заданному в функции callbackFunction. Возвращает true, если все элементы проходят проверку, и false в противном случае.
   Заключение
   Массивы предоставляют множество методов для удобной работы с элементами. Помните, что большинство методов, которые изменяют массив, возвращают измененную версию исходного массива, а не создают его копию. Если необходимо сохранить исходный массив, сначала создайте его копию с помощью метода slice().

Цикл for
const fruits = ['apple', 'banana', 'orange'];

for (let i = 0; i < fruits.length; i++) {
console.log(fruits[i]);
}

Цикл for...of
const fruits = ['apple', 'banana', 'orange'];

for (const fruit of fruits) {
console.log(fruit);
}

Метод forEach()
const fruits = ['apple', 'banana', 'orange'];

fruits.forEach(function(fruit) {
console.log(fruit);
});

Метод map()
const numbers = [1, 2, 3, 4, 5];

const squaredNumbers = numbers.map(function(number) {
return number \* number;
});

console.log(squaredNumbers); // Выведет: [1, 4, 9, 16, 25]

Метод filter()
const numbers = [1, 2, 3, 4, 5];

const evenNumbers = numbers.filter(function(number) {
return number % 2 === 0;
});

console.log(evenNumbers); // Выведет: [2, 4]

Метод reduce()
const numbers = [1, 2, 3, 4, 5];

const sum = numbers.reduce(function(accumulator, currentValue) {
return accumulator + currentValue;
}, 0);

console.log(sum); // Выведет: 15

Метод some() и every()
const numbers = [1, 2, 3, 4, 5];

const hasNegative = numbers.some(function(number) {
return number < 0;
});

const allPositive = numbers.every(function(number) {
return number > 0;
});

console.log(hasNegative); // Выведет: false
console.log(allPositive); // Выведет: true

Теория. Объекты в JS
Объекты в JavaScript представляют собой основной способ хранения и организации данных. Они позволяют создавать структуры с уникальными свойствами и методами.

Создание объекта
Существует несколько способов создания объектов в JavaScript:

Литеральная нотация:
const person = {
name: 'John',
age: 30,
isAdmin: true
};
Конструктор объекта:
const person = new Object();
person.name = 'John';
person.age = 30;
person.isAdmin = true;
С помощью функции-конструктора:
function Person(name, age, isAdmin) {
this.name = name;
this.age = age;
this.isAdmin = isAdmin;
}

const person = new Person('John', 30, true);
Доступ к свойствам объекта
Для доступа к свойствам объекта можно использовать два варианта синтаксиса:

Точечная нотация:
const name = person.name;
Квадратные скобки и строковый ключ:
const age = person['age'];
Изменение и добавление свойств
Свойства объекта можно изменять и добавлять в процессе выполнения программы:

const person = {
name: 'John',
age: 30
};

person.name = 'Alice'; // Изменение значения свойства
person.isAdmin = true; // Добавление нового свойства
Удаление свойств
Для удаления свойств объекта используется оператор delete:

const person = {
name: 'John',
age: 30
};

delete person.age; // Удаление свойства "age"
Методы объекта
Методы объекта - это функции, определенные в контексте объекта. Они могут использоваться для выполнения действий или операций с данными объекта:

const person = {
name: 'John',
age: 30,
greet: function() {
console.log('Hello, my name is ' + this.name + ' and I am ' + this.age + ' years old.');
}
};

person.greet(); // Выведет "Hello, my name is John and I am 30 years old."
Перебор свойств объекта
Для перебора свойств объекта можно использовать различные циклы или методы:

Цикл for...in:
const person = {
name: 'John',
age: 30,
isAdmin: true
};

for (let key in person) {
console.log(key + ': ' + person[key]);
}
Метод Object.keys():
const person = {
name: 'John',
age: 30,
isAdmin: true
};

const keys = Object.keys(person);
keys.forEach(key => {
console.log(key + ': ' + person[key]);
});
Вложенные объекты
Объекты могут содержать в себе другие объекты, создавая иерархические структуры данных:

const person = {
name: 'John',
age: 30,
address: {
city: 'New York',
zipCode: '10001'
}
};

console.log(person.address.city); // Выведет "New York"
