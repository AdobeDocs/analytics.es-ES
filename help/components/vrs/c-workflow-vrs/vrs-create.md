---
description: Antes de empezar a crear grupos de informes virtuales, hay que tener algunos aspectos en cuenta.
keywords: Grupo de informes virtuales
seo-description: Antes de empezar a crear grupos de informes virtuales, hay que tener algunos aspectos en cuenta.
seo-title: Creación de grupos de informes virtuales
solution: Analytics
title: Creación de grupos de informes virtuales
topic: Reports and Analytics
uuid: 022 a 6656-808 e -4 c 92-b 7 ec -4 d 2 a 42 e 84 fa 8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Creación de grupos de informes virtuales

Antes de empezar a crear grupos de informes virtuales, hay que tener algunos aspectos en cuenta.

* Los usuarios que no sean administradores no pueden ver el Administrador de grupos de informes virtuales.
* Los grupos de informes virtuales no se pueden compartir. El uso compartido se realiza mediante grupos/permisos.
* En el Administrador de grupos de informes virtuales solo puede ver sus propios grupos. Debe hacer clic en Mostrar todos para ver los de otros usuarios.

1. Navigate to **[!UICONTROL Components]** &gt; **[!UICONTROL Virtual Report Suites]**.
1. Click **[!UICONTROL Add +]**.

   ![](assets/new_vrs.png)

1. Rellene los campos:

<table id="table_0F85B56480BB46CBA5BE236BBD70156D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre </td> 
   <td colname="col2"> <p>El nombre del grupo de informes virtuales no se hereda del grupo de informes superior y debe ser distinto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Descripción </td> 
   <td colname="col2"> <p>Agregue una buena descripción para los usuarios empresariales. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Etiquetas </td> 
   <td colname="col2"> <p>Puede agregar etiquetas para organizar los grupos de informes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Grupos </td> 
   <td colname="col2"> <p>Seleccione los grupos de permisos a los que quiera tener acceso en este VRS. (También puede administrar permisos de grupos en <span class="ignoretag"><span class="uicontrol">Administración</span> &gt; <span class="uicontrol">Administración de usuarios</span> &gt; <span class="uicontrol">Grupos</span></span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Grupo de informes superior </td> 
   <td colname="col2"> <p>El grupo de informes del que surge este grupo de informes virtuales hereda la siguiente configuración. La mayoría de los niveles y funciones de servicio (por ejemplo, la configuración eVar, las reglas de procesamiento, las Clasificaciones, etc.) se heredan. Para realizar cambios en esta configuración heredada en un VRS, debe editar el grupo de informes superior (<span class="ignoretag"><span class="uicontrol">Administración</span> &gt; <span class="uicontrol">Grupos de informes</span></span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zona horaria </td> 
   <td colname="col2"> <p>Elegir una zona horaria es opcional. </p> <p>Si elige una zona horaria, esta se guarda junto con el VRS. En caso contrario, se usará la zona horaria del grupo de informes superior. </p> <p>Al editar un VRS, la zona horaria que se guardó con el VRS se muestra en el selector desplegable. Si el VRS se creó antes de que se añadiera la opción de la zona horaria, en el selector desplegable se muestra la zona horaria del grupo de informes superior. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Segmentos </td> 
   <td colname="col2"> <p>Solo tiene que añadir un segmento o <a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_stack.html" format="https" scope="external">apilar otros</a>. </p> <p> <p>Nota: Al apilar dos segmentos, se unen de manera predeterminada con una instrucción Y. No es posible cambiarlo a una instrucción O. </p> </p> <p>Si intenta eliminar o modificar un segmento que se utilice en un grupo de informes virtuales, se muestra un error. </p> </td> 
  </tr> 
 </tbody> 
</table>

