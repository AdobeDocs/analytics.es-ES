---
title: eVars de comercialización y métodos de búsqueda de productos
description: Una profundización en los conceptos subyacentes a las eVars de comercialización y en cómo procesan y asignan los datos.
feature: Admin Tools
role: Admin
exl-id: 9e1a39aa-451f-49bb-8e39-797b6bbd5499
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '5279'
ht-degree: 95%

---

# eVars de comercialización y métodos de búsqueda de productos

En este documento detallado se explican los conceptos subyacentes a las eVars de comercialización, que procesan y asignan los datos de forma diferente a las eVars estándar. También se explica cómo se relacionan las eVars de comercialización con los métodos de búsqueda de productos.

## Información general

El uso de eVars de comercialización permite asignar cualquier actividad exitosa a los valores capturados por las eVars en un nivel *por producto* en lugar de hacerlo en un nivel de *por visita/por pedido.*

Aunque la mayoría de los sitios web de comercios ofrecen muchas formas de encontrar productos, Adobe considera que los siguientes son los métodos fundamentales de búsqueda de productos que todos los clientes minoristas deben rastrear en Adobe Analytics:

* Palabras clave de búsqueda interna
* Códigos de seguimiento internos de Campaign
* Categorías de comercialización y exploración
* Vínculos de venta cruzada

A los efectos de este documento, asignemos algunas eVars a las soluciones de la siguiente manera:

* eVar2: Palabras clave de búsqueda interna
* eVar3: Códigos de seguimiento internos de Campaign
* eVar4: Categorías de comercialización y exploración
* eVar5: Vínculos de venta cruzada

Podemos usar una eVar adicional para medir el rendimiento de todos los métodos de búsqueda de productos en comparación con los demás. Además de los métodos de búsqueda descritos anteriormente, la eVar incluye otros métodos de búsqueda en su comparación, como vínculos a páginas de detalles de productos de sitios web externos.

* eVar1: Métodos de búsqueda de productos

En lugar de configurar cualquiera de estas variables para que sean eVars estándar, configúrelas para que sean eVars de comercialización.

Para demostrar cómo configurar estas variables, aquí tiene un ejemplo en el que un visitante decide utilizar la palabra clave de búsqueda interna “sandalias” para encontrar un producto en el sitio. En la página de resultados de búsqueda de palabras clave, debe capturar los datos de al menos dos eVars:

* `eVar2` es igual a la palabra clave que se utilizó en la búsqueda (sandalias)
* `eVar1` es igual al método de localización de productos utilizado (búsqueda de palabras clave interna).

Cuando establece estas dos variables en función de estos valores específicos, sabe que el visitante está usando el término de búsqueda de palabra clave interna “sandalias” para encontrar un producto. Al mismo tiempo, sabe que el visitante no está usando los otros métodos de búsqueda de productos para encontrarlos (por ejemplo, el visitante no está navegando a través de las categorías de productos al mismo tiempo que realiza una búsqueda de palabras clave). Para garantizar que se realice la asignación adecuada por producto, estos métodos no utilizados no deben obtener crédito por encontrar un producto que se haya encontrado mediante una búsqueda de palabras clave interna. Por lo tanto, debe insertar una lógica en el código (como AppMeasurement, Adobe Experience Platform Web SDK, etc.) que establezca automáticamente las eVars asociadas con estos otros métodos de búsqueda iguales a un valor de método de no localización.

Por ejemplo, cuando un usuario busca productos utilizando la palabra clave “sandalias”, la lógica del código de Analytics debe establecer las variables iguales a las siguientes en la página de resultados de búsqueda de la palabra clave interna:

* eVar2=&quot;sandalias&quot;: la palabra clave “sandalias” se utilizó en la búsqueda de palabra clave interna
* eVar1=&quot;internal keyword search&quot;: se utilizó el método de localización “búsqueda de palabra clave interna”
* eVar3=&quot;non-internal campaign&quot;: no se utilizó una campaña interna para acceder a la página de resultados de la búsqueda
* eVar4=&quot;non-browse&quot;: no se accedió a una categoría de examinar en la página de resultados de la búsqueda
* eVar5=&quot;non-cross-sell&quot;: no se hizo clic en un vínculo de venta cruzada en la página de resultados de la búsqueda

## Configuración de eVars de comercialización

Estas son las diferentes configuraciones que puede usar con las eVars de comercialización. La siguiente captura de pantalla proviene del Administrador del grupo de informes. Para acceder, vaya a [!UICONTROL Analytics] > [!UICONTROL Administración] > [!UICONTROL Grupos de informes] > [!UICONTROL Editar configuración] > [!UICONTROL Conversión] > [!UICONTROL Variables de conversión] > [!UICONTROL Añadir nuevo] > [!UICONTROL Habilitar la comercialización].

![eVar de comercialización](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/assets/merch-evars1.png)

Encontrará más información sobre esta configuración en las secciones debajo de la tabla.

