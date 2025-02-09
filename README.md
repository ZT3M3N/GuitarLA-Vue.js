# Vue 3 + Vite

Este primer proyecto fue para aprender las bases y fundamentos de Vue.js. El proyecto consistió en aprender vue haciendo un pequeño carrito de compras, con temática de guitarras. En la página principal se listan las guitarras que hay disponibles para su venta. Las guitarras cuentan con su nombre, una descripción y sus respectivos precios. Cada guitarra disponible se puede agregar al carrito, donde se almacenara la imagen, el nombre, el precio y se pueden modificar las cantidades que se quieran de una guitarra. También, se tiene la opción de quitar una guitarra del carrito o bien, vaciar completamente el carrito. Se desglosa el precio total a pagar y se calcula con base al precio de cada guitarra y su cantidad. El proyecto es meramente visual y no cuenta con un servidor BackEnd o BackEnd as a Service (BaaS) para guardar los datos porque los datos se almacenan en el Local Storage.

![GuitarLA-Vue-02-09-2025_12_10_AM](https://github.com/user-attachments/assets/a9b70332-0eef-423d-af36-09d444549686)

![GuitarLA-Vue-02-09-2025_12_12_AM](https://github.com/user-attachments/assets/97996113-3c3f-45c8-bacb-61fc017a7d87)



### ¿Qué es Vue.js? 

Vue es un framework progresivo de JavaScript, lo que significa que puede ser utilizado desde proyectos sencillos y simples hasta proyectos grandes. Vue es versátil, accesible y cuenta con un gran performance para crear interfaces de usuario para sitios/aplicaciones web.

Vue se basa en HTML, CSS Y JavaScript, además provve una síntaxis declarativa y basada en componentes.

### Ventajas de Vue.js

- Vue cuenta con una documentación sumamente completa. La documentación es accesible a través de su **[Documentación oficial](https://vuejs.org/guide/introduction.html)**.
- Debido a los pocos cambios que hay entre versiones, se asegura la compabilidad entre estas.

### ¿Qué se necesita para empezar a crear aplicaciones en Vue.js?

- Vite o el CLI de Vue.js
- Node (V. 14.18 o superior)
- Conocimientos sólidos en HTML, CSS y JavaScript (ES6+)

## Temas vistos en este primer proyecto, denominado "GuitarLA"

Como se ha mencionado, en este proyecto se vieron los fundamentos y el ecosistema de Vue.js. Se abarcaron los temas de:  

- Single File Components (SFC): Se refiere al HTML, CSS y JavaScript en un solo archivo. Vue utiza componentes y deben tener la extensión .vue; Un componente tiene dos propósitos, ser reutilizable o separar la funcionalidad. El SFC contiene las partes de <script>, <template> y <style>. En el <script> va toda la lógica y código de JavaScript, en <template> va todo lo relacionado al HTML y en <style> van los estilos con CSS.

- API Styles: Los componentes de Vue.js se pueden escribir en 2 API’s diferentes, en Options API y Composition API. Composition API es la forma recomendada para proyectos con Vue 3.

- Composition API: Se definen los componentes utilizando Imports. Composition API se define añadiendo setup al <script>.

- State y reactividad (con ref y con reactive, y solo en Composition API).

- State con Reactive: Reactive siempre es un objeto. Se accede con las propiedades de reactive con la síntaxis de punto (.).
  
- State con Ref: Ref permite trabajar con los tipos de datos de arreglos, booleanos, strings u objetos. Para acceder a las propiedades, se utiliza el **.value**.

- Directivas: Las directivas en Vue.js son atributos HTML con JavaScript. Las directivas siempre inician con v- y se colocan como atributos HTML (algunos ejemplos de estas son v-text, v-if, v-else, v-else-if, v-for, v-model, etc.). 

- Eventos: Son los eventos del DOM (click, submit, etc). Interactuar con ciertos eventos se hace con la directiva v-on.

- Tipo de evento inline handler: son para tareas muy sencillas, como cambiar a dark o light mode.

- Tipo de evento method handle: útiles para realizar diferentes acciones, como validar los datos de un formulario.

- Component Events: Eventos para componentes en Vue.js. Es la forma en la que los componentes comunican información entre sí. Básicamente, los componentes hijo pueden emitir eventos que los componentes padre pueden escuchar y reaccionar.

- Emits: Es el método que se usa en un componente hijo para disparar o emitir un evento.

- Props: Los props sirven para comunicar componentes. Los props pueden ser datos estáticos o reactivos. Si se quieren pasar funciones, es mejor utilizar un Component Event. Los props no deben modificar el state en el componente hijo.

- Computed properties: Forma de declarar propiedades que dependen de otras propiedades y se recalculan automáticamente cuando las propiedades de las que dependen cambian. 

- Watch: Es una forma de observar y reaccionar a los cambios en los datos de la instancia de Vue. Los watchers son útiles cuando se necesita realizar una acción específica en respuesta a los cambios de los datos, en lugar de simplemente recalcular un valor como harías con un computed property. Los watchers son especialmente útiles cuando se requiera realizar operaciones asíncronas, validaciones o cualquier otra lógica compleja en respuesta a cambios en los datos.

- Local Storage: Es una característica de las aplicaciones web que permite almacenar datos de forma persistente en el navegador del usuario. Esto significa que los datos guardados en local storage permanecerán allí incluso después de cerrar el navegador.

#### Con todos estos temas abarcados, se logró construir el proyecto web "GuitarLA". Los estilos están hechos con CSS, y manteniendo la responsividad utilizando media queries para que la aplicación se adapte a diferentes tamaños de pantallas. Cabe mencionar que los datos de las guitarras fueron introducidos en un archivo js para poder consultarlos y mostrar sus datos. Además, el proyecto se trató de hacer con código limpio, claro de entender y modularizado.

El proyecto se ha subido a internet por medio de Netlify, por lo cual se puede acceder a través de **[este link](https://adorable-macaron-cdb871.netlify.app/)**.

![GuitarLA-Vue-02-09-2025_12_07_AM](https://github.com/user-attachments/assets/f0fb3a52-aaed-45d2-a5e9-5e658468adc6)

