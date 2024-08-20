## ЗАДАЧА 1:

Создайте функцию, которая принимает массив URL и функцию fetch, и запускает все запросы параллельно,
но с ограниченным количеством одновременных запросов. Например, если вы запрашиваете 100 URL,
но у вас есть ограничение в 5 одновременных запросов, то ваша функция должна гарантировать,
что в любой момент времени не будет больше 5 одновременных запросов.

```js
var parallelPromisesWithLimit = async function (promisesArr, parallelLimit) {

};

const testURLs = [
  'https://jsonplaceholder.typicode.com/posts/1',
  'https://jsonplaceholder.typicode.com/posts/2',
  'https://jsonplaceholder.typicode.com/posts/3',
  'https://jsonplaceholder.typicode.com/posts/4',
  'https://jsonplaceholder.typicode.com/posts/5',
  'https://jsonplaceholder.typicode.com/posts/6',
  'https://jsonplaceholder.typicode.com/posts/7',
  'https://jsonplaceholder.typicode.com/posts/8',
  'https://jsonplaceholder.typicode.com/posts/9',
  'https://jsonplaceholder.typicode.com/posts/10',
];

function mockFetch(url) {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve(`Response from ${url}`);
    }, 1);
  });
}

async function test(time) {
  Запуск 5 одновременных запросов
  const results = await parallelPromisesWithLimit(testURLs.map((url) => () => mockFetch(url)), time);

  return results;
}

test();
```

# РЕШЕНИЕ

```js
async function parallelPromisesWithLimit(promisesArr, parallelLimit) {
const results = [];
const executing = [];
let index = 0;

async function executeNext() {
const currentIndex = index++;
if (currentIndex >= promisesArr.length) {
return; All promises have been executed
}

    const currentPromise = promisesArr[currentIndex];
    const promise = currentPromise();

    executing.push(promise);

    const result = await promise;
    results[currentIndex] = result;

    executing.splice(executing.indexOf(promise), 1);

    await executeNext();

}

const parallelExecutions = [];
for (let i = 0; i < parallelLimit; i++) {
parallelExecutions.push(executeNext());
}

await Promise.all(parallelExecutions);

return results;
}

const testURLs = [
'https://jsonplaceholder.typicode.com/posts/1',
'https://jsonplaceholder.typicode.com/posts/2',
'https://jsonplaceholder.typicode.com/posts/3',
'https://jsonplaceholder.typicode.com/posts/4',
'https://jsonplaceholder.typicode.com/posts/5',
'https://jsonplaceholder.typicode.com/posts/6',
'https://jsonplaceholder.typicode.com/posts/7',
'https://jsonplaceholder.typicode.com/posts/8',
'https://jsonplaceholder.typicode.com/posts/9',
'https://jsonplaceholder.typicode.com/posts/10',
];

function mockFetch(url) {
return new Promise((resolve) => {
setTimeout(() => {
resolve(`Response from ${url}`);
}, 1);
});
}

async function test(time) {
Запуск 5 одновременных запросов
const results = await parallelPromisesWithLimit(testURLs.map((url) => () => mockFetch(url)), time);

return results;
}

test(); Запуск
```

# ОБЪЯСНЕНИЕ

Код реализует функцию parallelPromisesWithLimit,
которая позволяет запускать асинхронные задачи (в данном случае, запросы к API) параллельно,
но с ограничением на количество одновременно выполняемых задач.

Пошагово:

Инициализация:
Создаются массивы results (для хранения результатов) и executing (для отслеживания выполняющихся обещаний).
Переменная index используется для отслеживания индекса следующего обещания в очереди.

executeNext():
Эта асинхронная функция запускает выполнение следующего обещания из promisesArr.
Она проверяет, остались ли еще обещания. Если нет, функция возвращает значение.
Получает текущее обещание из promisesArr и запускает его.
Добавляет это обещание в массив executing.
Ожидает завершения обещания, сохраняет результат в results.
Удаляет обещание из executing.
Рекурсивно вызывается сама себя, чтобы запустить выполнение следующего обещания.

Параллельное выполнение:
Создается массив parallelExecutions, куда добавляются вызовы executeNext() в количестве, равном parallelLimit.
Запускается Promise.all(parallelExecutions), которое ожидает завершения всех обещаний в parallelExecutions.

Возвращение результатов:
После завершения всех обещаний возвращается массив results, содержащий результаты выполнения всех обещаний в promisesArr.

Пример работы:
testURLs содержит список URL-адресов, к которым нужно сделать запросы.
mockFetch имитирует запрос к API, возвращая обещание, которое разрешается через 1 секунду.
test(time) запускает 5 одновременных запросов, используя parallelPromisesWithLimit с ограничением time.

Пример использования:
test(3); Запускает 5 запросов с ограничением 3 одновременных запроса.
Как работает ограничение:

parallelLimit определяет максимальное количество обещаний, которые могут выполняться одновременно.
executeNext() рекурсивно запускает следующее обещание только после завершения одного из текущих.
Это обеспечивает, что не будет превышен лимит параллельных запросов.

