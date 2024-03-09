# LABORATORIO 5 - SPRING MVC INTRODUCTION

### INTRODUCCIÓN A PROYECTOS WEB

## PARTE I. - JUGANDO A SER UN CLIENTE HTTP

Usaremos las siguientes aplicaciones como cliente HTTP

Postman
Telnet
Abre la aplicación Postman, lo usaremos para hacer una solicitud a un servidor HTTP, al abrirlo indentifica qué controles de Postman corresponde a los elementos de entrada y salida de un servicio HTTP:

![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/905626a7-5369-4775-9ef7-dcb0af95e0a8)

### Postman

Has un request GET a la URL https://www.escuelaing.edu.co/es/ y verifica el body de respuesta en las opciones Pretty, Raw, Preview.

- Hacemos el get de https://www.escuelaing.edu.co/es/
  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/540992bf-8270-451f-8f6c-202e5516acb8)

- Verificamos el body de respuesta en la opción "Pretty"
  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/5db60fce-7b52-4629-8cd3-61817c9a6be3)

- Verificamos el body de respuesta en la opción "Raw"
  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/34848706-ecfe-47e3-86e0-2fdf63b56a1e)

- Verificamos el body de respuesta en la opción "Preview"
  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/0a8deb3b-4608-47a2-b9aa-3b848bec21e9)


Ahora has otro request GET al recurso https://dummyjson.com/todos, nuevamente verifica el body en varias opciones.

- Hacemos el get de https://dummyjson.com/todos
  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/f8fdab9f-47cd-480f-be9e-b745c62bfebf)

- Verificamos el body de respuesta en la opción "Pretty"
  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/a0c35fa6-5611-4b09-a50a-18e4e20dc71d)

- Verificamos el body de respuesta en la opción "Raw"
  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/5c635159-5341-40f8-bc62-9694c0ea33a8)

- Verificamos el body de respuesta en la opción "Preview"
  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/68c164a8-640d-4ced-aa36-971d34362a4e)


Responde las siguientes preguntas:

- ¿Qué pasa si no envío el método correcto?
  
  Si no envías el método HTTP correcto (por ejemplo, envías un método no permitido como GET en lugar de POST), el servidor responderá con un código de estado 405 Method Not Allowed indicando que el método utilizado no está permitido para el recurso solicitado.

- ¿Qué pasa si al body response HTML lo fuerzo a leerse como JSON?

  Si fuerzas al body response HTML a ser leído como JSON, el navegador o la herramienta que estés utilizando para leer la respuesta probablemente te mostrará un error indicando que no se puede interpretar el contenido como JSON, ya que el formato no coincide.

- ¿Por qué el preview de HTML no se ve igual a cuando accedo a la URL en un navegador web?

  El preview de HTML puede no verse igual que cuando accedes a la URL en un navegador web debido a varias razones:

  Algunas herramientas de visualización de HTML no interpretan correctamente todos los estilos CSS o JavaScript asociados con la página web, lo que puede afectar la apariencia.
  Los navegadores web suelen tener diferentes motores de renderizado y ajustes de visualización, lo que puede resultar en diferencias en la apariencia de la página.
  El preview puede mostrar una versión simplificada o sin formato de la página, mientras que los navegadores web suelen aplicar estilos y scripts para mejorar la experiencia de usuario.

  
- ¿Qué pasa si le envías un body a una solicitud GET?

  En general, el método GET no incluye un body en la solicitud, ya que está diseñado para recuperar recursos del servidor sin enviar datos en el cuerpo de la solicitud. Si envías un body con una solicitud GET, es posible que algunos servidores lo ignoren, mientras que otros pueden responder con un error como "400 Bad Request" indicando que la solicitud es incorrecta. El uso de un body en una solicitud GET no es estándar y puede considerarse una mala práctica en términos de diseño RESTful y HTTP.

### Telnet 

Como parte del laboratorio en casa has los dos request anteriores pero ahora usando la herramienta Telnet, ya que esta no funciona adecuadamente en los equipos del laboratorio.

- Activamos el cliente Telnet en las características de Windows:
  
  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/c26ecc99-65f6-4b63-80b7-42c1bac29d44)

- Escribimos la siguiente línea:

  telnet www.escuelaing.edu.co 80

- Una vez adentro en Telnet, escribimos:

  GET /es/ HTTP/1.1
  
  Host: www.escuelaing.edu.co

  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/08d21f9c-de36-4e6c-9da6-dcc54bd979b4)

