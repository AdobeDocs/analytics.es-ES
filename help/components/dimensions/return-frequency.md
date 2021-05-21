---
title: Frecuencia de retorno
description: Cantidad de tiempo acumulada entre la visita actual y la anterior.
exl-id: 8ec31e17-a57d-416f-b471-c2c37a98d134
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '252'
ht-degree: 100%

---

# Frecuencia de retorno

La dimensión “Frecuencia de retorno” muestra el periodo de tiempo que transcurre entre las visitas de un visitante que retorna. Cuando un visitante regresa a su sitio, Adobe consulta hace cuánto tiempo se produjo la visita anterior y agrupa la visita en el elemento de dimensión correspondiente. Esta dimensión es valiosa para ayudar a medir el atractivo y la importancia que su sitio web tiene para los visitantes a lo largo del tiempo. También puede ayudar a identificar el impacto del contenido y las promociones del sitio en sus visitantes.

>[!TIP]
>
>Esta dimensión no incluye visitantes nuevos.

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones. Si un grupo de informes contiene datos, esta dimensión funciona.

Los datos de esta dimensión se establecen en la primera visita individual de la visita y persisten durante toda la visita. El valor no puede cambiar a mitad de la visita.

## Elementos de dimensión

Los elementos de dimensión incluyen bloques basados en tiempo, según el tiempo transcurrido desde la visita anterior.

* Menos de 1 día
* 1 a 3 días
* 3 a 7 días
* 7 a 14 días
* 14 días a 1 mes
* Más de 1 mes

## Los elementos de dimensión aparecen bajo bloques fuera del intervalo de fechas del proyecto

Cuando se establece el intervalo de fechas de un proyecto, es común ver los elementos de dimensión atribuidos a las visitas fuera del intervalo de fechas. Por ejemplo, un visitante llega al sitio en julio y vuelve dos veces en el mismo día en septiembre. La dimensión Frecuencia de retorno del mes de septiembre incluirá una visita en “Más de 1 mes” y una visita en “Menos de un día”.
