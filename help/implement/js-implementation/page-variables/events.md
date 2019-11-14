---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---



# Eventos

La variable se usa para registrar eventos de éxito comunes del carro de compras, así como eventos de éxito personalizados.

<!-- 

events.xml

 -->

<table id="table_9EB9D08C80544CD68C4B1A2012440472"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamaño máximo </th> 
   <th class="entry"> Parámetro depurador </th> 
   <th class="entry"> Informes rellenados </th> 
   <th class="entry"> Valor predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Sin límite </td> 
   <td> eventos </td> 
   <td> <p>Eventos del carro de compras </p> <p>Eventos personalizados </p> </td> 
   <td> N.D. </td> 
  </tr> 
 </tbody> 
</table>

Un [!UICONTROL evento] se debe considerar un hito dentro de un sitio. Los eventos de éxito generalmente se rellenan en la página de confirmación final de un proceso, como un proceso de registro o la suscripción a un boletín. Los eventos personalizados se definen rellenando la variable de eventos con los valores literales definidos en la sección Valores posibles, a continuación.

De forma predeterminada, los eventos de éxito se configuran como eventos de *contador*. Los eventos de contador contabilizan el número de veces que se configura un evento de éxito (x+1). Los eventos también se pueden configurar como eventos *numéricos*. Los eventos numéricos permiten especificar el número que se incrementará. Esto podría ser necesario cuando se contabilizan valores dinámicos o arbitrarios, como los resultados devueltos por una búsqueda interna.

Un tipo de evento final, *moneda*, permite definir la cantidad que se sumará (similar a los eventos numéricos), pero la muestra como moneda en los informes y está sujeta a las conversiones monetarias basadas en el valor de s. *`currencyCode`* y en la configuración de moneda predeterminada para su grupo de informes. Para obtener información adicional sobre cómo usar eventos numéricos y monetarios, consulte [Productos](/help/implement/js-implementation/c-variables/page-variables.md).

**Configuración de la variable** {#section_9195286C34C54B02B2598E2B856492C3}

La variable [!UICONTROL s.events] está habilitada de forma predeterminada para todas las implementaciones. Los siete eventos de conversión preconfigurados están habilitados automáticamente para todos los grupos de informes nuevos. Los nuevos eventos personalizados (event1- [event100 o event1000](/help/implement/js-implementation/c-variables/page-variables.md)) los puede habilitar un usuario con derechos de administrador en Admin Console.

**Valores posibles** {#section_18395A3BEFEB4E9F8D7B2ED0001FBE4E}

La lista siguiente muestra los posibles valores para la variable de eventos:

| Evento | Descripción | Informes rellenados |
|---|---|---|
| prodView | Vistas del producto | Productos |
| scOpen | Abrir o inicializar un nuevo carro de compras | Carros de compras |
| scAdd | Agregar artículos al carro de compras | Adiciones al carro de compras |
| scRemove | Eliminar artículos del carro de compras | Eliminaciones del carro de compras |
| scView | Ver el carro de compras | Vistas del carro de compras |
| scCheckout | Comienzo del proceso de cierre de compra | Cierres de compra |
| purchase | Finalización de una compra (pedido) | Pedidos |
| event1 - event1000 (event100 para producto específico) | Eventos personalizados | Eventos personalizados |

**Sintaxis y ejemplos** {#section_45A159DF00114066B8551DDEB15E084C}

Los eventos de contador se configuran colocando los eventos deseados en la variable [!UICONTROL s.events], en una lista separada por coma (si se van a pasar varios eventos).

```js
s.events="scAdd"
```

```js
s.events="scAdd,event1,event7"
```

```js
s.events="event5"
```

```js
s.events="purchase,event10"
```

En código H23 o posterior, los eventos de contador pueden tener asignados enteros mayores que uno.

```js
s.events="event1=10"
```

```js
s.events="scRemove=3,event6,event2=4"
```

Al implementar los eventos de contador con valores enteros asignados, el evento se trata como si se hubiera activado varias veces en la solicitud de imagen. Los eventos de contador no permiten decimales; se recomienda usar eventos numéricos en su lugar si esta funcionalidad es necesaria.
Los eventos numéricos y monetarios deben incluirse en la variable [!UICONTROL s.events], aunque normalmente reciben su valor numérico (por ejemplo, 24.99) en la variable [!UICONTROL s.products]. Esto permite enlazar valores numéricos y monetarios específicos con entradas de productos individuales.

**Serialización de eventos** {#section_A89488EF4471405AAFC4D6DD05E77621}

De forma predeterminada, un evento se contabiliza cada vez que se establece el evento en su sitio.

Consulte [Serialización de eventos](/help/implement/js-implementation/event-serialization.md) para obtener más información.

**Sintaxis** {#section_8559D42D3F344AF3BB3C0125F78C4989}

```js
s.events="event1:3167fhjkah"
```

**Ejemplos** {#section_7B5B5728A59648ADB3E2548CDAD2C9D4}

```js
s.events="scAdd:003717174"
```

```js
s.events="scAdd:user228197,event1:577247280,event7:P7fhF8571"
```
