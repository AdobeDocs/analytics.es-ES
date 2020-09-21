---
description: Una propiedad web puede ser cualquier agrupación de uno o más dominios y subdominios incluida en un código incrustado y con una biblioteca de reglas.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;web property;property
title: Crear una propiedad web
topic: Developer and implementation
uuid: f19d5504-eb44-4d93-a387-7470ab4b3a3a
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '466'
ht-degree: 100%

---


# Crear una propiedad web

Una propiedad web puede ser cualquier agrupación de uno o más dominios y subdominios incluida en un código incrustado y con una biblioteca de reglas.

>[!NOTE]
>
>Solo los usuarios con derechos de administrador pueden crear una propiedad. Para obtener más información sobre las funciones, consulte [Crear y administrar grupos en la DTM](https://docs.adobe.com/content/help/es-ES/dtm/using/admin/groups.html) en la documentación del producto de Dynamic Tag Management.

Puede administrar y rastrear estos recursos con DTM. Por ejemplo, supongamos que tiene varios sitios web basados en una plantilla y quiere rastrear los mismos recursos en todos. Puede aplicar una propiedad web a varios dominios.

Para obtener información general sobre propiedades web y prácticas recomendadas, consulte [Propiedades web](https://docs.adobe.com/content/help/es-ES/dtm/using/admin/web-property.html) en la documentación del producto de Dynamic Tag Management.

1. Vaya a la página de su empresa y haga clic en **[!UICONTROL Agregar propiedad]**.

   ![](assets/dtm-create-web-property.png)

1. Rellene los campos:

   <table id="table_376D72251C4D4C4CA878D10C18D2532C"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Elemento </th> 
    <th colname="col2" class="entry"> Descripción </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Nombre</span> </td> 
    <td colname="col2"> <p>El nombre de su propiedad. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> URL</span> </td> 
    <td colname="col2"> <p>URL base de la propiedad. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Este sitio expande varios dominios </span> </td> 
    <td colname="col2"> <p>Puede agregar y eliminar dominios si desea que los datos del visitante se mantengan entre los dominios. Si se selecciona esta opción, los datos de la visita persisten entre subdominios. </p> <p>Este ajuste le permite especificar cómo desea rastrear el tráfico entre sus subdominios o dominios asociados. Los vínculos a subdominios se tratan como vínculos de salida. Las visitas a subdominios se rastrean separadamente. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. (Opcional) Configure la [!UICONTROL Configuración avanzada].

   <table id="table_6E687FBE6ACC4301BCCD837F4DCBB9C9"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Elemento </th> 
    <th colname="col2" class="entry"> Descripción </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Permitir aprobaciones de reglas múltiples</span> </td> 
    <td colname="col2"> <p>Permite que se aprueben múltiples reglas para esta propiedad al mismo tiempo. La aprobación predeterminada permite aprobar una única regla. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Habilitar publicación selectiva</span> </td> 
    <td colname="col2"> <p>Especifica si se permite a los usuarios seleccionar qué reglas de aprobación se publican. Se trata de la opción predeterminada. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Nombre de cookie de seguimiento</span> </td> 
    <td colname="col2"> <p>Anula el nombre de la cookie de seguimiento predeterminado. Puede personalizar el nombre que utiliza Dynamic Tag Management para rastrear el estado de exclusión para recibir otras cookies. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Tiempo de espera de etiqueta</span> </td> 
    <td colname="col2"> <p>Especifica cuánto tiempo espera Dynamic Tag Management a que una etiqueta se active antes de cancelar su solicitud. </p> <p> Debido al modo en que funciona Dynamic Tag Management, no se preocupe si el valor es muy grande. DTM cuenta con métodos eficaces de asegurar que las etiquetas lentas no afecten a la experiencia de usuario. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Retraso de anclaje</span> </td> 
    <td colname="col2"> <p>Especifica cuánto tiempo espera Dynamic Tag Management a que las etiquetas se activen cuando se pulsa un vínculo, antes de pasar a la siguiente página. El valor predeterminado es 100 milisegundos. </p> <p>Un tiempo de espera superior mejora la precisión de seguimiento. Adobe recomienda un tiempo de espera de 500 milisegundos o menos, ya que el usuario no lo percibirá. </p> <p>Dynamic Tag Management esperará el tiempo especificado, pero se reducirá el tiempo de espera si la señalización se activa antes de lo previsto (esto significa que el usuario no siempre tendrá que esperar durante todo el tiempo de espera). </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Haga clic en **[!UICONTROL Crear propiedad]**.