Преимущества:
Параллельное выполнение: Ускоряет выполнение задач.
Ограничение ресурсов: Предотвращает перегрузку сервера или других ресурсов.

Недостатки:
Сложность: Код может быть более сложным по сравнению с простом последовательным выполнением.
Проблемы с обработкой ошибок: Может потребоваться дополнительный код для обработки ошибок во время выполнения обещаний.

##ЗАДАЧА 2:
Реализуйте функцию runInOrder(functions, delays),
которая принимает массив функций и массив задержек,
и выполняет функции в указанном порядке с соответствующими задержками.

```js
function runInOrder(functions, delays) {
 Ваш код здесь
}


const functions = [() => console.log("first"), () => console.log("second"), () => console.log("third")];
const delays = [2000, 1000, 3000];

runInOrder(functions, delays); logs "first" after 2 seconds, "second" after another 1 second, and "third" after another 3 seconds
```

# РЕШЕНИЕ

```js
function runInOrder(functions, delays) {
    Проверяем, что длины массивов функций и задержек одинаковы
    if (functions.length !== delays.length) {
      throw new Error("Lengths of functions and delays arrays must be the same");
    }

    Вспомогательная функция для создания задержки
    function delay(ms) {
      return new Promise(resolve => setTimeout(resolve, ms));
    }

    Асинхронная функция для последовательного выполнения функций с задержкой
    async function executeFunctions() {
      for (let i = 0; i < functions.length; i++) {
        await delay(delays[i]); Ждем соответствующую задержку
        functions[i](); Выполняем функцию
      }
    }

    Запускаем асинхронную функцию
    executeFunctions();
  }

  Пример использования
  const functions = [
    () => console.log("first"),
    () => console.log("second"),
    () => console.log("third")
  ];
  const delays = [2000, 1000, 3000];

  runInOrder(functions, delays); Запуск

  //logs "first" after 2 seconds, "second" after another 1 second, and "third" after another 3 seconds
```

# ОБЪЯСНЕНИЕ:

Проверка длины массивов:
В начале функции runInOrder проверяем, что длины массивов functions и delays одинаковы. Если они не равны, выбрасываем ошибку.

Функция delay:
Это вспомогательная функция, которая возвращает промис, разрешающийся через указанное количество миллисекунд.

Асинхронная функция executeFunctions:
В этой функции мы используем цикл for, чтобы проходить по всем функциям в массиве.
Для каждой функции ждем соответствующую задержку с помощью await delay(delays[i]).
После задержки выполняем функцию из массива functions.

Запуск асинхронной функции:
В конце вызываем executeFunctions, чтобы начать последовательное выполнение функций.
Этот подход гарантирует, что функции будут выполнены в правильном порядке с указанными задержками.

Преимущества:
Простота реализации и понимания.
Легко читаемый и поддерживаемый код.
Полностью последовательное выполнение функций.

Подводные камни:
Невозможность отмены выполнения после начала.
Потенциальные проблемы с переполнением стека вызовов, если массивы очень большие (хотя это маловероятно в данном контексте).
Нужно использовать асинхронный синтаксис, что требует понимания Promises и async/await.

## ЗАДАЧА 3:

Реализуйте функцию asyncEvery(array, predicate), которая работает аналогично Array.prototype.every(), но с поддержкой асинхронных предикатов.

```js
var asyncEvery = async function (array, predicate) {};

function delay(ms) {
  return new Promise((resolve) => setTimeout(resolve, ms));
}
```

#РЕШЕНИЕ

```js
//Функция задержки для имитации асинхронных операций
function delay(ms) {
  return new Promise((resolve) => setTimeout(resolve, ms));
}

async function asyncEvery(array, predicate) {
  const results = await Promise.all(array.map(predicate));
  return results.every(Boolean);
}
```

# ОБЪЯСНЕНИЕ

1. Функция delay

```js
function delay(ms) {
  return new Promise((resolve) => setTimeout(resolve, ms));
}
```

Эта функция создает задержку на заданное количество миллисекунд. Она возвращает обещание (Promise),
которое разрешается после выполнения функции setTimeout через заданное время (ms).
Это полезно для имитации асинхронных операций, таких как сетевые запросы.

2. Функция asyncEvery

```js
async function asyncEvery(array, predicate) {
  const results = await Promise.all(array.map(predicate));
  return results.every(Boolean);
}
```

Эта функция асинхронно проверяет, удовлетворяют ли все элементы массива заданному предикату.
Вот как она работает:

Асинхронное выполнение предикатов:

```js
const results = await Promise.all(array.map(predicate));
```

Здесь array.map(predicate) создает новый массив обещаний, вызывая predicate для каждого элемента исходного массива.
Promise.all берет этот массив обещаний и возвращает новое обещание, которое разрешается, когда все переданные обещания выполнены.
Таким образом, results будет массивом значений, возвращенных предикатами.

Проверка результатов:

```js
return results.every(Boolean);
```

