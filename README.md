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

  ![image](https://github.com/Nat15005/CVDS_Lab05/assets/111907712/2fed87c0-bef1-40db-9ddf-949717413744)

  

  


