---
description: Descripciones de los campos de configuración general de la cuenta para grupos de informes en Administradores.
title: Configuración general de la cuenta
feature: Admin Tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
exl-id: f49babb2-8e26-4cc6-b264-b4d7be93f130
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 88%

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
| Página predeterminada | Si el informe [!UICONTROL Páginas más populares] contiene direcciones URL en lugar de nombres de páginas, esta configuración evita que varias URL representen a la misma página. Por ejemplo: las direcciones URL `https://example.com` y `https://example.com/index.html` suelen ser la misma página. Puede quitar los nombres de archivo predeterminados para que estas dos direcciones URL se muestren como `https://example.com`.  Si se deja en blanco, los siguientes nombres de archivo se eliminarán de las direcciones URL: index.htm, index.html, index.cgi, index.asp, default.htm, default.html, default.cgi, default.asp, home.htm, home.html, home.cgi y home.asp.  Para no desactivar por completo la depuración de nombre de archivo, ingrese un valor que nunca esté presente en las direcciones URL. |
| Reemplazar el último octeto de direcciones IP por 0 | La eliminación del último octeto se realiza antes de que se realice cualquier procesamiento en la visita, incluso antes del filtrado/exclusión de IP, antes de comprobar las reglas de bots, antes de las búsquedas de Segmentación geográfica, etc. Como tal, el último octeto se sustituye por un 0 y las reglas de exclusión de la IP se deben actualizar para coincidir con las direcciones de IP que tengan un cero al final. Un * coincidente debe corresponder a un 0. Por ejemplo, si la dirección IP 11.22.33.44 se cambia a 11.22.33.0., los datos de segmentación geográfica no serán tan exactos como cuando se utiliza la dirección IP completa. En concreto, la precisión de ciudad se verá más afectada que la precisión de país o región. Tanto las reglas de Bot como las reglas de VISTA se ven afectadas porque ninguna de las direcciones IP está disponible para estas. Además, esta opción afecta a todas las reglas de procesamiento basadas en IP, incluidas las reglas de canal de marketing y las reglas de procesamiento de grupo de informes. <br> **Nota**: Esta configuración está habilitada por defecto para cualquier grupo de informes creado en el Centro de datos de Londres a partir de enero de 2019, pero solo si la configuración de dichos grupos de informes se copia de una plantilla incluida en Admin Console. Los grupos de informes cuya configuración esté duplicada desde otros grupos de informes heredarán toda la configuración del grupo de informes seleccionado. |
| Confusión de IP | Convierte las direcciones IP en cadenas irreconocibles, lo que esencialmente las elimina de los almacenes de datos de Adobe. Cuando la confusión de IP está activada, las direcciones IP originales se pierden de forma permanente.  <br> **Nota**: Las direcciones IP se confunden en cualquier lugar de Analytics, incluido el Data Warehouse. Sin embargo, la configuración de la IP en el destino se controla de forma independiente, por lo que no influye en el destino.<br> Si la confusión de la IP está habilitada, todo el procesamiento necesario, incluido el filtrado/exclusión de la IP, las reglas de bots y las búsquedas de segmentación geográfica, se realizan antes de que la dirección IP se confunda. No es necesario que cambie nada al habilitar la confusión de IP.<ul><li>Si activa **Deshabilitado**, se respeta la dirección IP de los datos.</li><li>La activación de la opción **Proteger dirección IP** cambia la IP a dos puntos seguidos de un valor hash (por ejemplo, `::1932023538`).</li><li>Si activa la opción **Eliminar direcciones IP**`::X.X.X.X`, se sustituye la dirección IP por en los datos después de la búsqueda geográfica.</li></ul>**Nota**: Esta configuración puede requerir cambios en las [reglas de bots](/help/admin/admin/bot-removal/bot-rules.md) personalizadas o en las [exclusiones de IP](/help/admin/admin/exclude-ip.md). |
| Almacenamiento del ID de transacción | Permite utilizar las fuentes de datos de [ID de la transacción](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md). |
| Habilitar Data Warehouse | Permite habilitar la IU de Data Warehouse en Analytics > Herramientas > Almacén de datos. |
