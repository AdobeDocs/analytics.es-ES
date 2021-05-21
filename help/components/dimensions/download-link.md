---
title: Vínculo de descarga
description: Nombre del vínculo de descarga.
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '184'
ht-degree: 100%

---

# Vínculo de descarga

La dimensión “Vínculo de descarga” indica los nombres de los vínculos de descarga implementados en el sitio. Esta dimensión es valiosa cuando desea obtener más información sobre el comportamiento del visitante en los vínculos de descarga como, por ejemplo:

* Determinar cuáles son los archivos que se descargan con mayor frecuencia desde el sitio.
* Saber si algunos archivos se descargan con mayor frecuencia durante períodos de tiempo específicos.
* Comprobar que los visitantes descargan distintos tipos de archivo si se ofrecen.

## Rellene esta dimensión con datos

Esta dimensión recopila datos de la [`pev2` cadena de consulta ](/help/implement/validate/query-parameters.md) en solicitudes de imagen para visitas individuales que también tienen la cadena de consulta `pe` con el valor de `lnk_d`. Si la cadena de consulta `pe` tiene un valor diferente en la visita, esta dimensión no recopila datos.

Si desea enviar datos a esta dimensión mediante AppMeasurement, envíe una solicitud de imagen [`tl()`](/help/implement/vars/functions/tl-method.md) con un argumento de tipo de vínculo de `"d"`. Rellene el argumento del nombre del vínculo con el valor deseado.

## Elementos de dimensión

Dado que esta variable se basa en una cadena personalizada en la implementación, su organización determina cuáles son los elementos de dimensión. Adobe recomienda agrupar los vínculos en categorías significativas en función de sus necesidades de creación de informes.