-  ¿Qué significa la respuesta 301 cuándo usas telnet en el puerto 80?.

    telnet soporta HTTP y no HTTPS, si se intenta enviar texto plano al 443 cierra la conexión, y si se usa el puerto 80, redirecciona al recurso HTTPs(sale un mensaje de tipo 30x que significa redirección, como se puede ver en la captura)
  
    El código de estado HTTP 301 significa "Movido permanentemente". Cuando se realiza una solicitud HTTP a un servidor web y se recibe una respuesta con el código de estado 301, indica que el recurso      solicitado ha sido movido permanentemente a una nueva ubicación. La nueva ubicación se especifica en el encabezado Location de la respuesta.


  Como telnet no soporta HTTPS(no soporta la de la página de la escuela, ni la de dummyjson), haremos la prueba con example.com

- Escribimos la siguiente línea:
  
  telnet example.com 80

- Una vez adentro en Telnet, escribimos:

  GET / HTTP/1.1
  
  Host: example.com

- De esta forma, obtenemos el recurso:

  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/3246c6f3-61d8-4d64-ae0a-51fa3b6a7453)

## PARTE II. - CLIENT SIDE RENDERING CON REACT

Para iniciar verifica que tengas alguna de estas herramientas:
- NPM o YARN
Verificando en terminal sería $ npm --version

![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/d3458706-0d02-48b4-8d66-0653cb6c0eeb)

La siguiente misión es ejecutar una aplicación react localmente:

- Abre la aplicación https://codesandbox.io/s/react-js-simple-calculator-pefmr, loguéate con GitHub y juega cambiando los parámetros como colores y duplicando las líneas del archivo App.js con tags como <ResultComponent ...> en la función render.

  - Cambiando colores:
    ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/45e2187a-920e-4b64-b3d0-db359d0f17db)

  - Duplicando las líneas del archivo App.js

    ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/c14b9609-5a38-4051-a86e-35c1eddb7ed6)


- ¿Qué hace cada uno de los archivos en la aplicación?

  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/b43d4ba3-94cd-4c47-906d-572d32f429e4)

  - package.json: Este archivo define las dependencias del proyecto, incluyendo las versiones de React y React-DOM utilizadas, así como los scripts para iniciar el servidor de desarrollo, construir el proyecto y ejecutar pruebas.

  -  public/index.html: Este archivo HTML es la plantilla base de la aplicación React. Contiene un div con el ID "root" donde se renderiza la aplicación React.
  
  - src/App.js: Este archivo contiene el componente principal de la aplicación (App). Define la lógica para la calculadora, incluyendo cómo se manejan los clics en los botones, cómo se realizan los cálculos, cómo se muestra el resultado y cómo se actualiza el estado de la aplicación.
  
  - src/components/KeyPadComponent.js: Este archivo contiene el componente KeyPadComponent, que define los botones de la calculadora. Cada botón tiene un evento onClick que llama a la función onClick definida en el componente principal (App) cuando se hace clic en él.
  
  - src/components/ResultComponent.js: Este archivo contiene el componente ResultComponent, que muestra el resultado de los cálculos realizados en la calculadora.
  
  - src/index.js: Este archivo es el punto de entrada de la aplicación React. Aquí se importa el componente App y se renderiza en el elemento con el ID "root" del archivo HTML principal.
  
  - src/styles.css: Este archivo contiene estilos CSS para la aplicación, incluyendo el diseño de la calculadora, los estilos de los botones y el resultado.

- Después de haber visto los cambios, vuelve a abrir la URL original https://codesandbox.io/s/react-js-simple-calculator-pefmr y sigue los siguientes pasos:

1. Descargar código en un Zip
2. Descomprimir el Zip en la carpeta de proyectos de software, (en ciertos PC solo funciona 7-Zip)
3. Abrir una terminal de Git Bash en la carpeta descomprimida
4. Instalar las dependencias con npm install

    ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/9924430c-0c0f-4ab4-af58-0462c5f1eb1c)

    ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/b2eaabbc-7f20-468f-88ba-2ae97f4e0289)


5. Iniciar la aplicación con npm start, en algunos computadores con versiones antiguas de nodejs hay que agregar NODE_OPTIONS=--openssl-legacy-provider npm run start

   Utilzamos 'NODE_OPTIONS=--openssl-legacy-provider npm run start' ya que no funciona solo con npm start

    ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/541d178c-a72b-4c79-b02c-088688bdb058)

