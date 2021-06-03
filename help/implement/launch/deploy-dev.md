---
title: Implementación de Adobe Analytics en un entorno de desarrollo
description: Descubra cómo utilizar Adobe Experience Platform Launch para implementar Adobe Analytics en su entorno de desarrollo.
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 97%

---

# Integrar una implementación de Analytics en un entorno de desarrollo

Una vez creada y configurada una propiedad en Launch, las bibliotecas están listas para implementarse y el código se implementa en el sitio.

## Requisitos previos

[Cree y configure una propiedad para Adobe Analytics en Launch](create-analytics-property.md): Acceda a la herramienta y cree un espacio para la implementación de Analytics.

## Creación de adaptadores y entornos

Launch adapta muchos flujos de trabajo de la organización en la implementación de código. Siga estos pasos para crear los componentes mínimos necesarios para una implementación de Analytics. Como administrador de Launch, puede trabajar dentro de su organización para establecer el flujo de trabajo correcto para implementar las soluciones de Adobe.

1. Vaya a [Adobe Experience Platform Launch](https://launch.adobe.com) e inicie sesión si se le solicita.
2. Haga clic en la propiedad de Launch que desee implementar en el sitio.
3. Haga clic en la pestaña Adaptadores y, a continuación, haga clic en Agregar adaptador.
4. Asígnele el nombre “Akamai” y seleccione Akamai en la lista desplegable de tipos. Haga clic en Guardar.
5. Vaya a la pestaña Entornos y haga clic en Crear nuevo entorno.
6. Seleccione Desarrollo, asígnele el nombre “Entorno de desarrollo” y, a continuación, seleccione el adaptador de Akamai en el menú desplegable. Haga clic en Crear y, a continuación, en Cerrar.
7. Haga clic en Agregar entorno, seleccione Ensayo, asígnele el nombre “Entorno de ensayo” y, a continuación, seleccione el adaptador de Akamai. Haga clic en Crear y, a continuación, en Cerrar.
8. Vuelva a hacer clic en Agregar entorno, seleccione Producción, asígnele el nombre “Entorno de producción” y, a continuación, seleccione el adaptador de Akamai. Haga clic en Crear y, a continuación, en Cerrar.

## Creación de una biblioteca de desarrollo

A pesar de todos los cambios y configuraciones realizados hasta ahora, no se ha publicado ningún código. La creación de una biblioteca, traducida como una colección de cambios, permite la publicación de código para su uso en el sitio.

1. Vaya a [Adobe Experience Platform Launch](https://launch.adobe.com) e inicie sesión si se le solicita.
2. Haga clic en la propiedad de Launch que desee implementar en el sitio.
3. Haga clic en la pestaña Publicación y, a continuación, en Agregar nueva biblioteca.
4. Asigne a la biblioteca el nombre “Cambios iniciales” y seleccione su entorno de desarrollo.
5. Haga clic en Agregar todos los recursos modificados, que muestra automáticamente Adobe Analytics, Servicio de identidad y Principal.
6. Haga clic en Guardar.
7. Vuelva a la pantalla Flujo de trabajo de publicación, haga clic en el menú desplegable situado junto a la nueva biblioteca y, a continuación, haga clic en Generar para desarrollo. Después de unos segundos, el punto amarillo de la biblioteca se vuelve verde, lo que indica que la compilación se realizó correctamente.
8. Vaya a la pestaña Entornos y haga clic en su entorno de desarrollo.
9. En Instalar Launch, copie los bloques de código y envíeselos a los propietarios del sitio web de su organización.

## Instalación de Launch en el entorno de desarrollo del sitio web

Si controla el código de su sitio web, implemente los dos bloques de código en sus respectivas ubicaciones (en la etiqueta `<head>` y justo encima de la etiqueta de cierre `</body>`) en cada página del sitio. Este código generalmente se coloca en la plantilla de portada del sitio. Una página en blanco que solo contenga código de implementación tendría el siguiente aspecto:

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Example page</title>
  <script src="//assets.adobedtm.com/launch-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx-development.min.js"></script>
</head>
<body>
   <p>This is a test page.</p>
   <script type="text/javascript">_satellite.pageBottom();</script>
</body>
</html>
```

## Resolución de problemas

**Error al intentar la generación.**

Un motivo común es que ya existen elementos en otras bibliotecas que se insertan en las fases de ensayo o producción. Al crear bibliotecas por primera vez, asegúrese de que solo se agregan recursos modificados a la biblioteca.

## Documentación y recursos adicionales

- [Introducción a Launch](https://experienceleague.adobe.com/docs/launch/using/intro/get-started/quick-start.html): Conozca el flujo de trabajo básico de Launch
- [Publicación de Launch](https://experienceleague.adobe.com/docs/launch/using/reference/publish/overview.html): Obtenga más información sobre adaptadores y entornos

## Pasos siguientes

[Valide la implementación de Analytics y publique en el proceso de producción](validate-publish-prod.md): Empiece a sacar el máximo partido de Adobe Analytics.
