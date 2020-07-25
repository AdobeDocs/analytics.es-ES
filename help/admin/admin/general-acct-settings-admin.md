---
description: Descripciones de los campos de configuración general de la cuenta para grupos de informes en Administradores.
title: Configuración general de la cuenta
topic: Admin tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
translation-type: tm+mt
source-git-commit: aa8a82576d6790d3592767960d864eb58f482eec
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 100%

---


# Configuración general de la cuenta

Descripciones de los campos de configuración general de la cuenta para un grupo de informes en Administradores.

**[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]** > **[!UICONTROL Editar configuración]** > **[!UICONTROL General]** > **[!UICONTROL Configuración de la cuenta generales]**

Estos valores de configuración contienen opciones de edición para la funcionalidad básica del grupo de informes como, por ejemplo, nombre y zona horaria.

| Opción | Descripción |
|--- |--- |
| Título del sitio | Identifica el sitio. Asigne a cada grupo de informes un título de sitio único. |
| Dirección URL base | Especifica el sitio web principal del grupo de informes. La URL básica no afecta al filtrado de referentes. En su lugar, utilice [filtros de URL internos](/help/admin/admin/internal-url-filter-admin.md). |
| Zona horaria | Determina la fecha y la hora asociadas con los datos del informe.  Si se cambia la zona horaria de un grupo de informes activo, se creará un pico o un hueco en los datos del informe. Para minimizar el impacto, Adobe recomienda cambiar de zona horaria durante las horas de menor actividad; de este modo, se evita alterar los datos.  Por ejemplo, si cambia la zona horaria del grupo de informes de Turquía a Portugal a las 3 de la tarde, la hora actual del grupo de informes pasará a ser la 1. Dado que los informes ya han recopilado los datos de la 1, en los informes aparecerá un pico de tráfico entre la 1 y las 3.  Por otra parte, si cambia la zona horaria del grupo de informes de Portugal a España a las 3 de la tarde, la hora actual del grupo de informes pasará a ser las 4. En los informes no aparecerá ningún dato entre las 3 y las 4 de la tarde el día que se cambie la hora. |
| Página predeterminada | Si el informe [!UICONTROL Páginas más populares] contiene direcciones URL en lugar de nombres de páginas, esta configuración evita que varias URL representen a la misma página. Por ejemplo: las direcciones URL `https://mysite.com` y `https://mysite.com/index.html` suelen ser la misma página. Puede quitar los nombres de archivo predeterminados para que estas dos direcciones URL se muestren como `https://mysite.com`.  Si se deja en blanco, los siguientes nombres de archivo se eliminarán de las direcciones URL: index.htm, index.html, index.cgi, index.asp, default.htm, default.html, default.cgi, default.asp, home.htm, home.html, home.cgi y home.asp.  Para no desactivar por completo la depuración de nombre de archivo, ingrese un valor que nunca esté presente en las direcciones URL. |
| Reemplazar el último octeto de direcciones IP por 0 | La eliminación del último octeto se realiza antes del filtrado de IP. Como tal, el último octeto se sustituye por un 0 y las reglas de exclusión de la IP se deben actualizar para coincidir con las direcciones de IP que tengan un cero al final. Un * coincidente debe corresponder a un 0. Si activa esta opción, la dirección IP se modifica antes de procesarse. Por ejemplo, si la dirección IP 134.123.567.780 se cambia a 134.123.567.0., los datos de segmentación geográfica no serán tan exactos como cuando se utiliza la dirección IP completa. En concreto, la precisión de ciudad se verá más afectada que la precisión de país o región. Tanto las reglas de Bot como las reglas de VISTA se ven afectadas porque ninguna de las direcciones IP está disponible para estas. Además, esta opción afecta a todas las reglas de procesamiento basadas en IP, incluidas las reglas de canal de marketing y las reglas de procesamiento de grupo de informes. <br> **Nota**: Esta configuración está habilitada por defecto para cualquier grupo de informes creado en el Centro de datos de Londres a partir de enero de 2019, pero solo si la configuración de dichos grupos de informes se copia de una plantilla incluida en Admin Console. Los grupos de informes cuya configuración esté duplicada desde otros grupos de informes heredarán toda la configuración del grupo de informes seleccionado. |
| Confusión de IP | Convierte las direcciones IP en cadenas irreconocibles, lo que esencialmente las elimina de los almacenes de datos de Adobe. Cuando la confusión de IP está activada, las direcciones IP originales se pierden de forma permanente. <br> **Nota**: Las direcciones IP se confunden en cualquier lugar de Analytics, incluido el Data Warehouse. Sin embargo, la configuración de la IP en el destino se controla de forma independiente, por lo que no influye en el destino.<br> Si la confusión de la IP está habilitada, la exclusión de la IP se produce antes de que la dirección IP se confunda, por lo que los clientes no necesitan cambiar nada cuando habilitan la confusión de la IP. <br> Si activa **Deshabilitado**, se respeta la dirección IP de los datos. <br> La activación de la opción **Proteger direcciones IP** cambia la IP a un valor hash (p. ej., 234abc6493872038). <br> Si activa la opción **Eliminar direcciones IP**, se sustituye la dirección IP por x.x.x.x en los datos después de la búsqueda geográfica. <br> **Nota**: Esta configuración puede requerir cambios en las [reglas de bots](/help/admin/admin/bot-removal/bot-rules.md) personalizadas o en las [exclusiones de IP](/help/admin/admin/exclude-ip.md). |
| Almacenamiento del ID de transacción | Permite utilizar las fuentes de datos de [ID de la transacción](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md). |
| Activar Ad Hoc Analysis | Indica si el grupo de informes en cuestión se muestra como un grupo de informes disponible en un Ad Hoc Analysis. Utilice esta configuración para limitar los grupos de informes que aparecerán como opción en el Ad Hoc Analysis. Por ejemplo, puede deshabilitar el Ad Hoc Analysis para grupos de informes de desarrollo e informes de QA. |
| Habilitar Data Warehouse | Permite habilitar la IU de Data Warehouse en Analytics > Herramientas > Almacén de datos. |
