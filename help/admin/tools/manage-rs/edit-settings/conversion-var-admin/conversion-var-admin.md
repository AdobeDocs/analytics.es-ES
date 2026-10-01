---
description: La variable de conversión de Custom Insight (o eVar) se coloca en el código de Adobe en las páginas web del sitio seleccionadas. Su principal función es segmentar las métricas de éxito de conversión en los informes de marketing personalizados. Una eVar puede basarse en visitas y funcionar de modo similar a las cookies. Los valores pasados a las variables eVar siguen al usuario durante un período de tiempo predeterminado.
keywords: eVar
title: Variables de conversión (eVar)
feature: Admin Tools
role: Admin
exl-id: 822ecaff-a06c-42e1-aee8-ef4a43df4230
TQID: https://experienceleague.adobe.com/rYLxVYB1oDyfEk8gQyesTSRRPHid-6zJ8QaqFG2b0Kc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: ca917b867cd84b09b899ce7b72586f0b15003106
workflow-type: tm+mt
source-wordcount: '1726'
ht-degree: 44%
---
# Variables de conversión (eVars)

La variable de conversión de Custom Insight (o eVar) se coloca en el código de Adobe en las páginas web del sitio seleccionadas. Su principal función es segmentar las métricas de éxito de conversión en los informes de marketing personalizados. Una eVar puede basarse en visitas y funcionar de modo similar a las cookies. Los valores pasados a las variables eVar siguen al usuario durante un período de tiempo predeterminado.

**[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]** > **[!UICONTROL Editar configuración]** > **[!UICONTROL Conversión]** > **[!UICONTROL Variables de conversión]**.

## Información general de variables de conversión (eVars)

