---
title: Frecuencia de retorno
description: Cantidad de tiempo acumulada entre la visita actual y la anterior.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 4%

---


# Frecuencia de retorno

La dimensión &#39;Frecuencia de retorno&#39; muestra el período de tiempo que transcurre entre visitas desde visitantes de retorno. Cuando un visitante regresa a su sitio, Adobe observa cuánto tiempo atrás fue la visita anterior y bloquea la visita en el valor de dimensión correspondiente. Esta dimensión es valiosa para ayudar a medir el atractivo y la importancia que su sitio web tiene para los visitantes a lo largo del tiempo. También puede ayudar a identificar el impacto del contenido y las promociones del sitio en sus visitantes.

>[!TIP]
>
>Esta dimensión no incluye visitantes nuevos.

## Rellenar esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

Los datos de esta dimensión se establecen en la primera visita individual de la visita y persisten durante toda la visita. El valor no puede cambiar a mitad de la visita.

## Valores de dimensión

Los valores de dimensión incluyen bloques basados en tiempo, según el tiempo transcurrido desde la visita anterior.

* Menos de 1 día
* 1 a 3 días
* 3 a 7 días
* 7 a 14 días
* 14 días a 1 mes
* Más de 1 mes

## Los valores de dimensión aparecen bajo bloques fuera del intervalo de fechas del proyecto

Cuando se establece el intervalo de fechas de un proyecto, es común ver los valores de dimensión atribuidos a las visitas fuera del intervalo de fechas. Por ejemplo: un visitante llega a su sitio en julio y luego regresa dos veces en el mismo día en septiembre. La dimensión Frecuencia de retorno para el mes de septiembre muestra una visita en &#39;Más de 1 mes&#39; y una visita en &#39;Menos de 1 día&#39;.