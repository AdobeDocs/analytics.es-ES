---
description: No todos los segmentos creados en el Generador de segmentos son compatibles con el Data Warehouse. Esta tabla enumera las funciones compatibles.
title: Compatibilidad del segmento con el Data Warehouse
feature: Segmentation
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
source-git-commit: 002ce0f001796187c01fc955b79ac967ba36da9a
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 95%

---

# Compatibilidad de segmentos de Data Warehouse

No todos los segmentos creados en el Generador de segmentos son compatibles con [!DNL Data Warehouse]. Esta tabla enumera las funciones compatibles.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Analysis Workspace, Reports &amp; Analytics </th> 
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
   <td>Arrastre y suelte una dimensión en las <span class="uicontrol">Definiciones</span> del Generador de segmentos para conocer la compatibilidad del producto. Por ejemplo, estas dimensiones solo son compatibles con Analysis Workspace, Reports &amp; Analytics: 
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
     <li>ID de visitante </li> 
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
     <li>Profundidad de la visita </li> 
     <li>Tipo de visita </li> 
     <li>Hora del día </li> 
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

*Nota: Data Warehouse no admite todos los casos de uso de un contenedor `exclusion` o `without` al usar `AND/OR`. Cuando se usa una combinación de este tipo, solo se admiten en Data Warehouse aquellos segmentos que se puedan rescribir como `A AND NOT B`, (o **que permitan incluir esta característica** y **excluir esta característica**).*
