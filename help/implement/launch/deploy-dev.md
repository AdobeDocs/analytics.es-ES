---
title: Implementación de Adobe Analytics en un entorno de desarrollo
description: Descubra cómo utilizar etiquetas para implementar Adobe Analytics en su entorno de desarrollo.
feature: Tags
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 48%

---

# Integrar una implementación de Analytics en un entorno de desarrollo

Una vez creada y configurada una propiedad de etiquetas, las bibliotecas están listas para implementarse y el código se implementa en el sitio.

## Requisitos previos

[Crear y configurar una propiedad de etiquetas para Adobe Analytics](create-analytics-property.md): Acceda a la herramienta y cree un espacio para la implementación de Analytics.

## Creación de adaptadores y entornos

Las etiquetas adaptan muchos flujos de trabajo de la organización en la implementación de código. Siga estos pasos para crear los componentes mínimos necesarios para una implementación de Analytics. Como administrador de etiquetas, puede trabajar dentro de su organización para establecer el flujo de trabajo correcto para implementar las soluciones de Adobe.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas que desee implementar en el sitio.
3. Haga clic en **[!UICONTROL Hosts]** y, a continuación, haga clic en **[!UICONTROL Agregar host]**.
4. Asígnele el nombre `"Adobe managed"` y seleccione **[!UICONTROL Administrado por Adobe]** en la lista desplegable de tipos. Haga clic en Guardar.
5. Vaya a **[!UICONTROL Entornos]** y haga clic en **[!UICONTROL Agregar entorno]**.
6. Seleccione **[!UICONTROL Desarrollo]**, asígnele el nombre `"Dev Environment"` y, a continuación, seleccione el host administrado por Adobe en la lista desplegable. Haga clic en **[!UICONTROL Guardar]**.
7. Aparece una ventana modal que muestra las instrucciones de instalación web. Volveremos a esta ventana más adelante; por ahora, haz clic en **[!UICONTROL Cerrar]**.
8. Haga clic en **[!UICONTROL Agregar entorno]**, seleccione **[!UICONTROL Ensayo]**, asígnele el nombre `"Staging Environment"` y, a continuación, seleccione el host administrado por el Adobe. Haga clic en **[!UICONTROL Crear]** y cierre la ventana modal de instrucciones de instalación.
9. Vuelva a hacer clic en **[!UICONTROL Agregar entorno]**, seleccione **[!UICONTROL Producción]**, asígnele el nombre `"Production Environment"` y, a continuación, seleccione el host administrado por el Adobe. Haga clic en **[!UICONTROL Crear]** y cierre la ventana modal de instrucciones de instalación.

## Creación de una biblioteca de desarrollo

A pesar de todos los cambios y configuraciones realizados hasta ahora, no se ha publicado ningún código. La creación de una biblioteca, traducida como una colección de cambios, permite la publicación de código para su uso en el sitio.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas que desee implementar en el sitio.
3. Haga clic en la ficha **[!UICONTROL Flujo de publicación]** y, a continuación, haga clic en **[!UICONTROL Agregar biblioteca]**. Consulte [Información general de publicación](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=es) en la documentación de etiquetas para obtener más información sobre esta página.
4. Asigne un nombre a la biblioteca `'Initial changes'` y seleccione su entorno de desarrollo.
5. Haga clic en **[!UICONTROL Agregar todos los recursos modificados]**, que muestra automáticamente Adobe Analytics, Servicio de identidad y Principal.
6. Haga clic en **[!UICONTROL Guardar]**.
7. Vuelva a la pantalla Flujo de trabajo de publicación, haga clic en la lista desplegable situada junto a la nueva biblioteca y, a continuación, haga clic en **[!UICONTROL Generar para desarrollo]**. Después de unos segundos, el punto amarillo de la biblioteca se vuelve verde, lo que indica que la compilación se realizó correctamente.
8. Vaya a **[!UICONTROL Entornos]** y haga clic en el icono de instalación a la derecha del entorno de desarrollo. Esta acción vuelve a abrir la ventana modal Instrucciones de instalación web.
9. Copie los bloques de código y envíeselos a los propietarios del sitio web de su organización.

## Instalación de etiquetas en el entorno de desarrollo del sitio web

Si controla el código de su sitio web, implemente cada bloque de código en su ubicación respectiva:

* La etiqueta principal pertenece a la etiqueta `<head>` del sitio.
* Si decide cargar las etiquetas sincrónicamente, también debe incluir un segundo bloque de código justo debajo de la etiqueta de cierre `</body>` en el sitio. Puede elegir cargar las etiquetas de biblioteca de manera sincrónica alternando la opción **[!UICONTROL Cargar biblioteca de forma asincrónica]** en las Instrucciones de instalación web.

El código de etiqueta suele colocarse en la plantilla general del sitio. Una página en blanco que solo contenga código de implementación tendría el siguiente aspecto:

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
   <!-- Only include this extra code if you load tags synchronously -->
   <script type="text/javascript">_satellite.pageBottom();</script>
</body>
</html>
```

## Resolución de problemas

**Error al intentar la generación.**

Un motivo común es que ya existen elementos en otras bibliotecas que se insertan en las fases de ensayo o producción. Al crear bibliotecas por primera vez, asegúrese de que solo se agregan recursos modificados a la biblioteca.

## Pasos siguientes

[Valide la implementación de Analytics y publique en el proceso de producción](validate-publish-prod.md): Empiece a sacar el máximo partido de Adobe Analytics.
