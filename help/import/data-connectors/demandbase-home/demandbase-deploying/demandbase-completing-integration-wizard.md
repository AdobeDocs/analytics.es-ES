---
description: Para activar la integración, debe completar el asistente de configuración en la interfaz de Conectores de datos.
seo-description: Para activar la integración, debe completar el asistente de configuración en la interfaz de Conectores de datos.
seo-title: Finalización del Asistente para integración de Adobe
title: Finalización del Asistente para integración de Adobe
uuid: 75260b92-a6f5-44b6-b3ea-d5945fdd1ecb
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Finalización del Asistente para integración de Adobe{#completing-the-adobe-integration-wizard}

Para activar la integración, debe completar el asistente de configuración en la interfaz de Conectores de datos.

1. Vaya al área Conectores de datos (anteriormente Genesis) dentro de Adobe Experience Cloud.
1. Inicie el asistente de integración de Demandbase 2.0.
1. Elija el grupo de informes deseado y proporcione un nombre para la integración.
1. Configure los siguientes elementos:

<table id="table_8D60DC7C48C144DC9934749E7F9F65FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> La dirección de correo electrónico </td> 
   <td colname="col2"> La dirección de correo electrónico del contacto principal. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Descripción </td> 
   <td colname="col2"> (Opcional) Descripción de esta configuración de integración. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clave de API de Demandbase </td> 
   <td colname="col2"> Puede obtenerlo de su representante de Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensión Demandbase personalizada #N </td> 
   <td colname="col2"> Son los ID de las 8 dimensiones opcionales. Para obtener más información, consulte Dimensiones personalizadas de Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enviar a Adobe Target </td> 
   <td colname="col2">Si es "true", las dimensiones Demandbase también se enviarán a Adobe Target mediante un mbox oculto. <p>Nota:  Se debe implementar un archivo mbox.js configurado en la página web para que se recopilen las dimensiones. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Configure los siguientes elementos de Asignaciones de variables:

   | Elemento | Descripción |
   |---|---|
   | Dimensiones de Demandbase | Elija una variable eVar disponible en el grupo de informes. |
   | Dimensiones personalizadas de Demandbase (opcional) | Elija una variable eVar disponible en el grupo de informes. |

1. Configure los nombres de la dimensión personalizada (si corresponde).

   1. Si eligió incluir dimensiones personalizadas en el paso 4 y asignó la eVar opcional en el paso 5, deberá proporcionar nombres descriptivos para dichas dimensiones. Por ejemplo, si elige introducir "stock_ticker" como dimensión personalizada 1, debe cambiar la casilla que contiene "Dimension 1" a "Stock Ticker".
   1. NO **modifique** los nombres de las dimensiones estándar 8 (es decir, SID de Demandbase, Nombre de la empresa, Industria, etc.).

1. Marque la casilla para que el tablero de Integración de Demandbase se cree automáticamente (recomendado).
1. Revise todos los elementos de configuración y haga clic en **[!UICONTROL Activar ahora]**.

