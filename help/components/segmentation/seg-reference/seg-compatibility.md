---
description: Comprenda por qué no todos los segmentos creados en el Generador de segmentos son compatibles con Data Warehouse. Descubra qué funciones son compatibles.
title: Compatibilidad del segmento con el Data Warehouse
feature: Segmentation
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
TQID: https://experienceleague.adobe.com/7CrArNYD-8ZXVpfO86d1l42ySkTuv8V04PWJFeNWx3s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 345
ht-degree: 80%

---

# Compatibilidad del segmento con el Almacén de datos

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
   <td> Admitida </td> 
   <td> No admitido </td> 
  </tr> 
  <tr> 
   <td> <b>AND y OR pueden combinarse sin ningún límite</b> </td> 
   <td> Admitida </td> 
   <td> Algunas limitaciones. Consulte *nota* la tabla siguiente. </td> 
  </tr> 
  <tr> 
   <td> <b>Contenedores anidados</b> </td> 
   <td> Admitida </td> 
   <td> Algunas limitaciones (el ámbito debe disminuir; por ejemplo, los visitantes pueden contener las visitas individuales, pero no al revés) </td> 
  </tr> 
  <tr> 
   <td> <b>Dimensiones</b> </td> 
   <td>Arrastre y suelte una dimensión en el campo <span class="uicontrol"> definiciones</span> del Generador de segmentos para conocer la compatibilidad del producto. Por ejemplo, estas dimensiones solo son compatibles con Analysis Workspace, Reports &amp; Analytics: 
    <ul> 
     <li>Servidor de entrada </li> 
     <li>Categoría de entrada </li> 
     <li>Fecha de entrada </li> 
     <li>Clasificación de todas las páginas de búsqueda </li> 
    </ul> </td> 
   <td> Arrastre y suelte una dimensión en el campo <span class="uicontrol"> definiciones</span> del Generador de segmentos para conocer la compatibilidad del producto. Por ejemplo, estas dimensiones solo se admiten en el Data Warehouse: 
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
     <li>Hora y día </li> 
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
   <td> Admitida </td> 
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
