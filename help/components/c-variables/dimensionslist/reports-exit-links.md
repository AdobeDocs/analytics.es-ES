---
title: Vínculos de salida
description: Informar sobre los vínculos más comunes en los que las personas hacen clic para abandonar el sitio.
translation-type: tm+mt
source-git-commit: be4c3ec95b9e93dda7603c0bdb178c0a54d800a0

---


# Vínculos de salida

Muestra los vínculos más comunes en los que las personas hacen clic para abandonar el sitio. Estos vínculos normalmente apuntan a sitios asociados o afiliados; sin embargo, pueden ser cualquier ubicación donde tenga un vínculo externo. Este informe permite ver los vínculos de afiliados más populares y ayuda a validar el número de referentes que se ha proporcionado conforme al estado de los socios.

Para que esta página se rellene correctamente deben cumplirse varios requisitos:
* Si se utiliza el seguimiento manual de vínculos personalizados, se debe activar una `tl()` solicitud con el parámetro central establecido en `e`.
* Si se realiza un seguimiento automático de los vínculos personalizados, deben cumplirse todos los requisitos siguientes:
   * La [variable trackExternalLinks](/help/implement/vars/config-vars/trackexternallinks.md) debe estar habilitada.
   * The link the user clicked on must not match any values within the [linkInternalFilters](/help/implement/vars/config-vars/linkinternalfilters.md) variable.
   * If the [linkExternalFilters](/help/implement/vars/config-vars/linkexternalfilters.md) variable exists, the external link must match at least one of the values set in this variable.
* Si no se cumple alguno de los requisitos anteriores, la visita no rellena este informe.
* Al igual que con todas las visitas de seguimiento de vínculos personalizados, la variable [pageName](/help/implement/vars/page-vars/pagename.md) se elimina de la solicitud de imagen para evitar la inflación en la métrica de vistas de página.
* Este informe puede verse en los formatos de tendencias y clasificación.
* Este informe puede utilizar un filtro de búsqueda para localizar artículos de línea específicos.
* Pueden crearse [desgloses](/help/analyze/reports-analytics/reports-customize/breakdowns.md) con cualquier otra variable.
