---
description: Se trata de las preguntas más frecuentes sobre la configuración automática de la implementación de Adobe Analytics. El método de configuración automática se encarga de administrar el código de AppMeasurement.
keywords: Dynamic Tag Management;plug-ins;staging;effect on current settings;revision history;potential pitfalls;report suite id;currency code;tracking server;ssl tracking server;custom code;library management
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Preguntas frecuentes sobre la herramienta Adobe Analytics
uuid: 8fcef893-e305-4a95-a033-9066a56b09cd
translation-type: ht
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440
workflow-type: ht
source-wordcount: '410'
ht-degree: 100%

---


# Preguntas frecuentes sobre la herramienta Adobe Analytics

Se trata de las preguntas más frecuentes sobre la configuración automática de la implementación de Adobe Analytics. El método de configuración automática se encarga de administrar el código de [!DNL AppMeasurement].

<table id="table_A50D00E2C47A473B92DA800FB08FE640"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pregunta </th> 
   <th colname="col2" class="entry"> Respuesta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> ¿Dónde puedo colocar mis complementos al implementar Adobe Analytics a través de DTM? </p> </td> 
   <td colname="col2"> <p> Si utiliza DTM para alojar manualmente <code> s_code</code>, se pueden añadir complementos en el mismo editor que el <code> s_code</code> alojado, tal y como ocurriría en una implementación de Adobe Analytics típica. </p> <p>Sin embargo, también puede colocar los complementos en el editor dentro de la sección <span class="term">Personalizar código de página</span> de la configuración de la herramienta. Los dos métodos de implementación deberían ser igual de eficaces. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Si realizo cambios de configuración en la nueva versión de la herramienta, ¿puedo probarla en el entorno de ensayo antes de publicarla en el de producción? </p> </td> 
   <td colname="col2"> <p>Sí. </p> <p>Todos los cambios se pueden probar en un entorno de ensayo, tal y como lo haría normalmente, antes de implementarlos en un entorno de producción. Si decide no publicarla porque observa que se producen problemas en el entorno de ensayo, el código de producción seguirá funcionando tal y como lo hacía antes de publicar la nueva integración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Si cambio de la configuración manual (el ajuste predeterminado de las herramientas existentes) a la configuración automática, ¿se verá afectada mi configuración actual? </p> </td> 
   <td colname="col2"> <p>No. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Si cambio de la administración de biblioteca manual a la administración realizada por Adobe, ¿se verán afectados la configuración o el código actuales? </p> </td> 
   <td colname="col2"> <p>El código de usuario que haya especificado se sobrescribe con la biblioteca <span class="keyword">AppMeasurement</span> base. Para que el código se siga ejecutando, debe moverlo a la nueva sección <span class="wintitle">Código de página personalizado</span> al final de la herramienta de configuración. Este método permite administrar (y actualizar) la biblioteca <span class="keyword">AppMeasurement</span> con independencia del código personalizado del usuario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Se conservará el historial de revisiones de la herramienta <span class="keyword">Adobe Analytics</span> al publicar la nueva integración? </p> </td> 
   <td colname="col2"> <p>Sí. </p> </td> 
  </tr> 
 </tbody> 
</table>

Consulte [Agregar la herramienta Adobe Analytics](/help/implement/other/dtm/c-aa-tool/analytics-dtm.md) para obtener información sobre la configuración.

## Posibles inconvenientes {#section_201BF9E0EB7D4BC2B72A617543C2030B}

Existe una pequeña posibilidad de que la integración pueda provocar problemas de recopilación de datos si está utilizando [!DNL Adobe Analytics]. Estos problemas podrían surgir únicamente si publica la biblioteca en el entorno de producción después del lanzamiento (el código de producción permanece intacto tras la publicación).

Para evitar que se produzcan estos problemas, asegúrese de que:

* Los ID de los grupos de informes se introducen correctamente en la herramienta.
* Los ID de los grupos de informes de la herramienta coinciden con los ID del código de [!DNL AppMeasurement].
* Los campos de código de divisa, conjunto de caracteres, servidor de seguimiento y configuración del servidor de seguimiento SSL se han establecido correctamente con los valores admitidos.
* El código personalizado se define en [!DNL Library Management].

