---
layout: post
title: Introducción al protocolo HTTP
subtitle: Conceptos básicos y flujo general
cover-img: /assets/img/http-protocol.jpg
thumbnail-img: /assets/img/HTTPs.png
share-img: /assets/img/http-protocol.jpg
tags: [protocolo, concepto]
author: ss3k
---

{: .box-success}
Esta es una introducción al protocolo HTTP/s. Cabe destacar que, para efectos de este tema, utilizaremos los términos HTTP y HTTPS de manera indistinta, ya que en esta ocasión no nos enfocaremos en las diferencias de seguridad que existen entre ambos.

## ¿Qué es HTTP?

- HTTP (Protocolo de Transferencia de Hipertexto) es un protocolo de capa de aplicación **sin estado**, utilizado para la transmisión de recursos, como datos de aplicaciones web, que funciona sobre TCP.
- Fue diseñado específicamente para la comunicación entre navegadores web y servidores web.
- HTTP utiliza la arquitectura típica cliente-servidor para la comunicación, donde el navegador es el cliente y el servidor web es el servidor.
- Los recursos se identifican de manera única mediante una URL/URI.

{: .box-note}
**Nota:** URI: Uniform Resource Identifier || URL: Uniform Resource Locator


#### El flujo, a simple vista, es tal que así:
![HTTP](/assets/img/http-basics-1.webp){: .mx-auto.d-block :}

- Durante uan comunicación HTTP, el cliente y el servidor intercambian mensajes, comunmente clasificados como _HTTP requests_ y _responses_.
- El cliente envía solicitudes al servidor (_requests_) y recibe respuestas (_responses_).


#### Dentro de esta comunicación hay dos secciones escenciales --> HEADERS y MESSAGE BODY

![Burp](/assets/img/burp.jpg){: .mx-auto.d-block :}

---------------------

## Hablemos de los componentes de **HTTP _request_**

### I. Request line.

La linea request es la primera linea dentro de HTTP request y contiene los siguientes tres componentes: 
- Método HTTP (ej., GET, POST, PUT, DELETE, OPTIONS, etc.): Indíca el tipo de solicitud que se está realizando.
- URL (Uniform Resource Locator): La di rección del recursos a la que el cliente quiere acceder.
- Versión HTTP: La versión del protocolo HTTP que se está usando (ej., HTTP/1.1).

### II. Request header.

Las cabeceras entregan información adicional sobre la solicitud que se está realizando. Algunas cabeceras comunes son:
- User-Agent: Información sobre el cliente que realiza la solicitud (ej., tipo de navegador).
- Host: El hostname del servidor.
- Accept: El tipo de contenido que puede manejar el cliente en la respuesta (ej., HTML, JSON).
- Authorization: Credenciales de acceso en caso de ser necesario.
- Cookie: Información almacenada por lado del cliente (_client-side_) y enviada de vuelta al servidor en cada solicitud.

### III. Request body (opcional).

Algunos métodos HTTP (como POST o PUT) incluyen una request body donde se envía al servidor la data que se quiere manipular, comunmente en JSON.4

~~~
**hola** asd a
~~~
