---
description: El informe de páginas de entrada muestra, según el porcentaje y el número total de visitas, qué páginas del sitio son las primeras en ser vistas por un nuevo visitante.
seo-description: El informe de páginas de entrada muestra, según el porcentaje y el número total de visitas, qué páginas del sitio son las primeras en ser vistas por un nuevo visitante.
seo-title: Entradas y salidas
solution: Analytics
title: Entradas y salidas
topic: 'Informes '
uuid: 756 de 55 b -136 b -427 b-a 80 c-f 822260131 b 1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Entradas y salidas

>[!NOTE]
>Para visitas con varios valores en la variable products, Entradas y Salidas se aplican a todos los valores de producto en una visita individual en lugar de solo a la primera.

El informe de páginas de entrada muestra, según el porcentaje y el número total de visitas, qué páginas del sitio son las primeras en ser vistas por un nuevo visitante.

Se pueden ver:

* **Páginas de entrada** (o secciones): muestra, según el porcentaje y el número total de visitas, las páginas del sitio que son las primeras en ser vistas por un nuevo visitante. Puede utilizar este informe para identificar qué páginas web del sitio son los puntos de entrada más frecuentes; optimizar los principales puntos de entrada al sitio y dirigir el tráfico de entrada hacia los mensajes clave.

   A useful way to use the Page View metric is to run a **[!UICONTROL Paths]** &gt; **[!UICONTROL Pages]** &gt; **[!UICONTROL Pages Entry]** report, sort by it, and see which entry pages drive the most page views.

* **Páginas de entrada originales**: muestra la primera página vista por los visitantes que entraron en el sitio por primera vez. Cada uno de los usuarios se cuenta una sola vez, a menos que estos borren sus cookies o que no se los esté rastreando con cookies.
* **Visitas a una sola página**: muestra las páginas que, con mayor frecuencia, constituyen la página de entrada y de salida en las sesiones de navegación de los visitantes.
* **Páginas de salida**: muestra, según el porcentaje y el número total de visitas, las páginas del sitio que fueron las últimas en ser vistas por los visitantes antes de abandonar el sitio. Las páginas de salida tienen un alcance de desglose de visitas, lo que significa que persisten a través de todas las visitas.

**Métricas en un informe de páginas de entrada**

* **Entradas**: equivale a instancias u ocurrencias, el número de veces que la página especificada es la página de entrada para una visita.
* **Visitas**: el número de visitas en las que la página ha sido la página de entrada (esta métrica debe ser igual al número de entradas).
* **Salidas**: el número de veces que se ha producido una salida cuando la página de entrada era la página especificada. Si quiere conocer el número de veces que la página de entrada también era la página de salida, use la métrica Devoluciones en lugar de salidas.

**Segmentación en un informe de página de entrada**

Al ejecutar un [!UICONTROL Informe de páginas de entrada], solo se incluyen en el informe las páginas de entrada, aunque haya aplicado segmentos a una página que no sea de entrada.

Por ejemplo, supongamos que se produce la siguiente secuencia de visita:

[!DNL Page A] &gt; [!DNL Page B] &gt; [!DNL Page C]

Si en un segmento se usan las páginas B y C, solo la página A se incluirá en el [!UICONTROL Informe de páginas de entrada], porque la página A es la página de entrada.