| Configuración | Descripción |
|--- | --- |
| Nombre | El nombre o la dimensión de la creación de informes a la que se pretende asociar la variable. Si `eVar1` está pensado para capturar los métodos de búsqueda de productos, el campo Nombre de `eVar1` debe configurarse como Métodos de búsqueda de productos. |
| Comercialización | El tipo de sintaxis que se utilizará para capturar los valores de las eVar de comercialización |
| Asignación | Ayuda a determinar el valor de la eVar de comercialización que debe recibir crédito cuando se produce un evento de éxito. |
| Caduca después | Determina cuándo deben de dejar de estar vigentes las vinculaciones de productos y eVar de comercialización existentes. |
| Tipo | Tipo de datos que se recopilan en la eVar de comercialización |
| Evento de enlace de comercialización  | Eventos que determinan cuándo un producto debe estar vinculado a un valor de eVar de comercialización |
| Restablecer | Un activador que restablecerá todos los datos del back-end para la eVar en ese momento |
| Habilitar la comercialización | Un indicador que debe establecerse en Habilitado para que la eVar pase de ser una eVar estándar a una eVar de comercialización |

### Habilitar la comercialización

Cuando la opción Habilitar comercialización está habilitada, todas las opciones que se describen a continuación aparecen en el Administrador del grupo de informes. Cuando la opción Habilitar comercialización está deshabilitada, solo está disponible la configuración de eVar estándar.

### Comercialización

Esta opción no está disponible para eVars estándar. La configuración de [!UICONTROL Comercialización] permite elegir entre [!UICONTROL Sintaxis de la variable de conversión] o [!UICONTROL Sintaxis del producto] como método para capturar el valor de la eVar de comercialización.

La **[!UICONTROL Sintaxis de la variable de conversión]** significa que el valor de la eVar se establece en su propia variable. Por ejemplo, con Sintaxis de variables de conversión, el valor `eVar1` de búsqueda de palabras clave interna se establece de la siguiente manera dentro del código de página (o el código AppMeasurement, el código Adobe Experience Platform Web SDK, etc.):

`s.eVar1="internal keyword search";`

Sin embargo, con **[!UICONTROL Sintaxis del producto]**, la eVar se configura únicamente dentro de la variable products de Adobe Analytics. La variable products de Analytics se divide en seis partes diferentes por producto:

`s.products="[category];[name];[quantity];[revenue];[events];[eVars]"`

* [!UICONTROL Categoría] y [!UICONTROL Nombre] identifican el producto especificado.
* [!UICONTROL Cantidad] e [!UICONTROL Ingresos] son útiles cuando se realiza un seguimiento de la compra de un producto.
* Los [!UICONTROL Eventos] son útiles para registrar valores de eventos incrementales o monetarios personalizados que no están pensados para ser contabilizados como ingresos (como envíos, descuentos, etc.)

Las eVars de comercialización configuradas para usar Sintaxis del producto se establecen dentro de la parte final de la variable products. Por ejemplo, supongamos que un visitante utilizó una búsqueda de palabras clave interna para encontrar el ID de producto 12345. La forma basada en la Sintaxis del producto para configurar eVar1 en este ejemplo tendría este aspecto:

`s.products=";12345;;;;eVar1=internal keyword search";`

Observe que todavía tenemos marcadores de posición delimitados por punto y coma para las partes de cantidad, ingresos y evento de la variable products.  Sin estos marcadores de posición, se ignoraría completamente la configuración `eVar1` de la búsqueda de palabras clave interna.

### Asignación

El término Asignación de las eVars de comercialización puede resultar confuso, especialmente en el caso de las eVars de comercialización que utilizan Sintaxis de variables de conversión. Todas las eVars estándar pueden tener su propia configuración de asignación individual. Sin embargo, las eVars de comercialización con Sintaxis de variables de conversión solo usan la configuración de asignación “Más reciente (último)”, independientemente de lo que muestre la configuración de asignación en el Administrador del grupo de informes.

Comprender lo que hace esta configuración significa comprender la diferencia entre la asignación de la eVar y el enlace de la eVar de comercialización. Para las eVars de comercialización, Enlace de la eVar de comercialización es un nombre más apropiado para esta configuración de Asignación.

#### Configuración de asignación de eVar estándar

Siempre que se recopila cualquier eVar con sintaxis estándar de una solicitud de imagen, los servidores de procesamiento de Adobe Analytics insertan datos en otra columna de base de datos, denominada columna `post_evar`. Dado que las eVars están pensadas para ser persistentes (caducan en algún momento más allá de la visita actual en la mayoría de los casos), los servidores establecen esta columna `post_evar` en cada solicitud de imagen posterior. Se establece igual al último valor pasado a su eVar correspondiente. En el caso de las eVars estándar, cuando se produce un evento de éxito, Adobe Analytics utiliza la columna `post_evar` en lugar de la columna de eVar normal para determinar el valor de eVar que debe recibir crédito por el evento.

