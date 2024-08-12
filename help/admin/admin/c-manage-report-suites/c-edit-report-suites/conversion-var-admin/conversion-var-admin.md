---
description: La variable de conversión de Custom Insight (o eVar) se coloca en el código de Adobe en las páginas web del sitio seleccionadas. Su principal función es segmentar las métricas de éxito de conversión en los informes de marketing personalizados. Una eVar puede basarse en visitas y funcionar de modo similar a las cookies. Los valores pasados a las variables eVar siguen al usuario durante un período de tiempo predeterminado.
keywords: eVar
title: Variables de conversión (eVar)
feature: Admin Tools
role: Admin
exl-id: 822ecaff-a06c-42e1-aee8-ef4a43df4230
source-git-commit: 72f223cd1962a468aa6c0772958ad6a99cfc1c39
workflow-type: tm+mt
source-wordcount: '1715'
ht-degree: 98%

---

# Variables de conversión (eVars)

La variable de conversión de Custom Insight (o eVar) se coloca en el código de Adobe en las páginas web del sitio seleccionadas. Su principal función es segmentar las métricas de éxito de conversión en los informes de marketing personalizados. Una eVar puede basarse en visitas y funcionar de modo similar a las cookies. Los valores pasados a las variables eVar siguen al usuario durante un período de tiempo predeterminado.

**[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]** > **[!UICONTROL Editar configuración]** > **[!UICONTROL Conversión]** > **[!UICONTROL Variables de conversión]**.

## Información general de variables de conversión (eVars)

Para ver un vídeo introductorio de las variables de conversión, consulte [Introducción a las variables de conversión](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/dimensions/introduction-to-conversion-variables-evars) en la guía Tutoriales de Analytics.

Cuando una eVar está establecida en un valor para un visitante, Adobe recuerda automáticamente ese valor hasta que caduque. Cualquier evento de éxito que encuentra el visitante mientras la eVar está activa se cuenta hacia el valor eVar.

El mejor uso de las eVars es para medir causa y efecto, como:

* Qué campañas internas influyeron en los ingresos
* Qué anuncios de banner tuvieron como resultado final un registro
* El número de veces que se usó una búsqueda interna antes de realizar un pedido

Si se desea realizar la medición de tráfico o las rutas, se recomienda utilizar variables de tráfico.

>[!NOTE]
>
>Se puede guardar un solo valor único en una eVar de una solicitud de imagen. Si quiere que haya varios valores en un valor eVar, le recomendamos que implemente [Variables de lista](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html?lang=es).

### Variables de conversión - Descripciones {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

Descripciones de los campos utilizados al [editar variables de conversión](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md).

