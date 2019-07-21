---
title: Implementación de Adobe Analytics en un entorno de desarrollo
seo-title: Implementación de Adobe Analytics en un entorno de desarrollo
description: Descubra cómo utilizar Adobe Experience Platform Launch para implementar Adobe Analytics en su entorno de desarrollo.
seo-description: Descubra cómo utilizar Adobe Experience Platform Launch para implementar Adobe Analytics en su entorno de desarrollo.
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Implementación de una implementación de Analytics en un entorno de desarrollo

Una vez creada y configurada la propiedad en Launch, las bibliotecas están listas para implementarse y el código implementado en el sitio.

## Requisitos previos

[Cree y configure una propiedad para Adobe Analytics en Launch](create-analytics-property.md): Acceda a la herramienta y cree un espacio para su implementación de Analytics.

## Creación de adaptadores y entornos

Launch acomoda muchos flujos de trabajo de organización al implementar código. Siga estos pasos para crear los componentes mínimos necesarios para una implementación de Analytics. Como administrador de Launch, puede trabajar dentro de su organización para establecer el flujo de trabajo correcto para implementar las soluciones de Adobe.

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. Haga clic en la propiedad Launch que desee implementar en el sitio.
3. Haga clic en la ficha Adaptadores y, a continuación, haga clic en Agregar adaptador.
4. Póngale el nombre "Akamai" y seleccione Akamai en el menú desplegable Tipo. Haga clic en Guardar.
5. Vaya a la ficha Entornos y, a continuación, haga clic en Crear nuevo entorno.
6. Seleccione Desarrollo, asígnele el nombre «Entorno dev» y, a continuación, seleccione el adaptador Akamai en el menú desplegable. Haga clic en Crear y, a continuación, en Cerrar.
7. Haga clic en Añadir entorno, seleccione Ensayo, póngale nombre "Entorno de ensayo" y, a continuación, seleccione el adaptador Akamai. Haga clic en Crear y, a continuación, en Cerrar.
8. Vuelva a hacer clic en Añadir entorno, seleccione Producción, asígnele el nombre «Entorno de producción» y, a continuación, seleccione el adaptador Akamai. Haga clic en Crear y, a continuación, en Cerrar.

## Creación de una biblioteca dev

A pesar de todos los cambios y configuraciones realizados hasta el momento, no se publicó ningún código. La creación de una biblioteca, que se traduce aproximadamente como una colección de cambios, permite la publicación de código en el sitio.

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. Haga clic en la propiedad Launch que desee implementar en el sitio.
3. Haga clic en la ficha Publicación y, a continuación, haga clic en Agregar nueva biblioteca.
4. Asigne un nombre a los cambios iniciales de la biblioteca y seleccione su entorno de desarrollo.
5. Haga clic en Agregar todos los recursos modificados, que muestra automáticamente Adobe Analytics, Servicio de identidad y Core.
6. Haga clic en Guardar.
7. Vuelva a la pantalla de flujo de trabajo de publicación, haga clic en el menú desplegable situado junto a la nueva biblioteca y haga clic en Generar para desarrollo. Pasados unos segundos, el punto amarillo de la biblioteca se vuelve verde, indicando que la compilación se ha realizado correctamente.
8. Vaya a la ficha Entornos y, a continuación, haga clic en su entorno de desarrollo.
9. En «Install Launch» (Instalar lanzamiento), copie los bloques de código y proporciónelos a los propietarios de sitios web de su organización.

## Instalación en el entorno de desarrollo de su sitio web

If you control your website's code, implement the two blocks of code in their respective locations (in the `<head>` tag and just above the closing `</body>` tag) on every page of your site. Este código suele colocarse en la plantilla global del sitio. Una página en blanco que contenga el código de implementación tendría el siguiente aspecto:

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

**Intentar generar falla.**

Un motivo común es porque los elementos ya existen en otras bibliotecas insertadas en ensayo o producción. Al crear bibliotecas inicialmente, asegúrese de que solo se agregan recursos modificados a la biblioteca.

## Documentación y recursos adicionales

- [Introducción a Launch](https://docs.adobelaunch.com/getting-started): Obtenga información sobre el flujo de trabajo básico de Launch
- [Administración de lanzamiento](https://docs.adobelaunch.com/administration): Más información sobre adaptadores y entornos

## Pasos siguientes

[Valide su implementación de Analytics y publique en producción](validate-publish-prod.md): Empiece a obtener valor de Adobe Analytics.
