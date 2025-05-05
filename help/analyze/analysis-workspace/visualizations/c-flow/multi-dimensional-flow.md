---
description: Un flujo interdimensional le permite examinar las rutas del usuario entre diversas dimensiones.
title: Flujos interdimensionales
uuid: 51d08531-1c56-46c7-b505-bd8d5e6aa6c1
feature: Visualizations
role: User, Admin
exl-id: f84917a4-2c07-48fb-9af3-d96c537da65c
source-git-commit: be6056f9e7a64b47ab544594149ebfbe134f1c04
workflow-type: ht
source-wordcount: '340'
ht-degree: 100%

---

# Flujos interdimensionales

Un flujo interdimensional le permite examinar las rutas del usuario entre diversas dimensiones.

>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Flujos interdimensionales](https://video.tv.adobe.com/v/327473?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]

Este artículo muestra cómo utilizar este flujo para dos casos de uso: interacciones y eventos de aplicaciones móviles y cómo las campañas impulsan las visitas web.

## Eventos e interacciones de aplicaciones móviles

La dimensión [!UICONTROL Nombre de pantalla] se usa en este flujo de ejemplo para ver cómo utilizan los usuarios las distintas pantallas (escenas) de la aplicación. La pantalla principal devuelta es **[!UICONTROL luma: content: ios: en: home]**, que es la página principal de la aplicación:

![Un flujo que muestra el elemento añadido.](assets/flowapp.png)

Para explorar la interacción entre pantallas y tipos de eventos (como añadir al carro de compras, compras, etc.) en esta aplicación, arrastre y suelte la dimensión **[!UICONTROL Tipos de eventos]**:

* Sobre cualquier paso disponible en el flujo, para reemplazar esa dimensión:

  ![Un flujo que muestra la dimensión Página arrastrada a varias áreas.](assets/flowapp-replace.png)

* Fuera de la visualización de flujo actual, para añadir la dimensión:

  ![Un flujo que muestra la dimensión Página arrastrada al espacio en blanco al final.](assets/flowapp-add.png)

La siguiente visualización de flujo muestra el resultado de añadir la dimensión **[!UICONTROL Tipos de eventos]**. La visualización proporciona perspectivas sobre cómo los usuarios de aplicaciones móviles se mueven por varias pantallas de la aplicación antes de añadir productos al carro de compras, cerrar la aplicación, que se les presente una oferta y mucho más.

![Un valor de flujo que muestra los resultados de la dimensión Página en la parte superior de la lista.](assets/flowapp-result.png)

## Cómo impulsan las campañas las visitas a la web

Desea analizar qué campañas generan visitas al sitio web. Crea una visualización de flujo con **[!UICONTROL Nombre de campaña]** como dimensión

![Dimensión de nombre de campaña web de flujo](assets/flowweb.png)

Reemplace la última dimensión **[!UICONTROL Nombre de campaña]** por la dimensión **[!UICONTROL Nombre de página con formato]** y añada otra dimensión **[!UICONTROL Nombre de página con formato]** al final de la visualización del flujo.

![Nombre de campaña web de flujo y dimensión de página web](assets/flowweb-replace.png)

Puede pasar el ratón sobre cualquiera de los flujos para ver más detalles. Por ejemplo, qué campañas han resultado en un cierre de compra del carro de compras.

![Desplazamiento sobre nombre de campaña web de flujo y dimensión de página web](assets/flowweb-hover.png)
