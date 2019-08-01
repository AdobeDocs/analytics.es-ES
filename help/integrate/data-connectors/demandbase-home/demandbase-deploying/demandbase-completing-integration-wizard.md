---
description: Para activar la integración, debe completar el asistente de configuración dentro de la interfaz de Data Connectors.
seo-description: Para activar la integración, debe completar el asistente de configuración dentro de la interfaz de Data Connectors.
seo-title: Finalización del Asistente para integración de Adobe
title: Finalización del Asistente para integración de Adobe
uuid: 75260 b 92-a 6 f 5-44 b 6-b 3 ea-d 5945 fdd 1 ecb
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

Para activar la integración, debe completar el asistente de configuración dentro de la interfaz de Data Connectors.

1. Vaya al área Conectores de datos (anteriormente Genesis) dentro de Adobe Marketing Cloud.
1. Inicie el Asistente de integración de Demandbase 2.0.
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
   <td colname="col1"> Clave de API Demandbase </td> 
   <td colname="col2"> Puede obtenerlo de su representante de Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensión Demandbase personalizada N º N </td> 
   <td colname="col2"> Son los ID de las 8 dimensiones opcionales. Para obtener más información, consulte Dimensiones personalizadas Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enviar a Adobe Target </td> 
   <td colname="col2">Si es «true», las dimensiones Demandbase también se enviarán a Adobe Target con un mbox oculto. <p>Nota: Un archivo mbox. js configurado debe implementarse en la página web para que se recopilen dimensiones. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Configure los siguientes elementos de Asignaciones de variables:

   | Elemento | Descripción |
   |---|---|
   | Dimensiones Demandbase | Elija una variable evar disponible del grupo de informes. |
   | Dimensiones personalizadas Demandbase (opcional) | Elija una variable evar disponible del grupo de informes. |

1. Configure los nombres de la dimensión personalizada (si corresponde).

   1. Si ha elegido incluir dimensiones personalizadas en el paso 4 y ha asignado la evar opcional en el paso 5, tendrá que proporcionar nombres descriptivos para esas dimensiones. Por ejemplo, si elige introducir «stock_ ticker» como dimensión personalizada 1, deberá cambiar la casilla que contiene «Dimensión 1» en «Stock Ticker».
   1. **NO** modifique los nombres de las dimensiones estándar de 8 (es decir, el SID Demandbase, el nombre de la empresa, la industria, etc.).

1. Marque la casilla para crear automáticamente el tablero de Integración Demandbase (recomendado).
1. Review all configuration items and click **[!UICONTROL Activate Now]**.

