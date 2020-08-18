---
description: No todos los segmentos creados en el Generador de segmentos son compatibles con el Data Warehouse. Esta tabla enumera las funciones compatibles.
title: Compatibilidad del segmento con el Data Warehouse
topic: Segments
uuid: 370258c5-8614-4434-871c-41753ed77f5c
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 100%

---


# Compatibilidad del segmento con el Data Warehouse

No todos los segmentos creados en el Generador de segmentos son compatibles con [!DNL Data Warehouse]. Esta tabla enumera las funciones compatibles.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Analysis Workspace, Reports &amp; Analytics, Ad Hoc Analysis </th> 
   <th> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td > <b>Excluir contenedor</b> </td> 
   <td> Admitido en cualquier nivel </td> 
   <td> Admitido solo en casos especiales en el nivel superior </td> 
  </tr> 
  <tr> 
   <td> <b>Segmentos secuenciales</b> </td> 
   <td> Admitido </td> 
   <td> No admitido </td> 
  </tr> 
  <tr> 
   <td> <b>AND y OR pueden combinarse sin ningún límite</b> </td> 
   <td> Admitido </td> 
   <td> Algunas limitaciones. Consulte *nota* la tabla siguiente. </td> 
  </tr> 
  <tr> 
   <td> <b>Contenedores anidados</b> </td> 
   <td> Admitido </td> 
   <td> Algunas limitaciones (el ámbito debe disminuir; por ejemplo, los visitantes pueden contener las visitas individuales, pero no al revés) </td> 
  </tr> 
  <tr> 
   <td> <b>Dimensiones</b> </td> 
   <td>Arrastre y suelte una dimensión en las <span class="uicontrol">Definiciones</span> del Generador de segmentos para conocer la compatibilidad del producto. Por ejemplo, estas dimensiones solo son compatibles en Analysis Workspace, Reports &amp; Analytics y Ad Hoc Analysis: 
    <ul> 
     <li>Servidor de entrada </li> 
     <li>Categoría de entrada </li> 
     <li>Fecha de entrada </li> 
     <li>Clasificación de todas las páginas de búsqueda </li> 
    </ul> </td> 
   <td> Arrastre y suelte una dimensión en las <span class="uicontrol">Definiciones</span> del Generador de segmentos para conocer la compatibilidad del producto. Por ejemplo, estas dimensiones solo se admiten en el Data Warehouse: 
    <ul> 
     <li>Dirección IP </li> 
     <li>URL de la página </li> 
     <li>Visitor ID </li> 
     <li>ID de visitante de Experience Cloud </li> 
    </ul> <p><b>No</b> es posible utilizar las dimensiones siguientes en los segmentos del Data Warehouse: </p> 
    <ul> 
     <li>Clasificación de todas las páginas de búsqueda </li> 
     <li>AM/PM </li> 
     <li>Día del mes </li> 
     <li>Día de la semana </li> 
     <li>Día del año </li> 
     <li>Unidad comercial de entrada </li> 
     <li>Entrada (todas las dimensiones que contienen Entrada, excepto Página de entrada) </li> 
     <li>Salida (todas las dimensiones que contienen Salida, excepto Vínculo de salida y Página de salida) </li> 
     <li>Jerarquía (todas las dimensiones que comienzan con Jerarquía) </li> 
     <li>Profundidad de visita </li> 
     <li>Tipo de visita </li> 
     <li>Hora Día </li> 
     <li>Mes del año </li> 
     <li>Páginas no encontradas </li> 
     <li>Búsqueda de pago </li> 
     <li>Trimestre del año </li> 
     <li>Frecuencia de retorno </li> 
     <li>Visitas de página única </li> 
     <li>Tiempo previo al evento </li> 
     <li>Tiempo empleado en la página - Agrupado </li> 
     <li>Tiempo empleado por visita - General </li> 
     <li>Motivo de exclusión de seguimiento </li> 
     <li>Estados estadounidenses </li> 
     <li>Día de la semana/Fin de semana </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <b>Apilamiento de segmentos</b> </td> 
   <td> Admitido </td> 
   <td> Admitido </td> 
  </tr>
  <tr>
    <td><b>Operadores “Es igual a cualquiera de” y “No es igual a ninguno de”</b></td>
    <td>Admitido</td>
    <td>No admitido</td>
  </tr>
 </tbody> 
</table>

*Nota: Data Warehouse no admite todos los casos de uso de un contenedor`exclusion`o`without`al usar`AND/OR`. Cuando se usa una combinación de este tipo, solo se admiten en Data Warehouse aquellos segmentos que se puedan rescribir como `A AND NOT B`, (o **que permitan incluir esta característica** y **excluir esta característica**).*
