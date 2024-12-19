---
layout: post
title: Introducción al protocolo HTTP
subtitle: Conceptos básicos y flujo general
cover-img: /assets/img/http-protocol.jpg
thumbnail-img: /assets/img/HTTPs.png
share-img: /assets/img/http-protocol.jpg
tags: [protocolo, concepto]
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
- URL (Uniform Resource Locator): La dirección del recursos a la que el cliente quiere acceder.
- Versión HTTP: La versión del protocolo HTTP que se está usando (ej., HTTP/1.1).

### II. Request header.

Las cabeceras entregan información adicional sobre la solicitud que se está realizando. Algunas cabeceras comunes son:
- User-Agent: Información sobre el cliente que realiza la solicitud (ej., tipo de navegador).
- Host: El hostname del servidor.
- Accept: El tipo de contenido que puede manejar el cliente en la respuesta (ej., HTML, JSON).
- Authorization: Credenciales de acceso en caso de ser necesario.
- Cookie: Información almacenada por lado del cliente (_client-side_) y enviada de vuelta al servidor en cada solicitud.

### III. Request body (opcional).

Algunos métodos HTTP (como POST o PUT) incluyen una request body donde se envía al servidor la data que se quiere manipular, comunmente en JSON.

------------------------

### Ejemplo de HTTP request (mostrada en la imágen anterior)

~~~
GET  /HTTP/1.1
Host: www.sitioejemplo.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/108.0.0.0 Safari/537.36
Accept: text/html, application/xhtml+xml
Accept-Encoding: gzip, deflate
Connection: keep-alive

<BODY>
~~~

-----------------

## Hablemos de los tipos de métodos.

| Método | Función |
| :------ |:--- | :--- |
| GET | Solicita datos de un servidor sin modificar nada. Es utilizado para obtener información de una URL específica, como páginas web, imágenes o archivos. Es un método seguro y idempotente, lo que significa que no tiene efectos secundarios y su resultado no cambia si se ejecuta varias veces |
| POST | Envía datos al servidor para crear o modificar un recurso. Se usa comúnmente en formularios, como registro, inicio de sesión o envío de datos. A diferencia de GET, no es idempotente, lo que implica que al enviarlo varias veces puede generar diferentes resultados |
| PUT | Reemplaza un recurso completo en el servidor, creando o actualizando el recurso en la URL especificada. Se usa cuando se requiere actualizar un recurso con nuevos datos completos, como modificar un perfil de usuario o actualizar una entrada en una base de datos. Es idempotente, lo que significa que al repetir la solicitud no cambia el resultado |
| DELETE | Elimina un recurso específico en el servidor, como eliminar un producto, usuario o archivo. Es útil en aplicaciones para realizar operaciones de limpieza o eliminación permanente. Al igual que PUT, es idempotente; si se realiza varias veces, no tendrá efectos adicionales después de la primera ejecución |
| PATCH | Realiza una actualización parcial de un recurso, enviando solo los datos que deben ser modificados. Ideal para cambios pequeños, como actualizar un campo específico de un objeto o entrada, sin necesidad de reemplazar el recurso completo. No es idempotente por completo, ya que depende de los cambios que se realicen |
| HEAD | Solicita solo los encabezados de un recurso sin obtener su cuerpo. Es útil para obtener metadatos como el tipo de contenido, la longitud del archivo o la última modificación de un recurso, sin necesidad de descargarlo. Es como un GET pero sin recibir los datos asociados al recurso |
| OPTIONS | Solicita los métodos HTTP permitidos por el servidor para un recurso específico. Se usa para saber qué operaciones (GET, POST, PUT, etc.) se pueden realizar en una URL, y es útil en la negociación de CORS (Cross-Origin Resource Sharing) para definir las políticas de acceso entre dominios | 

-------------------------

# [AQUÍ] PRÓXIMAMENTE HTTP RESPONSE COMPONENTS


----------------
