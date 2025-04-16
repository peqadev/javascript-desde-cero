# Parte I – Nivel Introductorio

## 1. ¿Qué es JavaScript?
JavaScript es un lenguaje de programación que se ejecuta principalmente en navegadores web. Permite crear interactividad, controlar el contenido dinámico de las páginas y desarrollar tanto el frontend como el backend de aplicaciones web.

## 2. Variables: `let`, `const`, `var`
```javascript
let x = 10;
const y = 20;
var z = 30;

console.log(x, y, z); // 10 20 30
```

## 3. Tipos de datos
- `number`: números, como 1, 2.5, -3
- `string`: cadenas de texto, como "Hola", 'JavaScript'
- `boolean`: valores lógicos, como true, false
- `null`: valor nulo
- `undefined`: valor indefinid

## 4. Operadores básicos
- `+`: suma
- `-`: resta
- `*`: multiplicación
- `/`: división
- `%`: módulo
- `==`: igualdad
- `===`: igualdad estricta

## 5. Condicionales

### If
```javascript
if (x > 0) {
    console.log("x es positivo");
}
```

### Else
```javascript
if (x > 0) {
    console.log("x es positivo");
} else {
    console.log("x es negativo");
}
```

### Else If
```javascript
if (x > 0) {
    console.log("x es positivo");
} else if (x === 0) {
    console.log("x es cero");
} else {
    console.log("x es negativo");
}
```

### Switch
```javascript
switch (x) {
    case 0:
        console.log("x es cero");
        break;
    case 1:
        console.log("x es uno");
        break;
    default:
        console.log("x no es cero ni uno");
}
```

### Ternary
```javascript
const resultado = x > 0 ? "x es positivo" : "x es negativo";
console.log(resultado);
```

### And
```javascript
if (x > 0 && y > 0) {
    console.log("x e y son positivos");
}
```

### Or
```javascript
if (x > 0 || y > 0) {
    console.log("x o y es positivo");
}
```

### Not
```javascript
if (!x) {
    console.log("x es falso");
}
```

## 6. Bucles

### For
```javascript
for (let i = 0; i < 5; i++) {
    console.log(i); // 0 1 2 3 4
}
```

### While
```javascript
while (x > 0) {
    console.log(x); // 5 4 3 2 1
    x--;
}
```

### Do-While
```javascript
do {
    console.log(x); // 5 4 3 2 1
    x--;
} while (x > 0);
```

## 7. Funciones

### Function Declaration
```javascript
function saludar(nombre) {
    return "Hola, " + nombre;
}

saludar("Juan"); // "Hola, Juan"
```

### Arrow Function
```javascript
const saludar = (nombre) => "Hola, " + nombre;

saludar("Juan"); // "Hola, Juan"
```

### Named Function
```javascript
const saludar = function saludar(nombre) {
    return "Hola, " + nombre;
}

saludar("Juan"); // "Hola, Juan"
```

## 8. Objetos

### Object Literal
```javascript
const persona = {
    nombre: "Juan",
    edad: 30,
    ciudad: "Madrid"
};

console.log(persona); // { nombre: "Juan", edad: 30, ciudad: "Madrid" }
```

### Object Constructor
```javascript
const persona = new Object();
persona.nombre = "Juan";
persona.edad = 30;
persona.ciudad = "Madrid";

console.log(persona); // { nombre: "Juan", edad: 30, ciudad: "Madrid" }
```

### Object from JSON
```javascript
const persona = JSON.parse('{"nombre": "Juan", "edad": 30, "ciudad": "Madrid"}');

console.log(persona); // { nombre: "Juan", edad: 30, ciudad: "Madrid" }
```

## 9. Arrays

### Array Literal
```javascript
const numeros = [1, 2, 3, 4, 5];

console.log(numeros); // [1, 2, 3, 4, 5]
```

### Array Constructor
```javascript
const numeros = new Array(1, 2, 3, 4, 5);

console.log(numeros); // [1, 2, 3, 4, 5]
```