Para las eVars estándar, la configuración de Asignación determina si el primer o el último valor de eVar que se recopiló durante un periodo determinado se insertará en la columna `post_evar`. Si la configuración de Asignación para una eVar estándar es igual a Valor original (primero), el primer valor de eVar recopilado del visitante se inserta en la columna `post_evar` para todas las solicitudes de imagen posteriores. Esto continúa para todas las solicitudes futuras enviadas desde el explorador de este visitante hasta que la eVar caduque según la configuración Caduca después.

Si la configuración de Asignación de una eVar estándar es igual a “Más reciente (último)”, el valor de la eVar más reciente recopilado del visitante se rellena en la columna `post_evar` para todas las solicitudes de imagen posteriores. La asignación “Más reciente (último)” implica que el valor `post_evar` cambia cada vez que su eVar correspondiente se establece en un nuevo valor en cualquier solicitud de imagen. La asignación Valor original (primero) implica que la columna `post_evar` no cambia entre visitas individuales aunque su eVar correspondiente pueda establecerse en un valor diferente en una solicitud de imagen futura.

#### Configuración de asignación (enlace) de la eVar de comercialización

Como se mencionó anteriormente, todas las eVar de comercialización con Sintaxis de variables de conversión solo tienen una asignación “Más reciente (último)”.  Por lo tanto, la configuración de Asignación para eVars de comercialización no determina qué valores se insertan en la columna post_evar mientras un visitante sigue usando el sitio. En su lugar, esta configuración determina qué valor de eVar se vincula a un producto y cómo dichos productos asignan sus eventos de éxito de nuevo a los valores de eVar a los que están vinculados.

Lo siguiente ocurre cuando la configuración de asignación (enlace) de una eVar de comercialización se establece en “Valor original” (primero): todos los productos que se establecen junto a la columna post_evar y que no se hayan enlazado previamente a la eVar “preprocesada” correspondiente de la columna post_evar se enlazarán al valor contenido en la columna post_evar. Este enlace entre el valor de la eVar y el producto nunca cambiará hasta que la eVar caduque según el valor “Caduca después”, en la configuración del grupo de informes.

Cada vez que una solicitud de imagen cumple los criterios que, de lo contrario, enlazarían un producto ya enlazado con el valor de eVar establecido más recientemente, la configuración Valor original (primero) obliga a los servidores de recopilación de datos de Adobe Analytics a ignorar cualquier intento posterior de hacerlo. Lo contrario sucede con las eVars de comercialización cuya configuración de Asignación (enlace) tiene el valor &quot;Más reciente (último)&quot; Cada vez que una solicitud de imagen cumple los criterios que unen un producto a una eVar de comercialización, el producto se enlazará (y se volverá a enlazar) al valor más reciente pasado a la eVar o al valor que (siempre) se encuentra en la columna `post_evar`.

Como se ha mencionado anteriormente, las eVars de comercialización permiten asignar eventos de éxito a los valores de eVar por producto, en lugar de hacerlo por visita/por pedido. Por lo tanto, cada vez que un producto enlazado tiene un evento de éxito (como una compra o adición al carro de compras) asociado a él, el evento de éxito le da crédito tanto al producto como a los valores de eVar de comercialización a los que está enlazado el producto en ese momento.

### Caduca después

La configuración de caducidad de un eVar de comercialización le permite elegir

* Cuando los enlaces de producto/eVar deben caducar, y

* Cuando la columna post_evar ya no debe rellenarse automáticamente después de pasar un eVar a una solicitud de imagen.

La caducidad de un eVar puede producirse cuando se registra un evento de éxito o cuando transcurre un período de tiempo determinado. Adobe Analytics solo permite una configuración de caducidad a la vez por eVar.

Para el método de localización de productos, la práctica recomendada para configurar la caducidad de un eVar de comercialización es establecerlo en

* Cantidad de tiempo que un producto se encuentra en el carro de compras de un sitio antes de que el sitio lo elimine automáticamente de este (por ejemplo, 14 días, 30 días, etc.)
* O cuando se produce el evento de compra.

Con cualquiera de las opciones, los productos que compre un visitante tienen el crédito de pedido/unidad/ingresos asignado a los valores de eVar de comercialización a los que estaban enlazados los productos en ese momento.

### Tipo

La configuración del tipo de eVar determina qué tipo de datos se inserta en la eVar. En la mayoría de los casos, este valor debe ser igual a Texto. El uso de Contador para un eVar de comercialización es poco frecuente. Sin embargo, se podría usar Contador para asignar el éxito a los valores de eVar de contador por producto.  Abordar soluciones con un tipo de contador está fuera del ámbito de este documento.

### Evento de enlace de comercialización 

La configuración Evento de enlace de comercialización permite especificar las condiciones para que un producto se enlace al valor de una eVar de comercialización. Estas condiciones se limitan a la activación de eventos de éxito específicos o solo eVars; la activación de variables de tráfico (por ejemplo, props) no afecta a los enlaces de comercialización.

