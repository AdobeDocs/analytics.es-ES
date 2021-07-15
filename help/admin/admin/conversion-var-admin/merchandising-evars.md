---
title: eVars de comercialización y métodos de búsqueda de productos
description: Una profundización en los conceptos subyacentes a las eVars de comercialización y en cómo procesan y asignan los datos.
source-git-commit: 6f98366a58c7c249c474d9f4474faa1676cdf1ea
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 1%

---

# eVars de comercialización y métodos de búsqueda de productos

En este documento se explican los conceptos subyacentes a las eVars de comercialización, que procesan y asignan los datos de forma diferente a las eVars estándar. También explica cómo se relacionan las eVars de comercialización con los métodos de búsqueda de productos.

Aunque la mayoría de los sitios web comerciales tienen muchas formas de encontrar productos, Adobe considera que los siguientes son los métodos fundamentales de búsqueda de productos que todos los clientes minoristas deben rastrear en Adobe Analytics:

* Palabras clave de búsqueda interna
* Códigos de seguimiento de campaña internos
* Categorías de comercialización y exploración
* Vínculos de venta cruzada

A los efectos de este documento, asignemos algunas eVars a las soluciones de la siguiente manera:

* eVar2: Palabras clave de búsqueda interna
* eVar3: Códigos de seguimiento de campaña internos
* eVar4: Categorías de comercialización y exploración
* eVar5: Vínculos de venta cruzada

Podemos usar un eVar adicional para medir el rendimiento de todos los métodos de búsqueda de productos en relación mutua. Además de los métodos de búsqueda descritos anteriormente, el eVar incluye otros métodos de búsqueda en su comparación, como vínculos a páginas de detalles de productos de sitios web externos.

* eVar1: Métodos de búsqueda de productos

En lugar de configurar cualquiera de estas variables para que sean eVars estándar, configúrelas para que sean eVars de comercialización. El uso de eVars de comercialización permite asignar cualquier actividad exitosa a los valores capturados por las eVars en un nivel *por producto* en lugar de en un nivel *por visita/por pedido*. Este documento aclara la diferencia entre la asignación por producto y por pedido en todo.

Para demostrar cómo configurar estas variables, aquí tiene un ejemplo donde un visitante decide utilizar las &quot;sandals&quot; de búsqueda de palabras clave internas para encontrar un producto en el sitio. En la página de resultados de búsqueda de palabras clave, debe capturar los datos de al menos dos eVars:

* `eVar2` es igual a la palabra clave que se utilizó en la búsqueda (&quot;sandals&quot;)
* `eVar1` es igual al método de búsqueda de productos utilizado (&quot;búsqueda de palabras clave interna&quot;).

Cuando configura estas dos variables en función de estos valores específicos, sabe que el visitante está usando el término de búsqueda de palabras clave internas &quot;sandals&quot; para encontrar un producto. Al mismo tiempo, sabe que el visitante no está usando los otros métodos de búsqueda de productos para encontrar productos (por ejemplo, el visitante no está navegando por categorías de productos exactamente al mismo tiempo que realiza una búsqueda de palabras clave). Para garantizar que se realice la asignación adecuada por producto, estos métodos no utilizados no deben obtener crédito para encontrar un producto que se haya encontrado mediante una búsqueda de palabras clave interna. Por lo tanto, debe insertar lógica en el código (como AppMeasurement, AEP Web SDK, etc.) que establezca automáticamente las eVars asociadas con estos otros métodos de búsqueda en un valor &quot;método de no búsqueda&quot;.

Por ejemplo, cuando un usuario busca productos utilizando la palabra clave &quot;sandals&quot;, la lógica del código de Analytics debe establecer las variables iguales a las siguientes en la página de resultados de búsqueda de palabras clave internas:

* eVar2=&quot;sandals&quot;: la palabra clave &quot;sandals&quot; se utilizó en la búsqueda de palabras clave interna
* eVar1=&quot;búsqueda de palabras clave interna&quot;: se utilizó el método de búsqueda &quot;búsqueda de palabras clave internas&quot;
* eVar3=&quot;campaña no interna&quot;: no se utilizó una campaña interna para acceder a la página de resultados de la búsqueda
* eVar4=&quot;non-browse&quot;: no se accedió a una categoría Examinar en la página de resultados de búsqueda
* eVar5=&quot;non-cross-sell&quot;: no se hizo clic en un vínculo de venta cruzada en la página de resultados de la búsqueda

## Configuración de eVars de comercialización

Antes de continuar con el ejemplo de &quot;sandals&quot;, aquí están los diferentes ajustes que puede usar con las eVars de comercialización.  La siguiente captura de pantalla proviene del Administrador del grupo de informes. Para acceder a él, vaya a Analytics > Administración > Grupos de informes > Editar configuración > Conversión > Variables de conversión > Agregar nuevo > Activar comercialización.

![](assets/merch-evars1.png)

Las secciones debajo de la tabla contienen más detalles sobre esta configuración.

| Configuración | Descripción |
|--- | --- |
| Nombre | Nombre o la dimensión de informes a la que está destinada la variable. Si `eVar1` está pensado para capturar los métodos de búsqueda de productos, el campo Nombre de `eVar1` debe configurarse como &quot;Métodos de búsqueda de productos&quot;. |
| Comercialización | El tipo de sintaxis que se utilizará para capturar los valores de eVar de comercialización |
| Asignación | Ayuda determina el valor del eVar de comercialización que debe recibir crédito cuando se produce un evento exitoso. |
| Caduca después | Determina cuándo los enlaces de productos y eVares de comercialización existentes ya no deben estar en vigor. |
| Tipo | Tipo de datos que se recopilan en el eVar de comercialización |
| Evento de enlace de comercialización | Eventos que determinan cuándo un producto debe enlazarse a un valor de eVar de comercialización |
| Restablecer | Un déclencheur que restablecerá todos los datos del back-end para el eVar en ese momento |
| Habilitar la comercialización | Un indicador que debe establecerse en &quot;Habilitado&quot; para que el eVar pase de ser un eVar estándar a un eVar de comercialización |

### Comercialización

Esta opción no está disponible para eVars normales. La configuración [!UICONTROL Marketing] permite elegir [!UICONTROL Sintaxis de la variable de conversión] o [!UICONTROL Sintaxis del producto] como método para capturar el valor del eVar de comercialización.

**[!UICONTROL La]** sintaxis de la variable de conversión significa que el valor de eVar se establece en su propia variable. Por ejemplo, con Sintaxis de la variable de conversión, el valor `eVar1` de &quot;búsqueda de palabra clave interna&quot; se establece de la siguiente manera dentro del código de página (o el código AppMeasurement, el código SDK web de AEP, etc.):

`s.eVar1="internal keyword search";`

Sin embargo, con **[!UICONTROL Sintaxis del producto]**, el eVar se configura únicamente dentro de la variable de productos de Adobe Analytics. La variable de productos de Analytics se divide en seis partes diferentes por producto:

`s.products="[category];[productID];[quantity];[revenue];[events];[eVars]"`

*  La categoría es una función obsoleta y ya no se recomienda como opción viable para realizar un seguimiento del rendimiento de la categoría del producto.  Su mera existencia demuestra por qué en la mayoría de las implementaciones de la variable products, un punto y coma simple precede a la parte productID del valor de la variable.
*  La cantidad y los   ingresos son útiles cuando se realiza un seguimiento de la compra de un producto.
*  Los eventos son útiles para registrar valores de eventos incrementales o monetarios personalizados que no están pensados para ser contabilizados como ingresos (como envíos, descuentos, etc.)