| Elemento | Descripción |
| --- | --- |
| [!UICONTROL Nombre] | Nombre descriptivo de la variable de conversión. Así se le llama a la eVar en los informes generales, y será el nombre del informe/dimensión que aparecerá en el menú de la izquierda. |
| [!UICONTROL Tipo]  (solo eVar) | Tipo del valor de la variable:<ul><li>**[!UICONTROL Cadena de texto]**: Registra los valores de texto que se usan en el sitio. Este es el tipo más común de eVar y el valor predeterminado. Actúa de forma similar a otras variables, donde el valor incluido dentro es una cadena de texto estático. Si está realizando un seguimiento de elementos como campañas internas o palabras clave de búsqueda interna, esta es la configuración recomendada.</li><li>**[!UICONTROL Contador]**: Cuenta la cantidad de veces que se produce una acción antes del evento de éxito. Por ejemplo, si utiliza una eVar para seguir una búsqueda interna en el sitio, configure este valor en [!UICONTROL Cadena de texto] para rastrear el uso de los términos de búsqueda. Defina este valor en [!UICONTROL Contador] para contar la cantidad de búsquedas hechas, independientemente de los términos de búsqueda utilizados. Por ejemplo, puede usar una eVar de contador para rastrear el número de veces que alguien usó su búsqueda interna antes de realizar una compra.</li></ul> |
| [!UICONTROL Asignación] | Determina la forma en la que Analytics asigna crédito por un evento de éxito si una variable recibe varios valores antes del evento. Los valores admitidos son:<ul><li>**[!UICONTROL Más reciente]**: El último valor de la eVar siempre recibe el crédito por los eventos de éxito hasta que la eVar caduque.</li><li>**[!UICONTROL Valor original]**: La primera eVar siempre recibe crédito por los eventos de éxito hasta que la eVar caduque.</li><li>**[!UICONTROL Lineal]**: Asigna eventos de éxito de forma equitativa a través de todos los valores de la eVar. Debido a que la asignación lineal distribuye los valores de forma precisa solamente dentro de una visita, debe utilizar dicha asignación con una caducidad de visita para eVar.</li></ul> **Nota**: Si se cambia la asignación a Lineal o de Lineal, los datos históricos no se mostrarán. La combinación de tipos de asignación en la interfaz de informes puede llevar a una exposición incorrecta de los datos en los informes. Por ejemplo, la asignación Lineal puede dividir los ingresos entre un número de distintos valores de eVar. Después de volver a cambiar a la asignación Más reciente, el 100 % de esos ingresos se asociarán con el valor único más reciente. Esta asociación puede llevar a conclusiones incorrectas por parte de los usuarios.<br><br>Para evitar confusión en los informes, Adobe Analytics impide que la interfaz tenga acceso a los datos históricos. Esos datos se pueden ver si decide cambiar de nuevo la eVar a su valor de asignación inicial, pero no debería cambiar ese valor simplemente para acceder a los datos históricos. Adobe recomienda usar una eVar nueva cuando se desee otra configuración de asignación para los datos ya registrados, en lugar de cambiar la configuración de asignación en una eVar que ya dispone de una cantidad importante de datos históricos creados. |
| [!UICONTROL Caduca después de] | Especifica un período de tiempo o un evento tras el cual caduca el valor de la eVar (ya no recibe crédito por los eventos de éxito). Si se da un evento de éxito después de que caduque la eVar, el valor Ninguno recibe crédito por el evento (no había ninguna eVar activa).  Si selecciona un evento como valor de caducidad, la variable caducará solamente si ocurre el evento. Si no ocurre el evento, la variable no caducará nunca.  Las opciones de caducidad disponibles se pueden clasificar en cuatro categorías principales:<ul><li>**A nivel de visita o vista de página:** los eventos de conversión más allá de la vista de página o la visita no se asocian a la eVar.</li><li>**En función de un período de tiempo como día, semana, mes o año:** los eventos de conversión que no entren en el período de tiempo especificado no se asocian a la eVar. El período de caducidad se inicia al configurar la variable. Las eVar caducan según la hora en la que se establecieron, hasta el nivel de los segundos (minuto, hora, día, mes, etc.): <ul><li>MINUTO=60 segundos</li><li>HORA=3600 segundos (60 minutos)</li><li>DÍA=86 400 segundos (24 horas)</li><li>SEMANA=60 4800 segundos (7 días)</li><li>MES=2 678 400 segundos (31 días)</li><li>TRIMESTRE=8 035 200 segundos (93 días, 3 meses de 31 días)</li><li>AÑO=31 536 000 segundos (365 días)</li><br>Si una visita se inicia a las 7:00 AM un lunes y la eVar se establece en esa visita a las 7:15 AM, la caducidad se mostrará de esta forma:<li>Caducidad de día: eVar caduca a las 7:15 AM del martes.</li><li>Caducidad de semana: eVar caduca el lunes que viene a las 7:15 AM.</li><li>Caducidad de mes: eVar caduca dentro de 31 días desde el lunes a las 7:15 AM.</li></ul><li>**Eventos de conversión específicos:** cualquier otro evento de conversión que se active después de que el evento específico designado se asocie a la eVar.</li><li>**Nunca.** Siempre que la cookie visitorID está intacta, puede pasar cualquier periodo de tiempo entre la eVar y el evento.</li></ul> |
| [!UICONTROL Estado] (solo eVar) | Define el estado de la [!UICONTROL eVar]:<ul><li>**Desactivado**: Desactiva la [!UICONTROL eVar]. Quita la [!UICONTROL eVar] de la lista de variables de conversión.</li><li>**Sin subrelaciones**: Evita que se desglose la [!UICONTROL eVar] con una dimensión.</li><li>**Subrelaciones básicas**: Le permite desglosar una eVar con subrelaciones completas (por ejemplo, Products o Campaign).</li></ul> |
| [!UICONTROL Restablecer] | Restaura todos los valores existentes en la eVar. Utilice esta configuración al reutilizar una eVar, para no mezclar los valores antiguos con los informes nuevos. El restablecimiento no borra los datos históricos. |
| [!UICONTROL Comercialización] (solo eVar) | Las variables de comercialización pueden seguir una de dos sintaxis:<ul><li>**[!UICONTROL Sintaxis de productos]**: Asocia el valor de la eVar a un producto. **Nota**: Si la [!UICONTROL sintaxis de los productos] se selecciona, la sección de [!UICONTROL Evento de enlace de comercialización] se desactiva y no se puede seleccionar para la edición. Para esta sintaxis, los [!UICONTROL eventos de enlace] no son aplicables.</li><li>**[!UICONTROL Sintaxis de variables de conversión]**: Asocia la eVar a un producto solamente si ocurre un [!UICONTROL evento de enlace]. En este caso, usted selecciona los eventos que actúan como [!UICONTROL eventos de enlace].  Si cambia este valor sin actualizar adecuadamente el código JavaScript, se perderán datos. Consulte [Variables de comercialización](/help/components/dimensions/evar-merchandising.md).</li></ul> |
| [!UICONTROL Evento de enlace de comercialización] (solo eVar) | Si la comercialización está configurada como [!UICONTROL Sintaxis de variables de conversión], los eventos seleccionados relacionarán el valor eVar con un producto. Para utilizar un [!UICONTROL evento de enlace], establezca [!UICONTROL Asignación] en [!UICONTROL Más reciente]. Si la [!UICONTROL Asignación] es el [!UICONTROL Valor original], el primer enlace de producto de la eVar se mantendrá hasta que caduque la eVar. Para seleccionar varios eventos, mantenga presionada la tecla Ctrl (Windows) o Cmd (Mac) y haga clic en los distintos elementos de la lista. Solo puede seleccionar eventos si también se selecciona la opción [!UICONTROL Sintaxis de la variable de conversión]. |