Tenga en cuenta que la configuración de Evento de enlace de comercialización puede enlazar un producto a un valor de eVar a través de más de un evento. Ejemplos:

* Mediante un evento de vista de producto
* Mediante un evento de adiciones al carro de compras
* Mediante un evento de compra

De forma predeterminada, la configuración vincula un producto a un valor de eVar de comercialización siempre que cualquier otro evento/eVar (comercialización o estándar) esté contenido en la misma solicitud de imagen que el producto.

### Restablecer

La configuración Restablecer le permite “caducar” inmediatamente todos los valores de eVar de todos los visitantes que actualmente tengan un valor `post_evar` en la base de datos back-end de Adobe Analytics. También elimina todos los enlaces actuales entre productos y eVar.

>[!IMPORTANT]
>Adobe no recomienda utilizar la configuración Restablecer a menos que tenga la intención de volver a empezar la eVar con una hoja de datos completamente limpia desde el momento en que se realiza el restablecimiento.

## ¿Qué configuración debe utilizar?

Entre las muchas combinaciones de configuración disponibles, es posible que se pregunte cuál es la práctica recomendada.

Si desea enlazar la búsqueda de palabras clave interna al ID de producto 12345, la variable de productos se configuraría de la siguiente manera:

`s.products=";12345;;;;eVar1=internal keyword search";`

Cualquier evento de éxito (compras, adiciones al carro de compras, etc.) que se capture al mismo tiempo que el ID de producto 12345 se acreditará tanto al ID de producto 12345 como al valor de eVar1 de “búsqueda de palabra clave interna”. La única manera en que un valor de eVar1 diferente obtenga crédito por los eventos de éxito asociados con el ID de producto 12345 es que eVar1 se establezca posteriormente en un valor diferente dentro de la variable de productos (junto con el ID de producto 12345).

Por ejemplo:

```js
s.products=";12345;;;;eVar1=internal campaign";
```

Esta configuración de variable cambia el enlace del ID de producto 12345 del valor de eVar1 de “búsqueda de palabra clave interna” al valor de eVar1 de “campaña interna”. Además, este cambio de enlace se produce cuando el eVar está configurado para utilizar Sintaxis del producto y la configuración Asignación (enlace) de “Más reciente (último)”. Si la configuración Asignación (enlace) se estableciera en “Valor original (primero)”, establecer eVar1 en “campaña interna” junto con el ID de producto 12345 no devolvería el ID de producto 12345 al valor de eVar1 de “campaña interna”. En su lugar, el enlace permanecería con el valor enlazado originalmente: “búsqueda de palabra clave interna”.

### Desafíos del uso de Sintaxis del producto

Sin una planificación cuidadosa, pueden surgir varios problemas al usar Sintaxis del producto. Veamos el caso de usar varias eVars para rastrear los métodos de búsqueda de productos en el sitio web. En este caso, cada eVar de método de localización de productos individual debe configurarse a la vez para dar un crédito de eVar de método de localización en particular (y las demás eVars de método de localización no tienen crédito). La Sintaxis del producto se puede utilizar en estos casos, pero el código resultante para implementar es más complicado.

Si usamos nuestro ejemplo de sandalias y lo adaptamos para usar Sintaxis del producto (suponiendo que el visitante encontró un producto con el ID sandalia123 utilizando la palabra clave sandalias), la variable de productos resultante debe configurarse de la siguiente manera:

`s.products=";sandal123;;;;eVar2=sandals|eVar1=internal search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";`

Aunque la sintaxis de la variable products es larga en este ejemplo, enlazará cada uno de los valores de eVar vistos con el ID del producto sandalia123. A partir de ese momento, cualquier evento de éxito (por ejemplo, compras o adiciones al carro de compras) que se capture al mismo tiempo que el producto sandalia123 se acreditará a los valores de eVar que se vincularon por última vez al producto.  Este ejemplo de código muestra si se realiza una compra de 1 unidad del producto sandalia123 (por 79,95 dólares) después de que las eVars anteriores se hayan enlazado al producto sandalia123:

```js
s.products=";sandal123;1;79.95";
s.events="purchase";
```

Los siguientes valores tendrían 1 pedido, 1 unidad y 79,95 $ de ingresos atribuidos a ellos:

* Valor de eVar2 de “sandalias”
* Valor de eVar1 de “búsqueda de palabras clave interna”
* Valor de eVar3 de “campaña no interna”
* Valor de eVar4 de “sin examinar”
* Valor de eVar5 de “no realizar venta cruzada”

Esto es una atribución correcta, lo que no es un problema. En cambio, el principal dilema con este enfoque es determinar cómo y cuándo configurar las eVars del método de localización de productos.