Las eVars de comercialización configuradas para usar Sintaxis del producto se establecen dentro de la parte final de la variable products. Por ejemplo, supongamos que un visitante utilizó una búsqueda de palabras clave interna para encontrar el ID de producto &quot;12345&quot;. La forma basada en la sintaxis del producto para configurar eVar1 en este ejemplo tendría este aspecto:

`s.products=";12345;;;;eVar1=internal keyword search";`

Observe que todavía tenemos marcadores de posición delimitados por punto y coma para las partes de cantidad, ingresos y evento de la variable products.  Sin estos marcadores de posición, se ignoraría completamente la configuración `eVar1` de la búsqueda interna de palabras clave.

### Asignación

El término &quot;Asignación&quot; para eVars de comercialización no es correcto, especialmente para eVars de comercialización que utilizan Sintaxis de variables de conversión. Todas las eVars que utilizan sintaxis estándar pueden tener su propia configuración de asignación individual, pero las eVars de comercialización con Sintaxis de variables de conversión usan únicamente una configuración de asignación de &quot;Más reciente (último)&quot;, independientemente de la configuración de asignación que muestre el Administrador de grupos de informes.

Para comprender lo que hace esta configuración, debe comprender la diferencia entre la asignación de eVar y el enlace de eVar de comercialización.  Para las eVars de comercialización, el &quot;Enlace del eVar de comercialización&quot; podría considerarse un nombre más adecuado para esta configuración de &quot;Asignación&quot;.
Siempre que se recopila cualquier eVar con sintaxis estándar de una solicitud de imagen, los servidores de procesamiento de Adobe Analytics insertan datos en otra columna de base de datos, denominada columna post_evar, junto con la columna eVar normal.  Dado que las eVars están pensadas para ser persistentes (es decir, que caducan en algún momento más allá de la visita actual en la mayoría de los casos), los servidores configurarán esta columna post_evar en cada solicitud de imagen posterior y la establecerán igual al último valor pasado a su eVar correspondiente. Para las eVars estándar (es decir, que no sean de comercialización), cuando se produce un evento de éxito, Adobe Analytics utiliza la columna post_evar en lugar de la columna eVar normal para determinar el valor de eVar que debe recibir crédito por el evento.
Para las eVars estándar (es decir, que no sean de comercialización), la configuración de Asignación determina si el primer o el último valor de eVar que se recopiló durante un periodo determinado se insertará en la columna post_evar. Si la configuración de Asignación para un eVar estándar es igual a &quot;Valor original (primero)&quot;, el primer valor de eVar recopilado del visitante se insertará en la columna post_evar para todas las solicitudes de imagen posteriores.  Esto continuará para todas las solicitudes futuras enviadas desde el explorador de este visitante hasta que el eVar caduque según la configuración &quot;Caduca después&quot;.\
Si la configuración de Asignación de un eVar estándar es igual a &quot;Más reciente (último)&quot;, el valor de eVar más reciente recopilado del visitante se rellenará en la columna post_evar para todas las solicitudes de imagen posteriores. La asignación &quot;Más reciente (último)&quot; implica que el valor post_evar cambiará cada vez que su eVar correspondiente se establezca en un nuevo valor en cualquier solicitud de imagen.  La asignación &quot;Valor original (primero)&quot; implica que la columna post_evar no cambiará entre visitas individuales aunque su eVar correspondiente pueda establecerse en un valor diferente en una solicitud de imagen futura.
Como se mencionó anteriormente, todas las eVars de comercialización con Sintaxis de variables de conversión solo tienen una asignación &quot;Más reciente (último)&quot; (según la definición de eVar estándar).  Por lo tanto, necesito explicar qué significa realmente la configuración de &quot;Asignación&quot; para las eVars de comercialización.  Como se ha insinuado anteriormente, esta configuración no determina qué valores se insertan en la columna post_evar a medida que un visitante continúa usando el sitio.  En su lugar, la configuración de Asignación para eVars de comercialización determina qué valor de eVar se enlaza a un producto y cómo se asignan dichos productos


