---
description: Una propiedad web puede ser cualquier agrupación de uno o más dominios y subdominios incluida en un código incrustado y con una biblioteca de reglas.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;web property;property
title: Crear una propiedad web
topic: Developer and implementation
uuid: f19d5504-eb44-4d93-a387-7470ab4b3a3a
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Crear una propiedad web

Una propiedad web puede ser cualquier agrupación de uno o más dominios y subdominios incluida en un código incrustado y con una biblioteca de reglas.

>[!NOTE] Solo los usuarios con derechos de administrador pueden crear una propiedad. Para obtener más información sobre las funciones, consulte [Crear y administrar grupos en la DTM](https://marketing.adobe.com/resources/help/es_ES/dtm/groups.html) en la documentación del producto de Dynamic Tag Management.

Puede administrar y rastrear estos recursos con DTM. Por ejemplo, supongamos que tiene varios sitios web basados en una plantilla y quiere rastrear los mismos recursos en todos. Puede aplicar una propiedad web a varios dominios.

Para obtener información general sobre propiedades web y prácticas recomendadas, consulte [Propiedades web](https://marketing.adobe.com/resources/help/es_ES/dtm/web_property.html) en la documentación del producto de Dynamic Tag Management.

1. Navigate to your company page, then click **[!UICONTROL Add Property]**.

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
    <td colname="col2"> <p>Puede agregar y eliminar dominios si desea que los datos de visitante se mantengan entre dominios. Si se selecciona esta opción, los datos de la visita persisten entre los subdominios. </p> <p>Esta opción le permite especificar cómo desea rastrear el tráfico que se mueve entre los subdominios o dominios asociados. Los vínculos a subdominios se tratan como vínculos salientes. Las visitas a los subdominios se rastrean por separado. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. (Opcional) Configure [!UICONTROL Advanced Settings].

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
    <td colname="col2"> <p>Permite que se aprueben múltiples reglas para esta propiedad al mismo tiempo. La aprobación predeterminada solo permite la aprobación de una sola regla. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Habilitar publicación selectiva</span> </td> 
    <td colname="col2"> <p>Especifica si se permite a los usuarios seleccionar qué reglas aprobadas se publican. Ésta es la opción predeterminada. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Nombre de cookie de seguimiento</span> </td> 
    <td colname="col2"> <p>Anula el nombre de la cookie de seguimiento predeterminado. Puede personalizar el nombre que la administración dinámica de etiquetas utiliza para rastrear el estado de exclusión para recibir otras cookies. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Tiempo de espera de etiqueta</span> </td> 
    <td colname="col2"> <p>Especifica cuánto tiempo espera la administración dinámica de etiquetas a que se active una etiqueta antes de agotar el tiempo de espera y cancelar la solicitud de etiqueta. </p> <p> Debido al funcionamiento de la administración dinámica de etiquetas, no se preocupe de que este número sea elevado. La DTM cuenta con métodos eficaces para garantizar que las etiquetas lentas no afecten a la experiencia del usuario. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Retraso de anclaje</span> </td> 
    <td colname="col2"> <p>Especifica cuánto tiempo espera la administración dinámica de etiquetas para que las etiquetas se activen cuando se hace clic en los vínculos antes de pasar a la página siguiente. El valor predeterminado es 100 milisegundos. </p> <p>Un tiempo de espera superior mejora la precisión de seguimiento. Adobe recomienda un tiempo de espera de 500 milisegundos o menos, ya que el usuario no lo percibirá. </p> <p>La administración dinámica de etiquetas esperará hasta el tiempo especificado, pero si la señalización se activa antes, el retraso se acortará. (esto significa que el usuario no siempre tendrá que esperar durante todo el tiempo de espera). </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Haga clic en **[!UICONTROL Create Property]**.