En la mayoría de los casos con Sintaxis del producto, las eVars del método de localización del producto tendrían que configurarse en una página de detalles del producto en lugar de en la página en la que se utilizó realmente el método de localización (por ejemplo, en la página de resultados de búsqueda de palabra clave, la página de navegación, la página de destino de la campaña interna, etc.). Es razonable suponer que un producto no se ha encontrado realmente hasta que un visitante interactúa con un producto hasta cierto punto. De este modo, estas eVars (que utilizan Sintaxis del producto) no deben configurarse en la página del método de localización porque en estas páginas se muestran (normalmente) varios productos. Queremos enlazar el valor del método de localización únicamente a los productos con los que ha interactuado el visitante.

Además, mientras ve una página de método de localización, los visitantes pueden hacer clic en un vínculo que les lleva a una página de detalles de producto para particulares o agregar un producto para particulares al carro de compras directamente desde la página de método de localización. Con nuestro ejemplo de palabra clave de búsqueda &quot;sandalias&quot;, si un visitante agrega el producto sandalia123 al carro de compras directamente desde una página de resultados de búsqueda de palabra clave, el código para capturar el aditivo al carro de compras (a través del evento onClick del botón Agregar al carro de compras, etc.) tendría que generarse dinámicamente en el momento en que se produce la adición al carro de compras o &quot;cifrarse&quot; directamente a través del código de página o un sistema de administración de etiquetas.  Independientemente, el código que se active en tales casos tendría este aspecto:

```js
s.linkTrackVars="products,events";
s.linkTrackEvents=s.events="scAdd";
s.products=";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
s.tl(true,"o","Cart Add")
```

Este código vincula correctamente los valores de eVar que se han visto arriba con el producto sandalia123. Sin embargo, para establecer correctamente estos valores cuando se produce el evento de clic, el desarrollador debe hacer esto:

* Agregue lógica del lado del servidor a la página de resultados de búsqueda que determina los valores que deben insertarse en las eVars del método de localización de productos, y
* Ensamble toda la variable products vista arriba sin errores de sintaxis.

Además, si un visitante decide buscar el producto haciendo clic en un vínculo a la página de detalles del producto, el desarrollador debe tener en cuenta esto:

* Pase los detalles del método de localización de productos (como se ha visto arriba) desde la página de métodos de localización a la página de detalles del producto, y
* Vuelva a crear el mismo valor de variable de productos a partir de los artículos que se acaban de pasar desde la página anterior.

### Dónde resulta útil la sintaxis del producto

La sintaxis del producto sigue siendo útil cuando

* Se interactúa con varios productos con los mismos ID de producto al mismo tiempo, y
* Las eVars que se enlazan a estos productos deben tener diferentes valores por ID de producto.

Por ejemplo, muchos productos de ropa tienen SKU secundarias, que designan el tamaño, el color, el estilo y cualquier otro atributo. Estos atributos separan un solo producto secundario de otros productos que pertenecen al mismo producto principal. Supongamos que decide comprar una camiseta azul mediana y una camiseta roja grande. Supongamos que ambas tienen el ID de producto principal camiseta123 y que `eVar10` se ha configurado para capturar SKU secundarias. Las variables configuradas en la página de confirmación de compra se establecerían de la siguiente manera:

```js
s.events="purchase";
s.products=";tshirt123;1;20;;eVar10=tshirt123-m-blue,;tshirt123;1;20;;eVar10=tshirt123-l-red";
```

En este caso, tanto los valores `eVar10` (childSKU) de camiseta123-m-azul como camiseta123-l-roja obtienen crédito por la compra de sus respectivas instancias del ID de producto camiseta123.

### Desafíos con la asignación “Más reciente”

Puede encontrar problemas adicionales utilizando la configuración Asignación (enlace) de “Más reciente (último)”. En muchas experiencias de navegación web, los visitantes vuelven a encontrar un producto que ya han visto o agregado al carro de compras. Esto suele ocurrir en una visita posterior o justo antes de que decidan completar una compra. Supongamos que durante su primera visita al sitio, un visitante encuentra el producto “sandalia123” a través de la búsqueda de la palabra clave “sandalias”. Inmediatamente lo añade al carro de compras desde la página de resultados de búsqueda de palabras clave. El código que captura la adición al carro de compras se configuraría de la siguiente manera:

```js
s.linkTrackVars="products,events";
s.linkTrackEvents=s.events="scAdd";
s.products=";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross";
```

Como resultado, cada uno de los valores de eVar que se ven en esta solicitud de imagen están enlazados al producto sandalia123.

Ahora, imaginemos que no compra el producto durante esta visita, pero regresa al sitio tres días después con el producto “sandalia123” aún en el carro de compras. El visitante desea obtener más información acerca del producto antes de realizar la compra. Pero, en lugar de usar una búsqueda de palabras clave para encontrarlo, navega por el sitio. Terminan en la sección de navegación de comercialización mujeres > zapatos > sandalias justo antes de “reencontrarse” con el producto. Cuando terminan “reencontrando” la página de detalles del producto para el producto sandalia123, las variables se configurarían de la siguiente manera (al cargar la página):

