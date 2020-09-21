---
title: Vínculo de descarga
description: Nombre del vínculo de descarga.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '180'
ht-degree: 100%

---


# Vínculo de descarga

La dimensión “Vínculo de descarga” indica los nombres de los vínculos de descarga implementados en el sitio. Esta dimensión es valiosa cuando desea obtener más información sobre el comportamiento del visitante en los vínculos de descarga como, por ejemplo:

* Determinar cuáles son los archivos que se descargan con mayor frecuencia desde el sitio.
* Saber si algunos archivos se descargan con mayor frecuencia durante períodos de tiempo específicos.
* Comprobar que los visitantes descargan distintos tipos de archivo si se ofrecen.

## Rellene esta dimensión con datos

Esta dimensión recopila datos de la [`pev2` cadena de consulta ](/help/implement/validate/query-parameters.md) en solicitudes de imagen para visitas individuales que también tienen la cadena de consulta `pe` con el valor de `lnk_d`. Si la cadena de consulta `pe` tiene un valor diferente en la visita, esta dimensión no recopila datos.

Si desea enviar datos a esta dimensión mediante AppMeasurement:

* Rellene la variable [`linkName`](/help/implement/vars/config-vars/linkname.md) con el valor deseado.
* Configure la variable [`linkType`](/help/implement/vars/config-vars/linktype.md) como `"d"`.
* Envíe una solicitud de imagen [`tl()`](/help/implement/vars/functions/tl-method.md).

## Elementos de dimensión

Dado que esta variable se basa en una cadena personalizada en la implementación, su organización determina cuáles son los elementos de dimensión. Adobe recomienda agrupar los vínculos en categorías significativas en función de sus necesidades de creación de informes.
