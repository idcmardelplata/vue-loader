# Introduction

### Que es `vue-loader`?

`vue-loader` es un loader para Webpack que puede transformar los componentes de Vue escritos en los siguientes formatos en un modulo simple de JavaScript:

![screenshot](http://blog.evanyou.me/images/vue-component.png)

Existen muchas funciones interesantes que proporciona `vue-loader`:

- ES2015 habilitado por defecto;
- Permite utilizar otros cargadores Webpack para cada parte de un componente Vue, por ejemplo SASS para `<style>` y Jade para `<template>`;
- Permite secciones personalizadas en un archivo .Vue que pueden tener aplicados multiples cargadores webpack personalizados.
- Trata los archivos estaticos mencionados en `<style>` y `<template>` como dependencias de modulos y manejarlas con cargadores Webpack;
- Puede simular CSS con ambito para cada componente.
- Soporta la recarga en caliente de componentes durante el desarrollo.

En una palabra, la combinacion de Webpack y `vue-loader` nos ofrece un workflow frontend moderno, flexible y extremadamente potente para crear aplicaciones Vue.

### ¿Que es Webpack?

Si ya esta familiarizado con Webpack, no dude en omitir la siguiente explicación. Pero para aquellos de ustedes que son nuevos en Webpack, he aqui una introducción rapida.

[Webpack](http://webpack.github.io/) Es un grupo de modulos. Esto toma un monton de archivos tratando a cada uno como un modulo, averigua las dependencias entre ellos, y los agrupa en assets estaticos listos para su implementación.

![webpack](http://webpack.github.io/assets/what-is-webpack.png)

Para un ejemplo básico, imaginemos que tenemos un monton de modulos CommonJS. Estos no pueden ejecutarse directamente en el navegador, por lo que necesitamos agruparlos en un solo archivo para que se pueda incluir a través de una etiqueta `<script>`. Webpack es capaz de seguir las dependencias de las llamadas a `require()` y hacer eso por nosotros.

Pero Webpack puede hacer mas que eso. Con "cargadores", Podemos enseñarle a Webpack como transformar todo tipo de archivos de la forma que deseemos antes de crear el paquete final. Algunos ejemplos incluyen:

- Transpilar ES2015, CoffeeScript o modulos TypeScript en modulos sencillos ES5 CommonJS.
- Opcionalmente puede canalizar el codigo fuente a través de un linter antes de hacer la compilación.
- Transpile las plantillas de Jade en HTML simple y en linea como una cadena de JavaScript.
- Transpila archivos SASS en CSS simple, luego convierte esto en un snippet JavaScript que insertara el CSS resultante en una etiqueta `<style>`.
- Procesar un archivo de imagen referenciado en un HTML o CSS, y moverlo al destino deseado basado en las configuraciónes del path y nombrarlo usando su hash md5.

Webpack es tan potente que cuando entiendes como funciona, puede mejorar dramaticamente tu flujo de trabajo front-end. Su principal desventaja es su configuración detallada y compleja; pero con esta guia deberia ser capaz de encontrar soluciones a los problemas mas comunes al usar Webpack con Vue.js y `vue-loader`.
