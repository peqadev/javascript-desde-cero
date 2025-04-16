# Parte II – Nivel Intermedio

## 15. Funciones anónimas y callbacks
### Funciones anónimas
```javascript
const saludar = function(nombre) {
    return `Hola, ${nombre}!`;
};

console.log(saludar("Juan")); // "Hola, Juan!"
```

### Callbacks
```javascript
function saludar(nombre, callback) {
    const mensaje = `Hola, ${nombre}!`;
    callback(mensaje);
}

saludar("Juan", function(mensaje) {
    console.log(mensaje); // "Hola, Juan!"
});
```

## 16. Async/Await y Fetch
### Async/Await
```javascript
async function obtenerUsuario(id) {
    const respuesta = await fetch(`https://api.github.com/users/${id}`);
    const usuario = await respuesta.json();
    return usuario;
}

obtenerUsuario(1).then(usuario => {
    console.log(usuario);
});

// or

const usuario = await obtenerUsuario(1);
console.log(usuario);
```

### Fetch
```javascript
fetch('https://api.github.com/users/octocat')
  .then(response => response.json()) // Convierte la respuesta a JSON
  .then(data => console.log(data)) // Maneja la respuesta
  .catch(error => console.error('Error:', error)); // Maneja errores
```

## 17. Estructuras avanzadas: Map y Set
### Map
```javascript
const mapa = new Map();
mapa.set('clave', 'valor');
console.log(mapa.get('clave')); // "valor"
```

### Set
Los Sets son colecciones de valores únicos.
```javascript
const conjunto = new Set();
conjunto.add('valor1');
conjunto.add('valor2');
console.log(conjunto.has('valor1')); // true
```

#### Comparación entre Map y Set
- Map:
  - Puede tener claves de cualquier tipo
  - Tiene métodos como `set`, `get`, `delete`, `has`
  - Puede tener valores duplicados
- Set:
  - Tiene métodos como `add`, `has`, `delete`
  - No puede tener valores duplicados
- Array:
  - Tiene métodos como `push`, `pop`, `shift`, `unshift`
  - Puede tener valores duplicados

## 18. Destructuring
### Destructuring de objetos
```javascript
const persona = {
    nombre: 'Juan',
    edad: 30,
    ciudad: 'Madrid'
};

const { nombre, edad, ciudad } = persona;
console.log(nombre, edad, ciudad); // "Juan" 30 "Madrid"
```

### Destructuring de arrays
```javascript
const numeros = [1, 2, 3, 4, 5];
const [primero, segundo, ...resto] = numeros;
console.log(primero, segundo, resto); // 1 2 [3, 4, 5]
```

## 19. Clases

### Definición de clases
```javascript
class Persona {
    constructor(nombre, edad) {
        this.nombre = nombre;
        this.edad = edad;
    }

    saludar() {
        return `Hola, mi nombre es ${this.nombre} y tengo ${this.edad} años.`;
    }
}

const persona = new Persona('Juan', 30);
console.log(persona.saludar()); // "Hola, mi nombre es Juan y tengo 30 años."
```

### Herencia
```javascript
class Persona {
    constructor(nombre, edad) {
        this.nombre = nombre;
        this.edad = edad;
    }

    saludar() {
        return `Hola, mi nombre es ${this.nombre} y tengo ${this.edad} años.`;
    }
}

class Empleado extends Persona {
    constructor(nombre, edad, cargo) {
        super(nombre, edad);
        this.cargo = cargo;
    }

    saludar() {
        return `Hola, mi nombre es ${this.nombre} y tengo ${this.edad} años. Soy ${this.cargo}.`;
    }
}

const empleado = new Empleado('Juan', 30, 'Desarrollador');
console.log(empleado.saludar()); // "Hola, mi nombre es Juan y tengo 30 años."
console.log(empleado.cargo); // "Desarrollador"
```

## 20. Módulos (ES6)
### Exportación de módulos
```javascript
export function saludar(nombre) {
    return `Hola, ${nombre}!`;
}
```

### Importación de módulos
```javascript
import { saludar } from './utils';

saludar('Juan'); // "Hola, Juan!"
```

### Exportación por defecto
```javascript
export default function saludar(nombre) {
    return `Hola, ${nombre}!`;
}
```

### Importación por defecto
```javascript
import saludar from './utils';

saludar('Juan'); // "Hola, Juan!"
```

### Importación dinámica
```javascript
// utils.js
export function saludar(nombre) {
    return `Hola, ${nombre}!`;
}

// main.js
import('./utils').then(module => {
    module.saludar('Juan'); // "Hola, Juan!"
});
```