После выполнения всех предикатов, results содержит массив значений true или false.
Метод every проверяет, все ли элементы массива приводятся к true (что эквивалентно тому, что все предикаты вернули true).
Если хотя бы один элемент является false, метод every вернет false.

Пример использования

```js
async function example() {
  const array = [1, 2, 3, 4, 5];

  const predicate = async (num, index) => {
    await delay(50); Имитация асинхронной операции
    return num < 4;
  };

  const result = await asyncEvery(array, predicate);
  console.log(result); false, так как не все числа в массиве меньше 4
}

example();
```

Заданный массив: [1, 2, 3, 4, 5]
Предикат: асинхронная функция, которая задерживается на 50 миллисекунд и затем возвращает true,
если число меньше 4, и false в противном случае.
В данном примере, asyncEvery вызывает предикат для каждого элемента массива одновременно (параллельно).
После того, как все предикаты завершатся, results будет [true, true, true, false, false]. Метод every вернет false,
так как не все элементы массива меньше 4.

Преимущества данного подхода
Параллельное выполнение: Асинхронные операции выполняются параллельно, что может значительно ускорить процесс
по сравнению с последовательным выполнением.
Эффективность: Если асинхронные операции не зависят друг от друга, этот метод эффективно использует ресурсы системы.
Простота кода: Код легко читается и понимается, поскольку предикаты выполняются
с использованием стандартных методов массива (map и every).

## ЗАДАЧА 4:

Напишите функцию fetchData, которая симулирует асинхронный запрос данных.
Функция должна принимать два параметра: url и callback. fetchData должна возвращать промис,
который разрешается через 2 секунды с фиктивными данными, и затем вызывает функцию callback.

Необходимо вернуть data такого вида:

```js
const data = { result: "Some data receiasdasdved from " + url };

var fetchData = function (url, callback) {};
```

# РЕШЕНИЕ

```js
function fetchData(url, callback) {
    return new Promise((resolve, reject) => {
      Имитируем асинхронный запрос с помощью setTimeout
      setTimeout(() => {
        Фиктивные данные (можно изменить на реальные данные)
        const data = { result: 'Some data received from ' + url };

        Разрешаем промис, передавая данные
        resolve(data);

        Вызываем callback, передавая также данные
        if (typeof callback === 'function') {
          callback(data);
        }
      }, 2000); Имитация задержки 2 секунды
    });
}
```

# ОБЪЯСНЕНИЕ:

Создание промиса: return new Promise((resolve, reject) => { ... }); создает новый промис,
который представляет собой объект, обещающий выполнить определенное действие в будущем.

setTimeout: setTimeout(() => { ... }, 2000); устанавливает таймер,
который задерживает выполнение кода внутри него на 2000 миллисекунд (2 секунды).

Симуляция данных: const data = { result: 'Some data received from ' + url };
создает объект с фиктивными данными, которые “получены” с указанного URL.

Вызов callback: callback(data); вызывает функцию callback, переданную в качестве параметра,
с полученными данными. Это позволяет использовать fetchData для выполнения дополнительных действий после получения данных.

Разрешение промиса: resolve(data); разрешает промис, передавая полученные данные. Это означает,
что промис успешно выполнился, и теперь доступны данные.

Преимущества:
Асинхронность: fetchData использует промис и setTimeout, что позволяет ей работать асинхронно,
не блокируя выполнение других операций.
Обработка ошибок: Хотя в этом примере нет обработки ошибок,
промис позволяет легко обрабатывать ошибки с помощью reject.
Гибкость: fetchData принимает функцию callback,
что позволяет выполнять дополнительные действия после получения данных.

Недостатки:
Искусственная задержка: setTimeout в этом примере используется для симуляции задержки.
В реальном мире задержка может быть вызвана сетевыми запросами, которые могут иметь различную скорость.
Фиктивные данные: В этом примере данные являются фиктивными.
В реальном мире данные должны быть получены из реального источника (например, API).

## ЗАДАЧА 5

Реализуйте функцию delay(ms), которая возвращает промис,
разрешающийся через указанное количество миллисекунд.

```js
var delay = function (ms) {};

delay(3000).then(() => console.log("Runs after 3 seconds"));
```

# РЕШЕНИЕ

```js
var delay = function (ms) {
  return new Promise((resolve) => setTimeout(resolve, ms));
};
```

# ОБЪЯСНЕНИЕ

1. new Promise(resolve => ...): Создает новый промис. Промис - это объект,
   который представляет собой обещание выполнить определенное действие в будущем.

2. resolve: resolve - это функция, которая используется для разрешения промиса.
   Когда промис разрешается, он передает значение, которое было передано в resolve.

3. setTimeout(resolve, ms): Вызывает функцию setTimeout,
   которая задерживает выполнение функции resolve на ms миллисекунд.

4. resolve вызывается только после истечения указанного времени.

Преимущества:

- Асинхронность: delay использует setTimeout и промисы для создания задержки асинхронно,
  не блокируя выполнение других операций.
- Промисы: Возвращая промис, delay позволяет использовать стандартные методы промисов,
  такие как .then, .catch и .finally для обработки результатов и ошибок.
