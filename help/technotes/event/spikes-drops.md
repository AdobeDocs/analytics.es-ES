---
title: Solución de problemas de picos y caídas de datos
description: Conocer las posibles razones por las que puede ver incrementos o disminuciones drásticos en los informes de tendencias.
translation-type: tm+mt
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 2%

---


# Solución de problemas de picos y caídas de datos

A medida que el sitio recopila datos, hay muchos factores externos que pueden afectar drásticamente a la recopilación de datos o a la generación de informes. A continuación se muestra una lista de posibles explicaciones sobre por qué ciertas variables o el tráfico general aumentan o disminuyen de forma drástica.

A medida que determina la causa y avanza hacia una resolución, puede medir el impacto del evento en los datos y determinar cómo desea proceder. See the [overview page](overview.md) for more information.

## Caídas del tráfico

Las caídas del tráfico se clasifican en dos secciones: datos parciales y cero datos.

### Posibles causas de la ausencia total de datos (ceros sistemas de informes)

* **Latencia** del grupo de informes: En ocasiones, un grupo de informes puede experimentar [latencia](../latency.md) debido a una serie de factores. Muchos de los problemas de latencia se resuelven en unas horas. Si le preocupa un grupo de informes específico, póngase en contacto con el servicio de atención al cliente de Adobe con la ID del grupo de informes correspondiente.
* **Eliminación** de la implementación: A veces, cuando una organización realiza cambios de implementación o reestructuras en su sitio, se pasa por alto la reimplementación de Analytics. Trabaje con los desarrolladores de su organización para volver a implementar el código en su sitio.
* **Problema** de la interfaz y el almacenamiento en caché de Analytics: En raras ocasiones, la caché de un explorador contiene datos no válidos que hacen que todos los informes devuelvan ceros. Borre las cookies y la caché del explorador para resolver el problema. Si la eliminación de cookies/caché no funciona, póngase en contacto con el Servicio de atención al cliente y comuníquese con el informe y el intervalo de fechas que faltan; pueden duplicado del problema y proporcionar información adicional.
* **Disponibilidad** de Analytics: Compruebe [status.adobe.com](https://status.adobe.com/products/1173/) para ver si hay algún problema con la recopilación o el procesamiento de datos.

### Posibles causas de la pérdida parcial de datos o la disminución del tráfico

* **Cambios** de implementación: Use el [depurador](/help/implement/validate/debugger.md) para validar que funcionen las dimensiones deseadas.
* **Se ha reducido el tráfico** de referencia: Si se elimina un anuncio publicitario de titular o un hipervínculo popular de otro sitio, puede causar una disminución drástica del tráfico. Realice la tendencia de la dimensión [Dominios](/help/components/dimensions/referring-domain.md) de referencia desde antes y después de la colocación para buscar más información.
* **Problemas** de rendimiento del sitio: La distribución incorrecta del tráfico a través de equilibradores de carga o problemas con el servidor que aloja el sitio puede contribuir a una disminución del sistema de informes de Analytics. Trabaje con el equipo de su organización que administra la integridad y el estado del sitio para investigar cualquier problema de rendimiento potencial.
* **Cambios en la clasificación** de búsqueda natural: El tráfico puede disminuir si otro sitio elimina la clasificación de búsqueda natural de algunas de sus palabras clave. Esta disminución puede ser especialmente evidente si el sitio ya no se encuentra en la primera página de resultados de búsqueda. Haga un seguimiento de la dimensión de motores [de](/help/components/dimensions/search-engine.md) búsqueda para realizar más investigaciones.
* **Cambios en la publicidad** de PPC: Cambiar los títulos y las descripciones de las campañas existentes puede afectar a la puntuación de calidad. En general, una puntuación de alta calidad significa que la palabra clave activa las publicidades en una posición más alta y con un costo por clic más bajo. Eleve la tendencia de las palabras clave de [búsqueda: dimensión paga](/help/components/dimensions/search-keyword.md) para buscar más información.

## Picos de tráfico

Los picos de tráfico se clasifican en dos secciones: cerca de los datos de doble y otras causas.

### Posibles causas del doble cercano o exacto de los datos esperados

* **Varias solicitudes de imagen dentro de una implementación**: Si la implementación contiene más de una llamada [`t()`](/help/implement/vars/functions/t-method.md) de método por página, doble todos los datos recopilados. Use el depurador del sitio y observe si hay varias solicitudes de imagen para capturar duplicados.
* **Archivos de origen de datos de Duplicado cargados**: Si su organización utiliza orígenes [de](/help/import/c-data-sources/datasrc-home.md)datos, un usuario de su organización puede cargar el mismo archivo dos veces a Adobe Analytics. Al realizar esta carga de duplicado, se doble efectivamente esa información en sistema de informes, lo que provoca el pico de tráfico.

### Otras causas potenciales del aumento del tráfico

* **Arañas o bots**: Si se observa un gran aumento repentino del tráfico, lo primero que hay que buscar es la posibilidad de una araña o un bot. La identificación de bots puede ser a veces complicada, ya que cada uno tiene su propia manera de ejecutar el código en el sitio. Cree un informe de Data warehouse usando IP como dimensión para ver qué direcciones provocan la mayor cantidad de tráfico. A continuación, puede utilizar reglas [](/help/admin/admin/bot-removal/bot-rules.md) Bot o una regla de VISTA para eliminar el tráfico de bots del sistema de informes futuro.
* **campañas** iniciadas: Los esfuerzos de mercadotecnia, tales como campañas por correo electrónico o optimización de motores de búsqueda, pueden causar potencialmente un pico de tráfico en el sitio. Haga un seguimiento de la dimensión del código [de](/help/components/dimensions/tracking-code.md) seguimiento para realizar más investigaciones. También puede ayudar a ponerse en contacto con el equipo de mercadotecnia para asegurarse de que el pico fue intencional.
* **Causas** ambientales o circunstanciales: Si se produce un feriado o un evento circunstancial (un evento significativo donde el sitio es un recurso conocido o los esfuerzos residuales de mercadotecnia de otras organizaciones), el tráfico puede aumentar en el sitio. La resolución de problemas de la causa exacta es difícil, ya que hay un número casi ilimitado de razones circunstanciales por las que el tráfico puede aumentar. Estas causas, sin embargo, son algunas de las más importantes para determinar, de modo que su organización pueda aprovecharlas y tomar las decisiones comerciales correspondientes. La tendencia de la dimensión [Página](/help/components/dimensions/page.md) o [Remitente del reenvío](/help/components/dimensions/referrer.md) es probablemente el mejor lugar para el inicio a la hora de determinar el origen del tráfico.

Si ninguna de las razones anteriores es causa potencial de aumento o disminución del tráfico en el sitio, póngase en contacto con el Servicio de atención al cliente de Adobe. Pueden proporcionar asistencia para localizar el origen del pico o la caída de tráfico. Al crear el incidente, indique al agente cómo volver a crear un informe específico que ilustra claramente el pico o la caída.
