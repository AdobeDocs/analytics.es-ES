---
description: Sección de preguntas más frecuentes de Analytics sobre atributos del cliente y cómo ejecutar el informe de atributos del cliente.
solution: Experience Cloud,Analytics
title: Atributos del cliente
uuid: 94721265-ba23-45d5-8807-76f81b0b8a30
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Atributos del cliente

Sección de preguntas más frecuentes de Analytics sobre atributos del cliente y cómo ejecutar el informe de atributos del cliente.

**[!UICONTROL Reports]** **[!UICONTROL > Visitor Profile]** > **[!UICONTROL Customer Attributes]**

Si captura los datos del cliente empresarial en una base de datos de administración de la relación con los clientes (CRM), podrá cargar los datos en una fuente de datos de atributos del cliente en Experience Cloud. Una vez que los datos se hayan cargado, podrá ejecutar el informe de atributos del cliente en Reports &amp; Analytics.

* [Atributos del cliente e informes de métricas en Analytics ](/help/components/c-variables/dimensionslist/reports-customer-attributes.md#section_EF343662146B460A882D3DF772ADD86D)
* [Preguntas más frecuentes - Atributos del cliente en Analytics](/help/components/c-variables/dimensionslist/reports-customer-attributes.md#section_E29641D1F3D649C1AC9EA5231921F038)

Consulte [Atributos del cliente](https://docs.adobe.com/content/help/es-ES/core-services/interface/customer-attributes/attributes.html) en la ayuda de Experience Cloud para obtener información sobre cómo cargar datos de atributos del cliente.

## Atributos del cliente e informes de métricas en Analytics  {#section_EF343662146B460A882D3DF772ADD86D}

Después de cargar atributos de cliente y validar el esquema (en Experience Cloud), el sistema crea métricas basadas en nombres prácticos (como *`age`* o *`gender`*) que se asignan a las cadenas de atributos y los enteros. Estas métricas aparecen en **[!UICONTROL Visitor Profile]** > **[!UICONTROL Customer Attributes]** informes.

Por ejemplo:

**[!UICONTROL Visitor Profile]** > **[!UICONTROL Customer Attributes]** > **[!UICONTROL Age]**

![](assets/report_age.png)

**Ejemplo - Métrica de edad**

Si especifica una cadena como *`age`*, el sistema crea las siguientes métricas y dimensiones:

* Dimensión Edad: le permite ejecutar un informe basado en el atributo Edad.
* Métrica Edad: métrica que puede añadir a un informe, como el de visitantes únicos.
* Métrica Recuento de edad: le permite saber, por ejemplo, si los visitantes han especificado un valor de  *`age`* en un formulario.

Como las métricas son sumas en una tabla de informe, debería  [crear una métrica calculada](https://docs.adobe.com/content/help/es-ES/analytics/components/calculated-metrics/cm-overview.html) que le indique la edad media. La fórmula para esta métrica es `Age / Count of Age`.

## Preguntas más frecuentes - Atributos del cliente en Analytics {#section_E29641D1F3D649C1AC9EA5231921F038}

<table id="table_88631069013B408EBB0A810657662B36"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pregunta </th> 
   <th colname="col2" class="entry"> Respuesta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>¿Por qué es preferible utilizar el servicio de identidad para establecer el ID de cliente en lugar de rellenarlo en una propiedad o eVar? </p> </td> 
   <td colname="col2"> <p>El uso del servicio de identidad ofrece una serie de ventajas: </p> 
    <ul id="ul_5D3659604D43419F9CA5920B4F93728E"> 
     <li id="li_BA2EF0715C5A47EFAFA7191CFAD088A4">Si no establece el ID de cliente con el servicio de identidad, los registros del cliente solo estarán disponibles para Adobe Analytics. Si desea utilizar los registros del cliente para la segmentación en tiempo real, debe usar el servicio de identidad. </li> 
     <li id="li_228358684E474A298E39578D427BF932">Utilizar el servicio de identidad para establecer el ID de cliente reduce el tiempo empleado en sincronizar los ID con Experience Cloud. Si pone el ID de cliente en una propiedad o eVar, los ID de cliente se envían a Experience Cloud mediante la sincronización de servidor de back-end que se produce por lotes. El servicio de identidad sincroniza inmediatamente el ID de cliente con Experience Cloud. </li> 
     <li id="li_BCF28219E4014FCF9F747C3D8D270526"> Usar el servicio de identidad en lugar de una propiedad o eVar libera esa propiedad o eVar para otros usos. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Si ya estoy almacenando un ID de cliente en una propiedad o eVar, ¿por qué debería utilizar esta nueva funcionalidad en lugar de clasificar mi propiedad o eVar con atributos de CRM? </p> </td> 
   <td colname="col2"> <p>Las propiedades o eVars están sujetas a limitaciones por superación únicas. El uso de esta funcionalidad puede aportar datos de atributos para un número ilimitado de ID de cliente. De igual forma, si utiliza el método de propiedad/eVar, limitará la información de CRM para Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Cómo aparecerán mis atributos de CRM en Adobe Analytics? </p> </td> 
   <td colname="col2"> <p>Los atributos de CRM se manifestarán en Analysis Workspace, Reports &amp; Analytics, Ad Hoc Analysis, la API de informes y el Report Builder. Los atributos de texto aparecerán como informes o dimensiones. Los atributos numéricos aparecerán como dimensiones o como métricas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Los datos de CRM estarán disponibles en el Data Warehouse y en las fuentes de datos? </p> </td> 
   <td colname="col2"> <p>En este momento, los datos de CRM no están disponibles en el Data Warehouse y en la fuente de datos. </p> </td> 
  </tr> 
 </tbody> 
</table>