7. Si te sale el Firewall dale click en cancelar
8. Abrir la ruta http://localhost:3000/ en un navegador web como Firefox o Google Chrome

   ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/537164b4-3aee-4864-a938-6798978ef9e6)

- Ahora, has el request GET http://localhost:3000/ usando Postman, y revisa si el body de la respuesta es igual a alguno de los archivos del proyecto. 

  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/f2cc6c13-cbbf-4a99-bcbd-1c5625d7b70f)

  Efectivamente, el body es igual al archivo index.html del proyeto

  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/8e0a63b1-d903-4788-8584-b5d071d7121a)

- Significa eso que es un recurso web dinámico o estático?

  Se encontró que el cuerpo de la respuesta es idéntico al contenido del archivo HTML, esto sugiere que el recurso es estático. Un recurso web estático es aquel cuyo contenido no cambia dinámicamente   en función de la solicitud del cliente o de factores internos del servidor. En otras palabras, el servidor está enviando un archivo estático tal como está almacenado en el sistema de archivos del servidor, sin procesamiento adicional.

## PARTE III. - HACIENDO UNA APLICACIÓN WEB DINÁMICA USANDO EL PATRÓN MVC

En este ejercicio, va a implementar una aplicación Web muy básica, haciendo uso de spring MVC.

Para esto usaremos la documentación oficial de Spring con que que aprenderemos las funciones básicas de este framework https://spring.io/guides/gs/serving-web-content/

- Clonamos el repositorio

  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/42978ab4-bcbd-4fc7-aede-a160f0be4721)

- Abrimos el proyecto en gs-serving-web-content/initial, escogemos mvn
  
  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/477c0778-8211-446d-928a-8a3ff1d580b7)

- Creamos un GreetingController en la siguiente ubicación 'src/main/java/com/example/servingwebcontent/GreetingController.java'

  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/9eb6ef69-2328-4498-80a8-dc2bafc5aa3f)

- Añadimos un html 'greeting.html' en la siguiente ubicación src/main/resources/templates/greeting.html

  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/be64715a-0424-4595-a9ec-0f3de29296bb)

- Ahora corremos el servicio desde git bash con el siguiente comando

  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/57665dee-cad0-49e4-81c6-afd1c693901d)

- Verificamos que el servicio esté funcionando

  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/863bd577-8250-4c25-b6a0-082add10accf)

- También podemos generar un jar con el comando ./mvnw clean package

  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/0c16aeab-e2f7-4791-bc56-6abd1365ca16)

  Para correrlo usamos: 'java -jar target/gs-serving-web-content-0.1.0.jar'

- Probamos la aplicación dando un parámetro de nombre 'http://localhost:8080/greeting?name=Nat'

  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/bb02a4dd-b865-49e7-a21b-0dfbe8fd1dff)

- Ahora agregamos una home page añadimos un 'index.html' en la ubicación src/main/resources/static/index.html

  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/4c99a7ed-c7ea-42a3-9cb3-f96a884ab086)

  - Probamos el home page
    
    ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/1038a9e4-042e-42ac-ba10-35edf9afd325)

    ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/81c88b51-389d-4a43-8a54-3fc89d5368aa)


Después de terminar el aprendizaje analice:

