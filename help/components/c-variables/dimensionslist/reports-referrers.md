---
title: Referentes
description: Muestra la dirección URL de la visita anterior, si dicha visita se encuentra fuera del sitio.
translation-type: tm+mt
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# Referentes

La dimensión &#39;Remitente del reenvío&#39; muestra la dirección URL de donde provienen los visitantes antes de llegar al sitio. Por ejemplo: si un visitante hace clic en un vínculo desde `example.com/example-page.html` y llega a su sitio, `example.com/example-page.html` es el remitente del reenvío si no se define como parte de su dominio.

Esta dimensión requiere que configure los filtros [URL](/help/admin/admin/internal-url-filter-admin.md)internos del grupo de informes. Si no configura filtros de URL internas, Adobe Analytics considera que todos los dominios son internos del sitio.

## Propiedades de dimensión

* Esta dimensión utiliza la asignación más reciente de forma predeterminada.
* Esta dimensión caduca después de la visita de forma predeterminada.
* Esta dimensión está sujeta al límite único de 500.000 antes de agrupar los valores de dimensión en (Poco tráfico). El almacén de datos no tiene un límite único.
* Si no hay ningún valor de remitente del reenvío para una métrica, se agrupa en `Typed/Bookmarked`.
* Esta dimensión se configura generalmente en la primera visita individual de la visita, pero puede establecerse a mitad de la visita.

## Resolución de problemas

**P: ¿Por qué veo`googleusercontent.com`como un valor de dimensión?**

A: [Google](https://about.google/) utiliza el dominio `googleusercontent.com` para el contenido alojado. El contenido alojado incluye:

* **Páginas** en caché: Las arañas de Google rastrean constantemente la web y guardan páginas web en caso de que se desconecten o no estén disponibles. Estas páginas en caché están disponibles al lado de todos los resultados de búsqueda haciendo clic en el vínculo &quot;En caché&quot; de una de las páginas de resultados de búsqueda de Google. Cuando un usuario hace clic en este vínculo y luego mira el contenido original del sitio, `googleusercontent.com` aparece como su dominio de referencia. Estas páginas tienen el subdominio `webcache.googleusercontent.com`.
* **Páginas** traducidas: Google oferta un servicio de traducción robusto y conveniente. Al ver un sitio que utiliza este servicio, se origina desde `googleusercontent.com`. La dimensión remitente del reenvío muestra las direcciones URL de este dominio si el usuario hace clic en un vínculo para volver al contenido original. Estas páginas tienen el subdominio `translate.googleusercontent.com`.