```js
s.events="prodView";
s.products=";sandal123;;;;eVar4=womens > shoes > sandals|eVar1=browse|eVar3=non-internal campaign|eVar2=non-search|eVar5=non-cross-sell";
```

Con la configuración Asignación (enlace) de “Más reciente (último)”, el producto “sandalia123” se vuelve a unir con valores de eVar completamente diferentes a los que estaba vinculado originalmente. Además, si el visitante completa la compra de la sandalia123, todo el crédito de compra se otorga a estos valores de eVar recién enlazados en lugar de a los valores enlazados originalmente.

La pregunta aquí es: “¿qué valores de eVar deben recibir crédito por la compra?” Recuerde que el visitante encontró inicialmente el producto sandalia123 con una búsqueda de palabras clave interna. Luego, lo agregaron al carro de compras directamente desde la página de resultados de búsqueda. Por lo tanto, el valor eVar1 de búsqueda de palabras clave interna (y el valor eVar2 de “sandalias”) debería obtener crédito por la compra. Sin embargo, la configuración Asignación (enlace) se estableció en “Más reciente (último)”. Por lo tanto, el valor eVar1 de examinar (y el valor eVar4 de mujer > zapatos > sandalias) obtiene el crédito de compra en su lugar. La razón es que fueron los últimos valores enlazados a sandalia123 antes de que el visitante completara la compra.

Una solución a este problema es cambiar la configuración de asignación (enlace) de la eVar de comercialización de “Más reciente (último)” a “Valor original (primero)”. De este modo, los valores de eVar originales enlazados al producto sandalia123 obtienen crédito cuando se realiza la compra, independientemente de cuántas veces el visitante “vuelva a encontrar” el producto.

Si el visitante agrega un producto al carro de compras, pero nunca lo compra, la caducidad de la eVar permite que se vincule un nuevo valor de método de localización al producto. La caducidad de la eVar debe coincidir con el tiempo que un sitio web permite que un producto permanezca en el carro de compras antes de que se elimine automáticamente.

### Uso de Sintaxis de la variable de conversión

Volvamos a la Sintaxis del producto frente a la pregunta Sintaxis de la variable de conversión. Adobe ha descubierto un método más sencillo para recopilar eVars de comercialización del método de localización de productos y enlazar sus valores a productos que los visitantes han encontrado: el uso de Sintaxis de variables de conversión reduce el trabajo de implementación del que son responsables los desarrolladores del cliente. Sigue ofreciendo la misma información (o incluso mejor) que el método de Sintaxis del producto. Los desarrolladores simplemente tienen que seguir las instrucciones de implementación que se les han dado y el resto del código se puede colocar en el archivo SDK web de Adobe AppMeasurement/Adobe Experience Platform.

Por ejemplo, veamos la solución recomendada para rastrear el rendimiento interno de la búsqueda de palabras clave. Dice que en la página de resultados de búsqueda de palabras clave, el código captura la palabra clave buscada a través de una prop (por ejemplo, prop4) y otra prop (por ejemplo, prop5). Estas props hacen un seguimiento de la cantidad de resultados que se muestran en la búsqueda. Siempre que se genera una solicitud de imagen de Adobe Analytics en la página de resultados de la búsqueda, se utilizan los objetos de capa de datos (o código de página) implementados por los desarrolladores para rellenar las variables anteriores (las props).

La lógica adicional contenida en el archivo AppMeasurement/Adobe Experience Platform Web SDK puede rellenar el resto de las variables (las eVars/dimensiones de comercialización) que deben configurarse al mismo tiempo.\
Por ejemplo, si un nuevo visitante realizara una búsqueda de palabra clave de “sandalias” que arroja 25 resultados en la página de resultados de búsqueda, el código que se activaría (a través del código de página O la captura de capa de datos) tendría este aspecto:

```js
s.prop4="sandals";
s.prop5="25";
```

La lógica del archivo SDK de AppMeasurement/Analytics podría transformar automáticamente este fragmento de código en lo siguiente:

```js
s.prop4="sandals";
s.prop5="25";
s.eVar2="sandals";
s.eVar1="internal keyword search";
s.eVar3="non-internal campaign";
s.eVar4="non-browse";
s.eVar5="non-cross sell";
```

No debe preocuparse de pasar datos de página en página e intentar crear una cadena bastante grande y poco manejable para insertarla en la variable products. En su lugar, los desarrolladores pueden implementar su parte de las soluciones de seguimiento (que se inserta en las props) y dejar el resto de la implementación en el código personalizado proporcionado por la asesoría de Adobe.

Como se explicó anteriormente, todas las eVars de comercialización que utilizan Sintaxis de variables de conversión tienen la configuración Asignación de “Más reciente (último)”. Una vez que una eVar tiene establecido cualquier valor, ese valor persiste en todas las visitas individuales posteriores (gracias a la columna post_evar). Se mantiene hasta que se establece en un valor diferente o hasta que caduca la eVar. Por lo tanto, cualquier producto con el que interactúe una vez configuradas las eVar, si aún no se han enlazado a ellas, se enlazará con los valores “Más reciente (último)” que se pasen a la eVar.

