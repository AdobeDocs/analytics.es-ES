---
title: Solución de problemas de picos y caídas de datos
description: Conocer las posibles razones por las que puede ver incrementos o disminuciones drásticos en los informes de tendencias.
translation-type: ht
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: ht
source-wordcount: '855'
ht-degree: 100%

---


# Solución de problemas de picos y caídas de datos

A medida que el sitio recopila datos, hay muchos factores externos que pueden afectar drásticamente a la recopilación de datos o a la generación de informes. La siguiente es una lista de posibles motivos por los cuales determinadas variables o el tráfico general aumentan o disminuyen de forma considerable.

A medida que determina la causa y avanza hacia una resolución, puede medir el impacto del evento en los datos y determinar cómo desea proceder. Consulte la [página de información general](overview.md) para obtener más información.

## Caídas del tráfico

Las caídas del tráfico se clasifican en dos secciones: datos parciales y datos cero.

### Posibles causas de la ausencia total de datos (creación de informes de ceros)

* **Latencia del grupo de informes**: En ocasiones, un grupo de informes puede experimentar [latencia](../latency.md) debido a una serie de factores. Muchos de los problemas de latencia se resuelven en unas horas. Si le preocupa un grupo de informes específico, póngase en contacto con el servicio de atención al cliente de Adobe con la ID del grupo de informes correspondiente.
* **Eliminación de la implementación**: A veces, cuando una organización realiza cambios de implementación o reestructura su sitio, se pasa por alto la reimplementación de Analytics. Trabaje con los desarrolladores de su organización para volver a implementar el código en su sitio.
* **Problema de caché/interfaz de Analytics**: En raras ocasiones, la memoria caché de un explorador contiene datos no válidos que hacen que todos los informes devuelvan ceros. Borre las cookies y la memoria caché del explorador para resolver el problema. Si la eliminación de cookies o de la memoria caché no funciona, póngase en contacto con el servicio de atención al cliente con el informe y el intervalo de fechas que faltan; pueden duplicar el problema y proporcionar información adicional.
* **Disponibilidad de Analytics**: Compruebe [status.adobe.com](https://status.adobe.com/products/1173/es) para ver si hay algún problema con la recopilación o el procesamiento de datos.

### Posibles causas de la pérdida parcial de datos o la disminución del tráfico

* **Cambios de implementación**: Use el [depurador](/help/implement/validate/debugger.md) para comprobar que las dimensiones deseadas funcionan.
* **Se ha reducido el tráfico de referencia**: Si se elimina una publicidad tipo titular o un hipervínculo popular de otro sitio, puede causar una disminución drástica del tráfico. Haga un seguimiento de la dimensión [Dominios de referencia](/help/components/dimensions/referring-domain.md) desde antes y después de la colocación para buscar más información.
* **Problemas de rendimiento del sitio**: La distribución incorrecta del tráfico a través de equilibradores de carga o problemas con el servidor que aloja el sitio puede contribuir a una disminución del sistema de informes de Analytics. Trabaje con el equipo de su organización que administra la integridad y el estado del sitio para investigar cualquier problema de rendimiento potencial.
* **Cambios en la clasificación de búsqueda natural**: El tráfico puede disminuir potencialmente si otro sitio elimina la clasificación de búsqueda natural de algunas de sus palabras clave. Esta disminución puede ser especialmente evidente si el sitio ya no se encuentra en la primera página de resultados de búsqueda. Haga un seguimiento de la dimensión [Motores de búsqueda](/help/components/dimensions/search-engine.md) para buscar más información.
* **Cambios en la publicidad de PPC**: Cambiar los títulos y las descripciones de las campañas existentes puede afectar a la puntuación de calidad. En general, una puntuación de calidad alta significa que la palabra clave activa los anuncios en una posición más alta y con un coste por clic más bajo. Haga un seguimiento de la dimensión [Palabra clave de búsqueda: de pago](/help/components/dimensions/search-keyword.md) para buscar más información.

## Picos de tráfico

Los picos de tráfico se clasifican en dos secciones: cerca de los datos dobles y otras causas.

### Posibles causas de tener casi o exactamente el doble de los datos esperados

* **Varias solicitudes de imagen dentro de una implementación**: Si la implementación contiene más de una llamada al método [`t()`](/help/implement/vars/functions/t-method.md) por página, dobla de forma eficaz todos los datos recopilados. Use el depurador del sitio y observe si hay varias solicitudes de imagen para captar duplicados.
* **Archivos de fuentes de datos de duplicado cargados**: Si su organización utiliza [fuentes de datos](/help/import/c-data-sources/datasrc-home.md), un usuario de su organización puede cargar el mismo archivo dos veces a Adobe Analytics. Al realizar esta carga de duplicado, se dobla de forma eficaz esa información en la creación de informes, lo que provoca el pico de tráfico.

### Otras causas potenciales del aumento del tráfico

* **Arañas o bots**: Si observa un gran aumento repentino del tráfico, lo primero que hay que buscar es la posibilidad de una araña o un bot. La identificación de bots puede ser a veces complicada, ya que cada uno tiene su propia forma de ejecutar el código en el sitio. Cree un informe del Data Warehouse usando la IP como dimensión para ver qué direcciones provocan la mayor cantidad de tráfico. A continuación, puede utilizar las [reglas de BOT](/help/admin/admin/bot-removal/bot-rules.md) o una regla VISTA para eliminar el tráfico de bots de la futura creación de informes.
* **Campañas iniciadas**: Los esfuerzos de marketing, como las campañas por correo electrónico o la optimización de los motores de búsqueda, pueden causar potencialmente un pico de tráfico en el sitio. Haga un seguimiento de la dimensión [Código de seguimiento](/help/components/dimensions/tracking-code.md) para buscar más información. También puede ayudar ponerse en contacto con el equipo de marketing para asegurarse de que el pico fue intencional.
* **Causas del entorno o circunstanciales**: Si hay un día festivo o un evento circunstancial (un evento significativo donde el sitio es un recurso conocido, o los esfuerzos de marketing residuales de otras organizaciones), el tráfico puede aumentar. Dar con la causa exacta es difícil, ya que hay un número casi ilimitado de razones circunstanciales por las que el tráfico puede aumentar. Estas causas, sin embargo, son algunas de las más importantes de determinar para que su organización pueda aprovecharlas y tomar las decisiones comerciales correspondientes. La tendencia de la dimensión [Página](/help/components/dimensions/page.md) o [Remitente del reenvío](/help/components/dimensions/referrer.md) es probablemente el mejor lugar para empezar a determinar el origen del tráfico.

Si ninguna de las razones anteriores es la causa potencial del aumento o la disminución del tráfico en el sitio, póngase en contacto con el servicio de atención al cliente de Adobe. Pueden proporcionar asistencia para localizar el origen del pico o la caída de tráfico. Al crear el incidente, indique al agente cómo volver a crear un informe específico que ilustre claramente el pico o la caída.
