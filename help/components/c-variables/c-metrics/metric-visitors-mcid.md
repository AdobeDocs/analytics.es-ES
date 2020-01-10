---
description: Está disponible en Analysis Workspace y en el Generador de segmentos.
title: Visitantes con Experience Cloud ID
uuid: 47ebd3d6-a921-4e51-ac7a-b8d5fb9565e0
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Visitantes con Experience Cloud ID

Está disponible en Analysis Workspace y en el Generador de segmentos.

Muestra el número de visitantes que tienen un Experience Cloud ID. Puede comprender qué páginas tienen implementado el servicio de identidad y cuántos visitantes se pueden compartir con otras soluciones de Experience Cloud. También puede usar esta métrica en segmentos que se comparten con Experience Cloud.

>[!IMPORTANT]
>
>Tenga en cuenta que esta métrica se muestra cuando se utiliza el [servicio de identidad](https://marketing.adobe.com/resources/help/es_ES/mcvid/) con el grupo de informes.

## Depuración de la configuración de Experience Cloud ID {#section_679E62142A3E46548FF8FBDA46568005}

La métrica [!UICONTROL Visitantes con Experience Cloud ID] de Adobe Analytics es muy útil y sirve para ayudar a encontrar y depurar la configuración del [!UICONTROL servicio de identidad]. La métrica es un recuento del número de visitantes en un grupo de informes a los que se les ha asignado un Experience Cloud ID desde el servicio de identidad. Esta métrica puede ser muy útil para diagnosticar por qué es posible que determinadas integraciones de Experience Cloud no compartan tantos visitantes como se esperaba, o bien para identificar áreas del sitio que no tengan aún MCID implementados.

Para utilizar la métrica Visitantes con Experience Cloud ID, simplemente arrástrela a cualquier informe como métrica, como este informe [!UICONTROL Páginas]:

![](assets/metric-mcvid1.png)

En este ejemplo, observe que cada página tiene el mismo número de visitantes únicos y de visitantes con un Experience Cloud ID. Sin embargo, el número total de visitantes únicos es mayor que el número total de visitantes con Experience Cloud ID. Para buscar las páginas que no han configurado el MCID para todos los visitantes, [cree una métrica calculada](https://marketing.adobe.com/resources/help/es_ES/analytics/calcmetrics/cm_build_metrics.html) con esta definición:

![](assets/metric-mcvid2.png)

Al añadir la métrica calculada al informe, puede ordenar el informe Páginas de manera que aparezcan las páginas con el mayor número de visitantes sin un MCID:

![](assets/metric-mcvid3.png)

Ahora puede ver rápidamente que las páginas “Vistas rápidas de productos” no se han implementado correctamente en el servicio de identidad y que deben actualizarse cuanto antes. Se puede construir un informe similar en relación a cualquier tipo de dimensión, como el tipo de navegador, la sección del sitio o los tipos de contenido.

Una vez que haya identificado las páginas que tienen visitantes sin ECID, podrá enviarlas al equipo de implementación para que puedan solucionar el problema de dichas páginas.

En algunos casos, es posible que observe que un número pequeño de MCID no se ha configurado para algunos visitantes a pesar de que el servicio MCID se implementó en la página. Esto se debe probablemente a una configuración errónea del JavaScript de Analytics o de la configuración de DTM donde la función AppMeasurement se adopta antes de proporcionar un grupo de informes. Para evitar esto, asegúrese de [insertar el código de AppMeasurement principal](https://marketing.adobe.com/resources/help/en_US/sc/implement/dtm/t_appmeasurement-code.html) correctamente.

Tenga en cuenta que cualquier segmento basado en la página “Vistas rápidas de productos” (como se muestra arriba) que comparta con Experience Cloud probablemente tendrá una tasa de coincidencia muy baja con otras soluciones de Experience Cloud. Para comprobar el alcance de MCID de cualquier segmento, puede crear un informe de la siguiente manera:

![](assets/metric-mcvid4.png)

A partir de esta tabla, en la que se comparan el número de visitantes únicos y el de visitantes con un Experience Cloud ID, es fácil observar que el “Segmento 1” no tiene un alcance de ECID del 100 %, mientras que el “Segmento 2”, sí. Esto significa que, si tuviera que compartir el Segmento 1 con Experience Cloud, solo se podrían compartir 2186 de los 3859 visitantes que forman el total.