Utilizando el ejemplo anterior, el valor `eVar2` de sandalias y el valor eVar1 de búsqueda de palabra clave interna, etc. persisten en todas las páginas vistas después de que se haya realizado la búsqueda de palabra clave. Persisten hasta que las eVars se sobrescriben con otros valores. Supongamos que un visitante hace clic en un vínculo a la página de detalles del producto correspondiente al ID del producto sandalia123 desde la página de resultados de búsqueda de palabras clave.  A continuación, el ID de producto sandalia123 (si aún no se ha enlazado) se enlaza a cada uno de los valores contenidos en las columnas post_evar o a los valores de eVar recopilados de la página anterior (resultados de búsqueda).

Hay algo más que debe reconsiderarse con la Sintaxis de la variable de conversión. Se trata de que los eventos de enlace deben configurarse para enlazar un valor de eVar a un producto. La simple configuración de una eVar de comercialización (en su propia variable) junto a un producto (en la variable products) de una solicitud de imagen de Adobe Analytics no necesariamente enlaza el valor de eVar al producto.  En su lugar, la configuración de Evento de enlace de comercialización, que se establece en el Administrador de grupos de informes, determina los criterios que enlazan un valor de eVar a un producto

Dado que queremos enlazar los valores de la eVar del Método de localización de productos a los productos cada vez que se produce una interacción de productos (lo que implica que se ha encontrado un producto), es seguro suponer que las interacciones más comunes de producto encontrado que se pueden llevar a cabo son una vista de producto (cuando los visitantes acceden a una página de detalles del producto) o una adición al carro de compras (cuando los visitantes agregan un producto al carro de compras directamente desde una página de métodos de búsqueda de productos).

Por lo tanto, podemos elegir estos dos eventos (prodView, scAdd) como eventos de enlace de comercialización fundamentales.
Esto es lo que sucede cuando alguno de estos eventos de enlace está contenido en una solicitud de imagen. Cualquier ID de producto que esté contenido en la misma solicitud (dentro de la variable products) y que no se haya enlazado a una eVar de comercialización se enlazará con los valores más recientes pasados a la eVar de comercialización (columnas post_evar). Cualquier intento de volver a enlazar estos productos después de que tenga lugar este enlace original se ignora cuando el valor de Asignación (enlace) esté establecido en Valor original (primero).

### Configuración de prácticas recomendadas

A continuación, se muestran las configuraciones de prácticas recomendadas. Implementan fácilmente el método de localización de productos con los mejores resultados. Adobe recomienda que los clientes configuren cada una de las eVars de comercialización de los métodos de localización de productos (en general) de la siguiente manera:

* Comercialización habilitada: Habilitado
* Sintaxis de [comercialización]: Sintaxis de la variable de conversión
* Enlace de [asignación]: Valor original (primero)
* Caduca después de: Cantidad de tiempo que un producto permanece en un carro de compras antes de ser eliminado automáticamente (por ejemplo, 14 días, 30 días, etc.).  Si no existe ese tiempo, caduca después del evento purchase
* Tipo: Texto
* Eventos de enlace de comercialización: Vista de producto, adición al carro de compras y compra

## ¿Qué hacen realmente los eventos de enlace?

Cuando un evento de enlace está contenido en la misma llamada al servidor que la variable de productos, los valores de eVar de comercialización (que utilizan Sintaxis de la variable de conversión) de su columna post se enlazan a la variable de productos. En función del ejemplo anterior, supongamos que una llamada al servidor contiene los siguientes valores de eVar de comercialización:

```js
s.eVar2="sandals";
s.eVar1="internal keyword search";
s.eVar3="non-internal campaign";
s.eVar4="non-browse";
s.eVar5="non-cross sell";
```

Como se explicó anteriormente, las eVars anteriores persisten más allá de la visita actual gracias a su columna post_evar correspondiente. Por lo tanto, los servidores de Adobe transforman las eVars anteriores en lo siguiente:

```js
post_eVar2="sandals";
post_eVar1="internal keyword search";
post_eVar3="non-internal campaign";
post_eVar4="non-browse";
post_eVar5="non-cross sell";
```

Estas columnas post se almacenan en la base de datos de Adobe y persisten más allá de la visita actual en la que se establecieron inicialmente. Esto supone que no se produce ninguna caducidad ni restablecimiento de variables.  Los servidores de Adobe tienen estos valores post_evar disponibles en el momento en que procesan cualquier llamada futura al servidor que contenga tanto el evento de enlace como la variable products.

El enlace que se produce es únicamente entre estos valores post_evar y el contenido de la variable products. El evento de enlace no necesariamente se enlaza a las eVars o a la variable products. Es el catalizador el que indica a los servidores de Adobe que enlacen los valores de post_evar a los productos.

