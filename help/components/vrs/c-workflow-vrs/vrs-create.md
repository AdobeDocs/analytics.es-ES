---
description: Antes de empezar a crear grupos de informes virtuales, hay que tener algunos aspectos en cuenta.
keywords: Grupo de informes virtuales
title: Crear un grupo de informes virtuales
feature: Conceptos básicos de Reports & Analytics y conceptos básicos de Analytics
uuid: 022a6656-808e-4c92-b7ec-4d2a42e84fa8
exl-id: 5ff6ff1a-5b99-41cc-a3a7-928197ec9ef9
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 98%

---

# Crear un grupo de informes virtuales

Antes de empezar a crear grupos de informes virtuales, hay que tener algunos aspectos en cuenta.

* Los usuarios que no sean administradores no pueden ver el Administrador de grupos de informes virtuales.
* Los grupos de informes virtuales no se pueden compartir. El uso compartido se realiza mediante grupos/permisos.
* En el Administrador de grupos de informes virtuales solo puede ver sus propios grupos. Debe hacer clic en “Mostrar todos” para ver los de otros usuarios.

1. Vaya a **[!UICONTROL Componentes]** > **[!UICONTROL Grupos de informes virtuales]**.
1. Haga clic en **[!UICONTROL Agregar +]**.

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
   <td colname="col2"> <p>Seleccione los grupos de permisos a los que quiera tener acceso en este VRS. (También puede administrar permisos de grupos en <span class="ignoretag"><span class="uicontrol"> Administración</span> &gt; <span class="uicontrol">Administración de usuarios</span> &gt; <span class="uicontrol">Grupos</span></span>). </p> </td> 
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
   <td colname="col2"> <p>Solo tiene que añadir un segmento o <a href="https://docs.adobe.com/content/help/es-ES/analytics/components/segmentation/segmentation-workflow/seg-build.html"  >apilar otros</a>. </p> <p> <p>Nota: Al apilar dos segmentos, se unen de manera predeterminada con una instrucción AND. No es posible cambiarlo a una instrucción OR. </p> </p> <p>Si intenta eliminar o modificar un segmento que se utilice en un grupo de informes virtuales, se muestra un error. </p> </td> 
  </tr> 
 </tbody> 
</table>
