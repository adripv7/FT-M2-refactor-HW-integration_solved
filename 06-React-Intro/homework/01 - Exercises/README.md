# HW 06 - React-Intro | Ejercicios

## Duraci贸n estimada 馃晵

60 minutos

---

## Consigna de la homework

En esta homework, vamos a crear dos componentes de React, que nos ayudar谩n a entender mucho mejor c贸mo funciona esta grandiosa librer铆a 馃榾

> **Nota**: No te preocupes por el estilo de los componentes. En la siguiente clase y homework nos dedicaremos a ellos.

---

## Pasos b谩sicos para realizar la homework

馃敼 Para poder ejecutar los `test` de esta homework, es necesario que abramos la terminal ubicados dentro de la carpeta `01 - Exercises`.

-  Cuando te encuentres en esta carpeta, debes ejecutar el comando

```bash
npm install
```

-  Listo!! Ya puedes correr los test:

```bash
npm test
```

馃敼 Para poder correr la aplicaci贸n de forma local, s贸lo debes ejecutar el comando

```bash
npm start
```

-  Ingresando a <http://localhost:3000> desde el navegador, podremos ir viendo en tiempo real el resultado de nuestro trabajo.

---

### Conociendo la estructura

馃敼 Dentro de la carpeta `01 - Exercises`, vas a encontrar la siguiente estructura:

-  Una carpeta llamada **img**
-  Una carpeta llamada **public**
-  Una carpeta llamada `src` (Es la carpeta en donde trabajaremos)
-  Una carpeta llamada **tests**
-  Un archivo **package.json**
-  Y el archivo `README.md` que ahora mismo est谩s leyendo. 馃

Adem谩s:

馃敼 Dentro de la carpeta `src` vas a encontrar ya el esqueleto del proyecto React, estructurado de la siguiente manera:

-  Una carpeta llamada `components`
-  Un archivo llamado **App.js**
-  Un archivo **index.css**
-  Un archivo **index.js**

馃敼 Para estos ejercicios, trabajaremos s贸lo dentro la carpeta `components`. En principio s贸lo tenemos el componente `Bienvenido.jsx`.

---

## 馃懇鈥嶐煉? Ejercicio 1

### Nuestro primer componente funcional de React

馃敼 En el archivo `Bienvenido.jsx` encontrar谩s definida la funci贸n de un componente funcional de React. Dentro de ella aplicaremos la magia de React para combinar los temas vistos en clase.

馃敼 Lo que hay que hacer:

1. Que la funci贸n renderice un div.
2. Dentro de este div, crea la etiqueta correspondiente para un t铆tulo h1 (puedes colocar el texto que desees).
3. Encontrar谩s una constante de tipo string llamada `studentName`, as铆gnale un texto con tu nombre. Dicha constante debe ser renderizada dentro de un h3.
4. Encontrar谩s una constante llamada `techSkills` de tipo array, con 5 elementos. Los elementos de este arreglo deben renderizarse en una lista desordenada.

> Tip: para recorrer el arreglo y retonar elementos de acuerdo a su contenido, puedes usar el m茅todo `map`.

馃敼 Resultado esperado:

<p align="center"><img src="./img/01.png" height="300px" ></p>

---

## 馃懇鈥嶐煉? Ejercicio 2

馃敼 Lleg贸 la hora de crear tu primer componente desde cero

Ya sabemos c贸mo funciona un componente en React, ahora vamos a crear un componente desde cero, pero esta vez ser谩 un **_componente de clase_**.

馃敼 Lo que hay que hacer:

1. Crea un componente de clase llamado `Botones.jsx` (click derecho sobre la carpeta components --> Nuevo archivo --> `Botones.jsx`)
2. Importa React desde 'react'.
3. Crea la funci贸n de clase llamada `Botones`.
4. El componente debe renderizar un div.
5. Dentro del div, renderiza un bot贸n llamado "M贸dulo 1".
6. Dentro del div, renderiza un bot贸n llamado "M贸dulo 2".
7. Cada bot贸n debe tener el atributo `onClick` que muestre un `alert` con cualquier texto. Para esto, puedes copiar el siguiente c贸digo para que te familiarices con la funci贸n **alert**.

```javascript
    onClick={() => alert('Tu mensaje')}
```

**... Estamos llegando a la 煤ltima parte de la homework** 猸?

Ahora necesitamos conectar estos dos componentes, 驴C贸mo lo hacemos? Muy f谩cil!

1. Debes importar `Botones.jsx` dentro del componente `Bienvenido.jsx`
2. Debes renderizar `Botones.jsx`, como etiqueta en el componente `Bienvenido.jsx`
3. Dentro del componente `Bienvenido` debemos pasarle el objeto `alerts` como **_props_** al renderizar el componente `Botones`.
4. El componente `Botones.jsx` recibe por props del componente `Bienvenido.jsx` dicho objeto con dos propiedades: `m1` y `m2`. Estos ser谩n renderizados dentro del alert que dispara cada bot贸n.

馃敼 Resultado esperado:

<p align="center"><img src="./img/02.png" height="300px"></p>

<p align="center"><img src="./img/03.png" height="300px"></p>

---

## Recuerda que...

-  Todo en React es un componente y existen dos tipos: los componentes funcionales y los componentes de clase.
-  Un componente funcional es una funci贸n de Javascript que puede o no recibir datos (props). Tanto el nombre de la funci贸n como el nombre del archivo se deben llamar igual y deben ser con may煤scula inicial.
-  Un componente de clase es otra manera de definir un componente, la diferencia radica en que es con sintaxis de ES6.
-  Las props o propiedades son la manera que tiene React para pasar par谩metros de un componente padre a sus hijos.

---

## Recursos adicionales

-  Documentaci贸n **"Intro to React"** <https://reactjs.org/tutorial/tutorial.html>

---

Listo!! Ahora est谩s preparado para crear tu propia app!! 鉁煔?

Dir铆gete a la carpeta 馃搨 [**"02 - Integration"**](../02%20-%20Integration/README.md) y divi茅rtete desarrollando la app de Rick & Morty 馃ぉ