### Caducidad

Las `eVars` caducan después del período de tiempo que especifique. Cuando la eVar caduca, ya no recibe el crédito por los eventos de éxito. Las eVars también se pueden configurar para que caduquen cuando se produzcan eventos de éxito. Por ejemplo, si tiene una promoción interna que caduca el final de una visita, la promoción interna recibe el crédito solo por las compras o registros que se produzcan durante la visita en la que se activaron.

Hay dos maneras de que una eVar caduque:

* Puede configurar la eVar para que caduque después de un período de tiempo o evento especificados.
* Puede forzar la caducidad de una eVar al restablecerla, lo que resulta útil cuando se cambia el propósito de una variable.

Por ejemplo, si cambia la caducidad de una eVar de 30 a 90 días, los valores de la eVar recopilados persistirán durante el nuevo conjunto de caducidad (en este caso, 90 días). El sistema simplemente observa la configuración de caducidad actual y la última marca de tiempo establecida del valor de eVar obtenido para determinar la caducidad. Solo la opción **[!UICONTROL Restablecer]** caduca los valores y lo hace de inmediato.

Otro ejemplo: si se usa una eVar en mayo para reflejar promociones internas y caduca después de 21 días, y en junio se usa para capturar palabras clave de búsqueda interna, el 1 de junio, debe forzar la caducidad o restablecer la variable. Al hacerlo, no se incluyen los valores de la promoción interna en los informes de junio.

### Distinción entre mayúsculas y minúsculas

Las eVars no distinguen entre mayúsculas y minúsculas. Las mayúsculas o minúsculas utilizadas en los informes se basan en el primer valor que registra el sistema backend. Este valor puede ser la primera instancia vista o puede variar en algún período de tiempo (por ejemplo, mensual), en función de la variedad y cantidad de datos asociados con el grupo de informes.

### Contadores

Aunque las eVars se usan habitualmente para guardar valores de cadena, también se pueden configurar para que actúen como contadores. Las eVars son útiles como contadores para contar el número de acciones que un usuario realiza antes de un evento. Por ejemplo, puede usar una eVar para capturar el número de búsquedas internas antes de la compra. Cada vez que un visitante realiza una búsqueda, la eVar debe contener un valor de &#39;+1&#39;. Si un visitante realiza cuatro búsquedas antes de una compra, verá una instancia con cada recuento total: 1.00, 2.00, 3.00 y 4.00. Sin embargo, solo el valor 4.00 recibe el crédito por el evento purchase (métricas de pedidos e ingresos). Solo se permiten números positivos como valores de un contador eVar.

## Adición o edición de variables de conversión

1. Haga clic en **[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]**.
1. Selección de un grupo de informes.
1. Haga clic en **[!UICONTROL Editar configuración]** > **[!UICONTROL Conversión]** > **[!UICONTROL Variables de conversión]**.
1. En la página [!UICONTROL Variables de conversión], haga clic en el icono **[!UICONTROL Expandir]** [+] situado junto a la variable de conversión que desee modificar.

   o

   Haga clic en **[!UICONTROL Agregar nuevo]** para agregar una eVar que no se esté utilizando al grupo de informes.
1. Seleccione los campos de la variable de conversión que desee modificar.

   Consulte [Variables de conversión: descripciones](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md#section_7C317BB0287A4B8EB0A1A4ECC40627BF). Algunos campos permiten escribir directamente en ellos. Otros permiten seleccionar una opción en una lista desplegable de valores admitidos.
1. Haga clic en **[!UICONTROL Guardar]**.
