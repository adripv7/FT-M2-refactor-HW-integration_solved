# HW 09 - React-Routing | Integraci贸n

## Duraci贸n estimada 馃晵

x minutos

---

## Rick & Morty App

### Intro

Continuamos con nuestra Rick & Morty App. Utilizaremos React-Router-DOM el cual nos va a permitir enrutar nuestra SPA. Esto quiere decir que podremos decidir en que path o "link" se renderice cada componente.

Al finalizar, habremos creado tres rutas por las que podremos navegar:

-  **"/home"**: esta ser谩 la ruta del Home (vista principal/general).
-  **"/detail/:detailId"**: en esta ruta encontraremos informaci贸n m谩s detallada sobre el personaje en particular.
-  **"/about"**: en esta ruta colocar谩s tu nombre y describir谩s de qu茅 trata la aplicaci贸n Rick & Morty.

---

## Comencemos

Vamos a comenzar creando los componentes que nos faltan en nuestra carpeta components. Creamos `About.jsx` y `Detalle.jsx` con sus respectivos archivos. S贸lo los crearemos, a煤n no los construiremos. Tambi茅n creamos el archivo `.css` para el estilado. Recuerda que puedes utilizar cualquier formato de estilos (in-line, module, styled components, etc)

C贸mo sabemos, `react-router-dom` nos da la posibilidad de crear rutas din谩micas. Estas rutas ser谩n los path o links en el que se renderizar谩 el componente que nosotros decidamos. Para este ejercicio queremos que en cada link se vea lo siguiente:

-  `<Nav />` tiene que aparecer en todas las rutas.
-  `<Cards />` debe aparecer s贸lo en la ruta `/home`.
-  `<About />` debe aparecer s贸lo en la ruta `/about`.
-  `<Detail />` debe aparecer s贸lo en la ruta `/detail/:detailId`

---

### 馃懇鈥嶐煉? Ejercicio 1

### Instalar y configurar `react-router-dom`.

Instala `react-router-dom` desde la terminal. Importa y envuelve la aplicaci贸n con "**BrowserRouter**" en el archivo index.js.

Importa los elementos "**Routes**" y "**Route**", para que luego definamos las rutas en el archivo app.js.

---

### 馃懇鈥嶐煉? Ejercicio 2

### Mi perfil.

Ahora si construiremos el componente `<About />`. Este componente ser谩 una vista que contenga tu informaci贸n y una explicaci贸n de qu茅 se trata la aplicaci贸n!

Esto significa que es completamente libre. Puedes mostrar incluso una foto tuya. Esto le servir谩 a las personas que vean tu App para conocer al creador :D.

---

### 馃懇鈥嶐煉? Ejercicio 3

### Routing time!

En nuestro archivo "app.js" (aplicaci贸n), crea las rutas necesarias para que los componentes `<About />`, `<Cards />` y `<Nav />` se rendericen en sus links correspondientes. Recuerda que en el **EJERCICIO 1** ya est谩n especificadas las rutas.

Respecto al componente `<Detail />`, su ruta recibir谩 el par谩metro **id**, por lo que debes asegurarte de escribir bien el path de esta ruta.

> **Nota:** Comprueba en tu navegador que los links rendericen el componente correcto, y que el componente `<Nav />` se vea siempre.

---

### 馃懇鈥嶐煉? Ejercicio 4

### Detail redirection.

Ahora nuestra SPA cuenta con tres rutas distintas: "`/home`", "`/detail/:detailId`" y "`/about`".

Para este ejercicio:

1. En el componente `<Card />` importa y envuelve el nombre del personaje con el elemento "**Link**". Tiene que redirigirnos a la ruta de cada personaje.
2. A este componente deber谩s pasarle por **props** el "**id**" del personaje para usarlo en el Link.

```js
// Card.js
...
<Link to={`/detail/${id}`} >
  <h5 className="card-title">{name}</h5>
</Link>
...
```

---

### 馃懇鈥嶐煉? Ejercicio 5

### Construcci贸n del Detail.

隆Genial! Cuando hacemos click sobre el nombre en una Card esta nos redirige a la ruta con el ID del personaje. Ahora necesitamos crear el componente que mostrar谩 toda la informaci贸n del personaje.

Para obtener esta informaci贸n importa los hooks **useState** de `react` y **useParams** de `react-router-dom` en el componente `<Detail />`.

1. Primero obten el ID del personaje mediante **useParams**.

2. Crea un estado local con el nombre **character**.

3. En este paso importaremos el hook **useEffect** de `react`. Una vez importado, copia el siguiente c贸digo y p茅galo en el cuerpo del componente.

```js
useEffect(() => {
   fetch(`https://rickandmortyapi.com/api/character/${id}`)
      .then((response) => response.json())
      .then((char) => {
         if (char.name) {
            setCharacter(char);
         } else {
            window.alert('No hay personajes con ese ID');
         }
      })
      .catch((err) => {
         window.alert('No hay personajes con ese ID');
      });
   return setCharacter({});
}, [id]);
```

> **NOTA:** Este c贸digo es el que buscar谩 al personaje de la API cada vez que el componente se monte. Y luego, cada vez que se desmonte, borrar谩 su informaci贸n.

---

### 馃懇鈥嶐煉? Ejercicio 6

Ahora en tu estado local **character** tendr谩s toda la informaci贸n del personaje disponible para que la renderices en este componente (`<Detail />`).

D谩ndole estilos deber铆a quedarte algo similar a esto:

<img src="./img/final_detail.png" width='800px'/>

---

### 馃懇鈥嶐煉? Ejercicio 7

Crea un bot贸n en el componente `<Detail />` que te permita regresar a "`/home`".

---

### 馃懇鈥嶐煉? EXTRA CREDIT

Ahora te desafiamos a que crees un nuevo componente llamado **Error**. A este componente le podr谩s dar los estilos que quieras, pero la idea es que se muestre un mensaje de error 404.

Pueden inspirarte en el siguiente link: "https://github.com/errroorrxd".

El desaf铆o es. Haz que este componente se muestre cada vez que el usuario ingrese a cualquier otra ruta que no exista. Es decir que no la hayas especificado en esta homework. Por ejemplo, si creaste una ruta "`/home`" y "`/about`", y el usuario en el navegador escribe y "`/henry`", deber铆a mostrar el error 404.