### Array from JSON
```javascript
const numeros = JSON.parse('[1, 2, 3, 4, 5]');

console.log(numeros); // [1, 2, 3, 4, 5]
```

### Array from Array
```javascript
const numeros = Array.from([1, 2, 3, 4, 5]);

console.log(numeros); // [1, 2, 3, 4, 5]
```

## 10. Sets

### Set Literal
```javascript
const numeros = new Set([1, 2, 3, 4, 5]);

console.log(numeros); // Set { 1, 2, 3, 4, 5 }
```

### Set from Array
```javascript
const numeros = new Set([1, 2, 3, 4, 5]);

console.log(numeros); // Set { 1, 2, 3, 4, 5 }
```

### Set from JSON
```javascript
const numeros = JSON.parse('[1, 2, 3, 4, 5]');

console.log(numeros); // Set { 1, 2, 3, 4, 5 }
```

## 11. Errores más comunes

### SyntaxError
```javascript
const x = 10;
console.log(x); // SyntaxError: Unexpected identifier
```

### ReferenceError
```javascript
console.log(x); // ReferenceError: x is not defined
```

### TypeError
```javascript
const x = 10;
x.toUpperCase(); // TypeError: x.toUpperCase is not a function
```

### RangeError - Maximum call stack size exceeded
```javascript
function factorial(n) {
    return n * factorial(n - 1);
}
factorial(-1); // RangeError: Maximum call stack size exceeded
```

### RangeError - Invalid array length
```javascript
const x = new Array(-1); // RangeError: Invalid array length
```

### Entre otros

## 12. Ejercicio práctico

### Ejercicio 1
Construir un programa que permita calcular el factorial de un número.

```javascript
function factorial(n) {
    return n * factorial(n - 1);
}
factorial(-1); // RangeError: Maximum call stack size exceeded
```


### Ejercicio 2
Construir una función que permita calcular el área de un triángulo.

```javascript
function areaTriangulo(base, altura) {
    return (base * altura) / 2;
}
areaTriangulo(10, 5); // 25
```

### Ejercicio 3
Construir una función que permita calcular el área de un círculo.

```javascript
function areaCirculo(radio) {
    return Math.PI * radio * radio;
}
areaCirculo(10); // 314.1592653589793
```

## 13. Manipulación básica del DOM

Para más información, referirse a la documentación oficial de MDN: https://developer.mozilla.org/es/docs/Web/API/Document_Object_Model

### Usando el DOM
```javascript
// Crear un nuevo elemento h1
const h1 = document.createElement("h1");
h1.textContent = "Hola, mundo";

// Agregar el nuevo elemento al body
document.body.appendChild(h1);
```

### Otros ejemplos
```javascript
// Agrega un listener de un botón que se crea en tiempo de ejecución
const boton = document.createElement("button");
boton.textContent = "Click me";
boton.addEventListener("click", () => {
    console.log("¡Hola!");
});
document.body.appendChild(boton);
```

## 14. Temporizadores (`setTimeout`, `setInterval`)
```javascript
// Ejecutar una función **después** de 1 segundo
setTimeout(() => {
    console.log("¡Hola!");
}, 1000);
```

```javascript
// Ejecutar una función **cada** 1 segundo
setInterval(() => {
    console.log("¡Hola!");
}, 1000);
```

## 15. JSON y almacenamiento local

### JSON
```javascript
const persona = JSON.parse('{"nombre": "Juan", "edad": 30, "ciudad": "Madrid"}');

console.log(persona); // { nombre: "Juan", edad: 30, ciudad: "Madrid" }
```

### Almacenamiento local
```javascript
localStorage.setItem("nombre", "Juan");

console.log(localStorage.getItem("nombre")); // "Juan"
```

### Almacenamiento session
```javascript
sessionStorage.setItem("nombre", "Juan");

console.log(sessionStorage.getItem("nombre")); // "Juan"
```
