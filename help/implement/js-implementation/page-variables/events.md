---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: edf88e40cae8b6886b04257f266666c13a37f88d

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

Un tipo de evento final, *moneda*, permite definir la cantidad que se sumará (similar a los eventos numéricos), pero la muestra como moneda en los informes y está sujeta a las conversiones monetarias basadas en el valor de s. *`currencyCode`* y en la configuración de moneda predeterminada para su grupo de informes. Para obtener información adicional sobre cómo usar eventos numéricos y monetarios, consulte [Productos](/help/implement/js-implementation/page-variables/page-variables.md).

**Configuración de la variable**

La variable `s.events` está habilitada de forma predeterminada para todas las implementaciones. Los siete eventos de conversión preconfigurados están habilitados automáticamente para todos los grupos de informes nuevos. Los nuevos eventos personalizados (event1- [event100 o event1000](/help/implement/js-implementation/page-variables/page-variables.md)) los puede habilitar un usuario con derechos de administrador en Admin Console.

**Valores posibles**

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

**Sintaxis y ejemplos**

Los eventos de contador se configuran colocando los eventos deseados en la variable `s.events`, en una lista separada por coma (si se van a pasar varios eventos).

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

**Serialización de eventos**

De forma predeterminada, un evento se contabiliza cada vez que se establece el evento en su sitio.

Consulte [Serialización de eventos](/help/implement/js-implementation/event-serialization.md) para obtener más información.

**Sintaxis**

```js
s.events="event1:3167fhjkah"
```

**Ejemplos**

```js
s.events="scAdd:003717174"
```

```js
s.events="scAdd:user228197,event1:577247280,event7:P7fhF8571"
```