Para ver un vídeo introductorio de las variables de conversión, consulte [Introducción a las variables de conversión](https://experienceleague.adobe.com/es/docs/analytics-learn/tutorials/analysis-workspace/dimensions/introduction-to-conversion-variables-evars) en la guía Tutoriales de Analytics.

Cuando una eVar está establecida en un valor para un visitante, Adobe recuerda automáticamente ese valor hasta que caduque. Cualquier evento de éxito que encuentra el visitante mientras la eVar está activa se cuenta hacia el valor eVar.

El mejor uso de las eVars es para medir causa y efecto, como:

* Qué campañas internas influyeron en los ingresos
* Qué anuncios de banner tuvieron como resultado final un registro
* El número de veces que se usó una búsqueda interna antes de realizar un pedido

Si se desea realizar la medición de tráfico o las rutas, se recomienda utilizar variables de tráfico.

>[!NOTE]
>
>Se puede guardar un solo valor único en una eVar de una solicitud de imagen. Si desea usar varios valores en un valor eVar, use [Variables de lista](/help/implement/vars/page-vars/page-variables.md).

### Variables de conversión - Descripciones {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

| Elemento | Descripción |
| --- | --- |
| [!UICONTROL Estado] | Determina si eVar está activo:<ul><li>**[!UICONTROL Habilitado]**: eVar está activo.</li><li>**[!UICONTROL Deshabilitado]**: deshabilita eVar y lo quita de la lista de variables de conversión.</li></ul> |
| [!UICONTROL Descripción] | Una descripción opcional de eVar. Utilícela para documentar lo que eVar captura y cómo se implementa. |
| [!UICONTROL Nombre] | Nombre de dimensión descriptivo de la variable de conversión. Así es como se hace referencia a eVar en los informes generales. |
| [!UICONTROL Asignación] | Determina la forma en la que Analytics asigna crédito por un evento de éxito si una variable recibe varios valores antes del evento. Los valores admitidos son:<ul><li>**[!UICONTROL Más reciente (último)]**: El último valor de eVar siempre recibe el crédito por los eventos de éxito hasta que la eVar caduque.</li><li>**[!UICONTROL Valor original (primero)]**: El primer eVar siempre recibe el crédito por los eventos de éxito hasta que la eVar caduque.</li><li>**[!UICONTROL Lineal]**: Asigna eventos de éxito de forma equitativa a través de todos los valores de la eVar. Dado que la asignación lineal distribuye los valores solo dentro de una visita, utilice la asignación lineal con una caducidad de visita de eVar o inferior. Esta opción no está disponible para eVars de comercialización.</li></ul>**Importante**: Adobe recomienda no cambiar de la asignación [!UICONTROL Lineal] a o desde ella, ya que oculta los datos históricos en los informes hasta que vuelva a cambiar. Para cambiar la asignación en una eVar con un historial significativo, Adobe recomienda utilizar una nueva eVar en su lugar. |
| [!UICONTROL Caduca después de] | Especifica cuándo caduca el valor de la eVar (ya no recibe crédito por los eventos de éxito). Si se da un evento de éxito después de que caduque la eVar, el valor Ninguno recibe crédito por el evento (no había ninguna eVar activa). Los valores admitidos son:<ul><li>**[!UICONTROL Visita]**: El valor caduca al final de la visita.</li><li>**[!UICONTROL Visita]**: El valor solo se aplica a la visita en la que está establecido.</li><li>**[!UICONTROL Minuto]**, **[!UICONTROL Hora]**, **[!UICONTROL Día]**, **[!UICONTROL Semana]**, **[!UICONTROL Mes]**, **[!UICONTROL Trimestre]** o **[!UICONTROL Año]**: El valor caduca una cantidad fija de tiempo después de establecerse, a la segunda:<ul><li>Minuto = 60 segundos</li><li>Hora = 3600 segundos (60 minutos)</li><li>Día = 86400 segundos (24 horas)</li><li>Semana = 604800 segundos (7 días)</li><li>Mes = 2678400 segundos (31 días)</li><li>Trimestre = 8035200 segundos (93 días - 3 meses de 31 días)</li><li>Año = 31536000 segundos (365 días)</li></ul>Por ejemplo, si se establece un eVar a las 7:15 AM del lunes, la caducidad de [!UICONTROL Day] finaliza a las 7:15 AM del martes, la caducidad de [!UICONTROL Week] finaliza a las 7:15 AM del lunes siguiente y la caducidad de [!UICONTROL Month] finaliza 31 días después a las 7:15 AM.</li><li>**[!UICONTROL Personalizado]**: El valor caduca después del número de días especificado (86400 segundos por día).</li><li>**Un evento** ([!UICONTROL Compra], [!UICONTROL Vista del producto], [!UICONTROL Apertura del carro de compras], [!UICONTROL Cierre de compra del carro de compras], [!UICONTROL Adición del carro de compras], [!UICONTROL Eliminación del carro de compras], [!UICONTROL Vista del carro de compras] o un evento personalizado): El valor caduca cuando se produce el evento seleccionado. Si el evento nunca se produce, el valor nunca caduca.</li><li>**[!UICONTROL Nunca]**: Siempre que un visitante utilice el mismo identificador, puede pasar cualquier cantidad de tiempo entre el eVar y el evento.</li></ul> |
| [!UICONTROL Tipo] | Tipo del valor de la variable:<ul><li>**[!UICONTROL Cadena de texto]**: Captura valores de texto. Es el tipo más común de eVar y la configuración predeterminada. Actúa de forma similar a otras variables, donde el valor incluido dentro es una cadena de texto estático. Si realiza un seguimiento de elementos como campañas internas o palabras clave de búsqueda interna, se recomienda esta configuración.</li><li>**[!UICONTROL Contador]**: Cuenta la cantidad de veces que se produce una acción antes del evento de éxito. Por ejemplo, puede contar el número de búsquedas realizadas, independientemente de los términos de búsqueda utilizados, antes de un evento de éxito.</li></ul> |
| [!UICONTROL Restablecer] | Al guardar, caduca inmediatamente todos los valores persistentes del lado del servidor para esta variable en todos los visitantes, incluidos los enlaces de productos de comercialización. Use [!UICONTROL Restablecer] al reutilizar un eVar para no mezclar valores antiguos con informes nuevos. **El restablecimiento no borra los datos históricos.** |
| [!UICONTROL Habilitar comercialización] | Los valores admitidos son:<ul><li>**[!UICONTROL Deshabilitado]**: eVar acredita los eventos de éxito al valor que persiste para el visitante.</li><li>**[!UICONTROL Habilitado]**: eVar se convierte en un eVar de comercialización que enlaza valores a productos individuales. Los eventos de éxito de cada producto se acreditan al valor enlazado a ese producto. Al habilitar la comercialización, se muestra la configuración de [!UICONTROL Comercialización] y [!UICONTROL Evento de enlace de comercialización], y se elimina la asignación [!UICONTROL Lineal].</li></ul>Habilite la comercialización solo para eVars que describan cómo se encuentran o compran los productos. Un eVar de comercialización ya no acredita eventos de éxito que no están vinculados a un producto. Consulte [eVar (comercialización)](/help/components/dimensions/evar-merchandising.md). |
| [!UICONTROL Comercialización] | Determina de dónde proviene el valor para enlazar a productos:<ul><li>**[!UICONTROL Sintaxis del producto]**: El valor se establece en cada producto de la variable `products` y se enlaza a ese producto en esa visita. Cada producto puede tener un valor diferente. No se usan eventos de enlace, por lo que [!UICONTROL Evento de enlace de comercialización] está deshabilitado.</li><li>**[!UICONTROL Sintaxis de la variable de conversión]**: el valor se establece en el propio eVar y persiste como valor de ensayo, reflejando siempre el valor enviado más recientemente, independientemente de [!UICONTROL Asignación]. El valor se enlaza a los productos en una visita solo si esa visita contiene un [!UICONTROL evento de enlace de comercialización] seleccionado. Todos los productos de esa visita reciben el mismo valor.</li></ul>Si cambia esta configuración sin actualizar la implementación en consecuencia, se perderán datos. Consulte [eVar (variable de comercialización)](/help/implement/vars/page-vars/evar-merchandising.md) para obtener detalles de implementación. |
| [!UICONTROL Evento de enlace de comercialización] | Solo está disponible cuando [!UICONTROL Merchandising] está establecido en [!UICONTROL Sintaxis de la variable de conversión]. Determina qué eventos o eVars enlazan el valor ensayado de eVar a los productos de la misma visita. Si no selecciona un evento de enlace, se usará [!UICONTROL All]. Los valores admitidos son:<ul><li>**[!UICONTROL Todos]**: cualquier otro evento o eVar en el enlace de déclencheur de visita. Esta configuración es la predeterminada.</li><li>**[!UICONTROL Evento de compra]**, **[!UICONTROL Evento de vista de producto]**, **[!UICONTROL Evento de apertura del carro de compras]**, **[!UICONTROL Evento de cierre de compra del carro de compras]**, **[!UICONTROL Evento de adición al carro de compras]**, **[!UICONTROL Evento de eliminación del carro de compras]** o **[!UICONTROL Evento de vista del carro de compras]**: el enlace se produce en las visitas que contienen el evento seleccionado.</li><li>**[!UICONTROL Evento de campaña]**: el enlace se produce en las visitas que contienen una instancia de la dimensión [Código de seguimiento](/help/components/dimensions/tracking-code.md) (variable [`campaign`](/help/implement/vars/page-vars/campaign.md)).</li><li>**Un evento personalizado**: el enlace se produce en las visitas que contienen el evento personalizado seleccionado.</li><li>**Un eVar personalizado**: el enlace se produce en las visitas que establecen el eVar seleccionado.</li></ul>Las props no pueden enlazar en déclencheur. Para seleccionar varios valores, mantenga presionada la tecla Ctrl (Windows) o Cmd (Mac) y haga clic en los distintos elementos de la lista. Cuando un producto específico que ya está enlazado a un eVar recibe otro enlace con ese mismo eVar, [!UICONTROL Asignación] determina qué valor se guarda. |

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

Aunque las eVars se usan habitualmente para guardar valores de cadena, también se pueden configurar para que actúen como contadores. Las eVars son útiles como contadores para contar el número de acciones que un usuario realiza antes de un evento. Por ejemplo, puede usar una eVar para capturar el número de búsquedas internas antes de la compra. Cada vez que un visitante realiza una búsqueda, la eVar debe contener un valor de &#39;+1&#39;. Si un visitante realiza cuatro búsquedas antes de una compra, verá una instancia con cada recuento total: 1.00, 2.00, 3.00 y 4.00. Sin embargo, solo el valor 4,00 recibe crédito por el evento purchase (métricas de pedidos e ingresos). Solo se permiten números positivos como valores de un contador eVar.

## Adición o edición de variables de conversión

1. Haga clic en **[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]**.
1. Selección de un grupo de informes.
1. Haga clic en **[!UICONTROL Editar configuración]** > **[!UICONTROL Conversión]** > **[!UICONTROL Variables de conversión]**.
1. En la página [!UICONTROL Variables de conversión], haga clic en el icono **[!UICONTROL Expandir]** [+] situado junto a la variable de conversión que desee modificar.

   o

   Haga clic en **[!UICONTROL Agregar nuevo]** para agregar una eVar que no se esté utilizando al grupo de informes.
1. Seleccione los campos de la variable de conversión que desee modificar.

   Consulte [Variables de conversión: descripciones](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md#section_7C317BB0287A4B8EB0A1A4ECC40627BF). Algunos campos permiten escribir directamente en ellos. Otros permiten seleccionar una opción en una lista desplegable de valores admitidos.
1. Haga clic en **[!UICONTROL Guardar]**.
