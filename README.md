## Qué es Node.js?

Node.js es un entorno de ejecución de JavaScript basado en el motor V8 de Google Chrome. Permite ejecutar código JavaScript en el lado del servidor, lo que facilita la creación de aplicaciones web y de red escalables y de alto rendimiento.

### Repasar el uso de JavaScript necesario para usar Node.js:

#### Lexical Structure

- **Expressions**: Las expresiones en JavaScript son fragmentos de código que producen un valor. Pueden ser simples, como `2 * 4`, o más complejas, como una llamada a función o una comparación.

    ```javascript
    2 * 4;
    ```

- **Data Types**: JavaScript tiene varios tipos de datos, incluyendo números, strings, booleanos, objetos, arrays, funciones, undefined, null y symbols.


    ```javascript
    let number = 10;
    let string = "Hola mundo";
    let boolean = false;
    let object = { key: "value" };
    function greet() {}
    let undefinedVar;
    let nullVar = null;
    let symbol = Symbol("unique");
    ```

- **Classes**: En JavaScript, las clases son una forma de definir objetos y su comportamiento utilizando una sintaxis orientada a objetos. Fueron introducidas en ES6 y proporcionan una manera más clara y sencilla de trabajar con herencia y prototipos.

    ```javascript
    class Person {
      constructor(name, age) {
        this.name = name;
        this.age = age;
      }
      greet() {
        console.log(`Hello, I'm ${this.name}`);
      }
    }

    const person1 = new Person("Alice", 25);
    person1.greet();
    ```

- **Variables**: Las variables se utilizan para almacenar valores en JavaScript. Pueden ser declaradas con las palabras clave `var`, `let`, o `const`, siendo `const` para valores que no cambian y `let` para variables que pueden cambiar de valor.

    ```javascript
    let x = 3;
    const y = 7;
    ```

- **Functions**: Las funciones son bloques de código que pueden ser llamados para realizar una tarea específica. Pueden ser definidas utilizando la palabra clave `function` o mediante funciones flecha (`=>`) en ES6.

    ```javascript
    function add(a, b) {
      return a + b;
    }

    const multiply = (a, b) => a * b;
    ```

- **this operator**: El operador `this` se refiere al objeto al que pertenece la función que está siendo ejecutada. Su valor depende de cómo se llama a la función y desde dónde se la llama.

    ```javascript
    const obj = {
      prop: "value",
      method() {
        console.log(this.prop);
      }
    };
    obj.method();
    ```

- **Arrow Functions**: Son una forma concisa de definir funciones en JavaScript, introducidas en ES6. Tienen una sintaxis más corta y un comportamiento diferente con respecto al valor de `this`.

    ```javascript
    const subtract = (a, b) => a - b;
    ```

- **Loops**: Los bucles (`for`, `while`, `do-while`) se utilizan para repetir una tarea hasta que se cumple una condición específica.

    ```javascript
    for (let i = 0; i < 3; i++) {
      console.log(i);
    }

    let j = 0;
    while (j < 3) {
      console.log(j);
      j++;
    }
    ```

- **Scopes**: El ámbito de una variable se refiere a dónde en el código puede ser accedida. JavaScript tiene ámbitos de función y ámbitos de bloque.

    ```javascript
    function outer() {
      let a = 5;
      console.log(a);
      function inner() {
        console.log(a);
      }
      inner();
    }
    outer();
    ```

- **Arrays**: Los arrays son estructuras de datos que permiten almacenar varios elementos bajo un solo nombre. Pueden contener cualquier tipo de datos y su longitud puede cambiar dinámicamente.

    ```javascript
    const array = [2, 4, 6, 8, 10];
    ```

- **Template Literals**: Son una forma de crear cadenas de texto más legibles y flexibles en JavaScript, introducidas en ES6. Permiten la interpolación de variables y expresiones dentro de cadenas de texto utilizando la sintaxis `${}`.

    ```javascript
    const name = "Alice";
    console.log(`Hello, my name is ${name}`);
    ```

- **Strict Mode**: Modo estricto es una forma de escribir código más seguro y eficiente en JavaScript. Se activa con la declaración `"use strict";`. Ayuda a evitar errores comunes y a hacer el código más optimizable para los motores de JavaScript.

    ```javascript
    "use strict";
    ```

- **ECMAScript 2015 (ES6) and beyond**: ES6 es una versión importante de JavaScript que introdujo muchas características nuevas, como clases, funciones flecha, let y const, entre otras. Desde entonces, nuevas versiones de ECMAScript han seguido introduciendo nuevas funcionalidades y mejoras al lenguaje.

    ```javascript
    class Animal {
      constructor(species) {
        this.species = species;
      }
      sound() {
        console.log(`I am a ${this.species}`);
      }
    }
    ```

### Define "Asynchronous Programming" y sus conceptos principales:

#### Asynchronous Programming and Callbacks

Las funciones asíncronas permiten que otras operaciones se ejecuten mientras se espera una tarea específica. Los callbacks son funciones que se pasan como argumentos a otras funciones y se llaman cuando se completa una tarea asíncrona. Son una forma común de manejar la asincronía en JavaScript.

```javascript
function doAsyncTask(callback) {
  setTimeout(function() {
    console.log("Asynchronous task completed");
    callback();
  }, 2000);
}

function callbackFunction() {
  console.log("Callback executed");
}

console.log("Starting asynchronous task...");
doAsyncTask(callbackFunction);
console.log("Asynchronous task in progress...");