- ¿Por qué MVC obtiene ese nombre? (puede apoyarse de https://www.javatpoint.com/spring-mvc-tutorial)

  El patrón de diseño MVC (Modelo-Vista-Controlador) obtiene su nombre debido a la división de las responsabilidades en tres componentes principales:

  - Modelo (Model): Representa los datos y la lógica de negocio de la aplicación. Es el encargado de gestionar y manipular los datos, así como de realizar las operaciones relacionadas con la lógica de negocio. El modelo no se preocupa por la forma en que los datos se presentan al usuario ni por cómo se interactúa con ellos.
  
  - Vista (View): Es la interfaz de usuario que presenta los datos al usuario final. Se encarga de mostrar la información de manera visual y de proporcionar una interfaz a través de la cual el usuario puede interactuar con la aplicación. La vista no realiza ningún procesamiento de datos ni contiene lógica de negocio.
  
  - Controlador (Controller): Actúa como intermediario entre el modelo y la vista. Gestiona las solicitudes del usuario, procesa la entrada del usuario y coordina la interacción entre el modelo y la vista. El controlador decide qué vista mostrar al usuario en función de la acción realizada y los datos proporcionados por el modelo.

- ¿Cuáles son las ventajas de usar MVC?

  1. Separación clara de responsabilidades: Spring MVC separa claramente los roles de cada componente, como el modelo, el controlador, el resolver de vistas, entre otros, lo que facilita el desarrollo y mantenimiento del código.
  2. Ligero: Utiliza un contenedor de servlets ligero, lo que lo hace adecuado para desarrollar y desplegar aplicaciones de manera eficiente.
  3. Configuración poderosa: Ofrece una configuración robusta tanto para el framework como para las clases de la aplicación, lo que permite una fácil referencia entre los controladores web, objetos de negocio y validadores.
  4. Desarrollo rápido: Facilita un desarrollo rápido y paralelo, lo que permite una implementación eficiente de nuevas características y cambios.
  5. Código de negocio reutilizable: Permite la reutilización de código de negocio existente en lugar de crear nuevos objetos, lo que mejora la eficiencia del desarrollo.
  6. Fácil de probar: Proporciona clases JavaBeans que facilitan la inyección de datos de prueba, lo que simplifica la realización de pruebas unitarias y de integración.
  7. Mapeo flexible: Ofrece anotaciones específicas que permiten un mapeo flexible y fácil redireccionamiento de páginas.
  
- ¿Qué diferencia tiene la estructura de directorios de este proyecto comparado con las de proyectos pasados (con solo maven y java EE)?

  Estructura de directorios en un proyecto MVC de Spring:
    
    - src/main/java: Contiene el código fuente Java de la aplicación, incluyendo los controladores, modelos y servicios.
    - src/main/resources: Contiene archivos de recursos, como archivos de configuración XML de Spring, archivos de propiedades, archivos de configuración de base de datos, etc.
    - src/main/webapp: Contiene los recursos web estáticos, como archivos HTML, CSS, JavaScript, imágenes, etc.
    - src/test: Contiene las pruebas unitarias y de integración de la aplicación.
    - pom.xml: El archivo POM (Project Object Model) de Maven que define la configuración del proyecto y las dependencias.
      
  Proyectos anteriores (solo Maven y Java EE):
    
    - src/main: Esta carpeta contiene los archivos fuente de la aplicación Java, incluidos los paquetes de código fuente, recursos estáticos (como archivos HTML, CSS, JavaScript), y archivos de configuración de la aplicación (como web.xml en aplicaciones Java EE).
    - src/test: Esta carpeta contiene los archivos de prueba de la aplicación Java.
    - pom.xml: Este archivo define la configuración del proyecto Maven, incluidas las dependencias del proyecto, las configuraciones del complemento Maven, etc.

- ¿Qué anotaciones usaste y cuál es la diferencia entre ellas?

  - @Controller:

    Esta anotación se utiliza para marcar una clase como un controlador de Spring MVC. Indica que la clase define métodos de manejo de solicitudes HTTP y puede devolver una vista o un objeto JSON como respuesta.
  
  - @GetMapping:
  
    Esta anotación se utiliza para mapear las solicitudes HTTP GET a métodos de controlador específicos. Es una abreviatura de las anotaciones @RequestMapping(method = RequestMethod.GET) y se utiliza para indicar que el método anotado manejará las solicitudes GET en la URL especificada.

  - @RequestParam:
  
    Esta anotación se utiliza para vincular los parámetros de una solicitud HTTP a los parámetros de un método del controlador. Puede utilizarse para obtener los valores de los parámetros de la URL, los parámetros de la consulta o los campos de formulario enviados con la solicitud. En este caso, @RequestParam se utiliza para obtener el valor del parámetro name de la URL.
  
  - @SpringBootApplication:
  
  Esta anotación se utiliza para marcar una clase de configuración de Spring Boot. Combina varias anotaciones, incluidas @Configuration, @EnableAutoConfiguration y @ComponentScan. Indica que la clase es la clase principal de la aplicación Spring Boot y habilita la configuración automática de Spring Boot y el escaneo de componentes.
  
- Ahora, haz el request GET http://localhost:8080/greeting usando Postman, y revisa si el body de la respuesta es igual a alguno de los archivos del proyecto. Significa eso que es un recurso web dinámico o estático?

  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/072b8302-89f8-4f88-b48e-274615f8a3b6)

  El body de la respuesta no es igual a ninguno de los archivos del proyecto. Esto significa que es dinámico.


  




