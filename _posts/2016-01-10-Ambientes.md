---
layout: post
title: Ambientes
author: "@gonzalomvelasco"
---

Al principio se comenzó utilizando un único ambiente para el desarrollo de la aplicación, testing y como prototipo de aceptación del cliente. De esta manera, también se tenía compartida la base de datos; lo que resultaba en una mezcla de los datos de prueba y los productivos. Para evitar errores en las presentaciones, nos tomábamos el trabajo de limpiar la base y reconstruir manualmente el set de datos necesarios para llevarla a cabo.

Para el código de la aplicación, se eligió utilizar GitHub por preferencia nuestra, para trabajar de manera colaborativa. Es gratis, público y sencillo de utilizar, además de las facilidades de integración con otras aplicaciones que también utilizamos (Slack, Travis, Heroku, etc) en el proyecto.

La persistencia de datos inicialmente se diseñó en una única base de datos de acceso remoto online. Se tomó esta decisión por un tema de sencillez. Elegimos Mongoose.

Aceptémoslo… Queríamos empezar, y empezar ya. Lo que intentamos resolver rápidamente fue la preparación de un ambiente completo que nos permitiera comenzar a desarrollar y mantener el código versionado. No era lo mejor, lo sabíamos pero al menos así, se podía usar online, y compartirlo sin necesidad de mandarnos archivos comprimidos por mail (ja).

Los problemas no tardaron en aparecer. Se generaban muchos datos de prueba por cada integrante del equipo. Además, siendo de desarrollo, podían no se detectarse errores que después se encontraban más adelante. Colaborábamos todos en generar una base con los renombrados "datos basura". Sumábamos a esto que al solo poder acceder online a la base de datos, cuando no se contaba con una conexión de internet se caia la aplicación local.

La primera mejora la obtuvimos con la incorporación de bases de datos locales. Cada uno podía entonces realizar sus pruebas sin perjudicar al otro. El ambiente lleva más tiempo de preparado, pero los resultados valen la pena. 

Luego nos armamos de valentía y separamos los ambientes en desarrollo, staging y producción. Cada uno con su base de datos y con el deploy en un pipeline, es decir, una vez cerrada la versión de desarrollo se sube a staging. Se muestra desde ahí al cliente y cuando éste la aprueba, se sube a producción. Lo que buscamos es tener en producción la versión más estable y terminada de la aplicación por cada iteración.

Finalmente, comenzamos a automatizar las pruebas unitarias y de integración con Travis. Estamos todavía trabajando en ellas para poder incorporar BDD.

