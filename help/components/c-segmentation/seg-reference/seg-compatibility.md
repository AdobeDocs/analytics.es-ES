---
description: No todos los segmentos creados en el Generador de segmentos son compatibles con el Almacén de datos. Esta tabla enumera las funciones admitidas..
seo-description: No todos los segmentos creados en el Generador de segmentos son compatibles con el Almacén de datos. Esta tabla enumera las funciones admitidas..
seo-title: Compatibilidad del segmento con el Almacén de datos
solution: Analytics
title: Compatibilidad del segmento con el Almacén de datos
topic: Segmentos
uuid: 370258 c 5-8614-4434-871 c -41753 ed 77 f 5 c
translation-type: tm+mt
source-git-commit: 26bba9528873c983852754056a5495c4004d25e6

---


# Compatibilidad del segmento con el Almacén de datos

Not all segments created in the Segment Builder are compatible with [!DNL Data Warehouse]. En esta tabla se muestran las funciones admitidas.

<table id="table_BBB1DAFDF85041598FA4AF869172CF7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Analysis Workspace, Informes y análisis, Análisis específicos </th> 
   <th colname="col3" class="entry"> Almacén de datos </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Excluye</b> </td> 
   <td colname="col2"> Admitido en cualquier nivel </td> 
   <td colname="col3"> Admitido solo en casos especiales en el nivel superior </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segmentos secuenciales</b> </td> 
   <td colname="col2"> Admitido </td> 
   <td colname="col3"> No admitido </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Y y O pueden combinarse sin ningún límite</b> </td> 
   <td colname="col2"> Admitido </td> 
   <td colname="col3"> Algunas limitaciones </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Contenedores anidados</b> </td> 
   <td colname="col2"> Admitido </td> 
   <td colname="col3"> Algunas limitaciones (el ámbito debe disminuir; por ejemplo, los visitantes pueden contener las visitas individuales, pero no al revés) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensiones</b> </td> 
   <td colname="col2">Arrastre y suelte una dimensión en las <span class="uicontrol">Definiciones</span> del Generador de segmentos para conocer la compatibilidad del producto. Por ejemplo, estas dimensiones solo se admiten en Analysis Workspace, Informes y análisis y Análisis específicos: 
    <ul id="ul_BD708CC3A16743F49F998D1046EC70A3"> 
     <li id="li_240DA619D50B4336ACD9117BF59AF10A">Servidor de entrada </li> 
     <li id="li_222D4D4116674EF8A52945CCB9C78719">Categoría de entrada </li> 
     <li id="li_5A43C846E2EA4EFCB892DE9E0607C68C">Fecha de entrada </li> 
     <li id="li_8E9CABBE04FC4A7A9A5D2BDD34AD3C87">Clasificación de todas las páginas de búsqueda </li> 
    </ul> </td> 
   <td colname="col3"> Arrastre y suelte una dimensión en las <span class="uicontrol">Definiciones</span> del Generador de segmentos para conocer la compatibilidad del producto. Por ejemplo, estas dimensiones solo se admiten en el Almacén de datos: 
    <ul id="ul_61A5B314CCCF497DB0385324E3309E22"> 
     <li id="li_1254089BDFAE4E0F8E51CB1511BBBF53">Dirección IP </li> 
     <li id="li_D8E040F77A8C46A084547F4FE685CB10">URL de la página </li> 
     <li id="li_4C79AE900CF6458780C124143DC6FA5B">ID del visitante </li> 
     <li id="li_4EC10645DE9740609D8DDFD4F668FE67">ID de visitante de Experience Cloud </li> 
    </ul> <p>The following dimensions <b>cannot </b>be used in Data Warehouse segments: </p> 
    <ul id="ul_FE143F6D1ABF45DAA444E1B5691C7D4F"> 
     <li id="li_E77F3CC45BA04674B857FE5AB19D56F1">Clasificación de todas las páginas de búsqueda </li> 
     <li id="li_95E1549C13F14BA0B32686401EE78E31">AM/PM </li> 
     <li id="li_6F1C8FC2E7674A0CA14B70B65784D896">Día del mes </li> 
     <li id="li_79D1A91D741D4CCC937D07906D71F964">Día de la semana </li> 
     <li id="li_4008565353084611BD782B98D50C0611">Día del año </li> 
     <li id="li_F87D78F125874087BFF74FAAE2BA46F5">Unidad comercial de entrada </li> 
     <li id="li_53DA4E64C6714CFF90D164245D01C16A">Entrada (todas las dimensiones que contienen Entrada, excepto Página de entrada) </li> 
     <li id="li_7F26B0E54A4A48319F31D8FC499D1CF2">Salida (todas las dimensiones que contienen Salida, excepto Vínculo de salida y Página de salida) </li> 
     <li id="li_1877D2D8A95B43F29CAA426BF2FE4996">Jerarquía (todas las dimensiones que comienzan con Jerarquía) </li> 
     <li id="li_DF0BCC63ED274ABEA1C5A28274936310">Profundidad de acierto </li> 
     <li id="li_98BE56213E1A4FD28D4858D53C46D23E">Tipo de visita </li> 
     <li id="li_52ECB31657DF4180BDB9C8D21CC74313">Hora del día </li> 
     <li id="li_93716207F2614822ACB84100B35D27BC">Mes del año </li> 
     <li id="li_FFC8E1F7092C4876A7E9F2365CC234B9">Páginas no encontradas </li> 
     <li id="li_7A070C8E0F664F5AB554555B17D0E4E6">Búsqueda de pago </li> 
     <li id="li_12228C18BF90463C8D8394FB810843D3">Trimestre del año </li> 
     <li id="li_1833B6E2011C4757A60CAA2C98B35AFA">Frecuencia de retorno </li> 
     <li id="li_39154CD74A534D9AA09C701FE1E2C521">Visitas a una sola página </li> 
     <li id="li_84BDE34DD577488881E8842D2DE72D3C">Tiempo previo al evento </li> 
     <li id="li_552BE3414CC949B3B24BE99298945874">Tiempo empleado en la página - Agrupado </li> 
     <li id="li_33D815E04CB3493C82BE33E958C2D7B9">Tiempo empleado por visita - General </li> 
     <li id="li_76F2BB88B8CD456DB50D04F36BB7854B">Motivo de omisión de seguimiento </li> 
     <li id="li_07345E08D0584CEC99128A0542587019">Estados Unidos </li> 
     <li id="li_3D6BD9E927334B9BBC29E602D1103F7A">Día de la semana/Fin de semana </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Apilamiento de segmentos</b> </td> 
   <td colname="col2"> Admitido </td> 
   <td colname="col3"> No admitido </td> 
  </tr> 
 </tbody> 
</table>

