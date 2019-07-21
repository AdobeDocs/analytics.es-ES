---
description: Una propiedad web puede ser cualquier agrupación de uno o más dominios y subdominios incluida en un código incrustado y con una biblioteca de reglas.
keywords: Implementación de Analytics; método de implementación; administración dinámica de etiquetas; dtm; web property; propiedad
seo-description: Una propiedad web puede ser cualquier agrupación de uno o más dominios y subdominios incluida en un código incrustado y con una biblioteca de reglas.
seo-title: Crear propiedad web
solution: Analytics
title: Crear propiedad web
topic: Desarrollador e implementación
uuid: f 19 d 5504-eb 44-4 d 93-a 387-7470 ab 4 b 3 a 3 a 3
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Crear propiedad web

Una propiedad web puede ser cualquier agrupación de uno o más dominios y subdominios incluida en un código incrustado y con una biblioteca de reglas.

>[!NOTE]
>
>Solo un usuario con derechos de administrador puede crear una propiedad. For more information about roles, see [Create and Manage Groups in DTM](https://marketing.adobe.com/resources/help/en_US/dtm/groups.html) in the Dynamic Tag Management Product Documentation.

Puede administrar y rastrear estos recursos con DTM. Por ejemplo, supongamos que tiene varios sitios web basados en una plantilla y quiere rastrear los mismos recursos en todos. Puede aplicar una propiedad web a varios dominios.

Para obtener información general sobre propiedades web y consejos, consulte [Propiedades web](https://marketing.adobe.com/resources/help/en_US/dtm/web_property.html) de Documentación del producto de la administración dinámica de etiquetas.

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
    <td colname="col1"> <span class="uicontrol"> Dirección URL</span> </td> 
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