Supongamos que en una visita futura se establecen las siguientes variables:

```js
s.products=";sandals123"
s.events="prodView";
```

En las columnas post_evar, los servidores de procesamiento de Adobe ven esta visita de la siguiente manera:

```js
s.products=";sandals123";
s.events="prodView";
post_eVar2="sandals";
post_eVar1="internal keyword search";
post_eVar3="non-internal campaign";
post_eVar4="non-browse";
post_eVar5="non-cross sell";
```

Supongamos que eVar1, eVar2, eVar3, eVar4 y eVar5 se han configurado para utilizar `prodView` como evento de enlace. Si alguna de estas eVars no está configurada para usar prodView como evento de enlace, entonces el enlace entre esa eVar (mal configurada) y la variable products no se usará.

El enlace produce algunos resultados muy interesantes, que se pueden ver en el valor de la columna post_products. El enlace transforma el código anterior y establece algunas columnas post de la siguiente manera:

```js
post_events="prodView";
post_products=";sandals123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
```

Puede que le resulte familiar el valor contenido en la columna post_products. Desplácese hacia arriba del documento y compare el valor de post_products y el valor de s.products como se muestra abajo.  Vea que la columna post_products está configurada usando Sintaxis de la variable products.

Esto significa que el enlace copia los valores de la eVar de sintaxis de la variable de conversión en la variable products a través de Sintaxis del producto. Esta acción de copia solo tiene lugar cuando la variable products y un evento de enlace (configurado mediante la configuración de eVar) están contenidos en la misma solicitud. En ese punto, los valores contenidos en las columnas post_eVar están enlazados al producto. Este enlace se representa mediante Sintaxis del producto tal como se almacena en la columna post_products.

## eVars de comercialización, métrica Instancias y Atribución

Cuando se envía una eVar estándar en una llamada al servidor de Analytics, el valor de su columna post_evar siempre obtiene una instancia atribuida a ella. Las instancias representan el número de veces que se ha establecido un eVar igual a un valor en particular en una solicitud de imagen.

Por ejemplo, supongamos que `eVar10` es una eVar estándar con atribución [!UICONTROL Último toque]. Si establece `s.eVar10="hello world"` en cualquier página, el valor de “hello world” se pasa a la columna post_evar10 cuando Adobe procesa la visita. La métrica de instancias es igual a 1 para cada `eVar10` configuración individual de `hello world`. Tenga en cuenta que una instancia no siempre se registra cuando la columna post_evar tiene un valor. En su lugar, la columna post_evar determina qué valor obtiene la instancia cuando se registra una instancia.

Las instancias de un eVar de comercialización atribuyen la atribución a los valores que recopila el eVar. Pero esto ocurre solamente cuando un producto que estaba enlazado al valor de eVar de comercialización estaba “interactuado” al mismo tiempo.

Por ejemplo, configurar `s.eVar1="Internal Keyword Search"` por sí solo no da crédito a ninguna métrica Instancia en el valor eVar1 de Búsqueda de palabras clave internas. Se registra una instancia en ese momento. Sin embargo, a menos que un producto esté enlazado a ese valor Búsqueda de palabras clave internas al mismo tiempo que `eVar1` está establecido, la instancia se atribuye al bloque No especificado. En otras palabras, el valor `eVar1` de Búsqueda de palabras clave internas puede obtener una instancia. Pero esto solo sucede cuando un producto enlazado al valor de Búsqueda de palabras clave internas aparece en la variable products de la misma solicitud de imagen.

En resumen, sin configuración adicional, la métrica Instancias predeterminada de un eVar de comercialización es menos que útil. Afortunadamente, Adobe lanzó [Atribución](/help/analyze/analysis-workspace/attribution/overview.md). Permite aplicar varios modelos de atribución para cualquier métrica personalizada que recopile Adobe Analytics. Las métricas que aplican estos modelos de atribución no utilizan los valores contenidos en las columnas post_evar ni los valores enlazados a un producto en particular. En su lugar, estas métricas utilizan solo los valores que se pasan a través de las propias solicitudes de imagen (o los valores que se capturan mediante reglas de procesamiento de Adobe Analytics). Puede utilizar las funciones de Atribución para obtener una métrica de instancias atribuidas con precisión para todas las eVars de comercialización que utilicen Sintaxis de variables de conversión.

![Selección de atribución](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/assets/attribution-select.png)

Al añadir una métrica de instancias para una eVar de comercialización a un informe, el modelo de atribución adecuado sería el modelo Último toque. La configuración de la ventana de búsqueda del modelo no importa en este caso. El motivo es que un modelo de atribución de Último toque “forzado” siempre da crédito de instancia a cada valor individual que se transfiere mediante una solicitud. Esto sucede independientemente de si la configuración real de atribución/enlace del eVar está establecida en “Más reciente (último)” en “Valor original (primero)”.
