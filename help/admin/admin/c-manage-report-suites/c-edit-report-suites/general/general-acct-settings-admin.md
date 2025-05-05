---
description: Descripciones de los campos de configuración general de la cuenta para grupos de informes en Administradores.
title: Configuración general de la cuenta
feature: Admin Tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
exl-id: f49babb2-8e26-4cc6-b264-b4d7be93f130
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 83%

---

# Configuración general de la cuenta

Descripciones de los campos de configuración general de la cuenta para un grupo de informes en Administradores.

**[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]** > **[!UICONTROL Editar configuración]** > **[!UICONTROL General]** > **[!UICONTROL Configuración de la cuenta generales]**

Estos valores de configuración contienen opciones de edición para la funcionalidad básica del grupo de informes como, por ejemplo, nombre y zona horaria.


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuración general de la cuenta](https://video.tv.adobe.com/v/3411505/?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]

| Opción | Descripción |
|--- |--- |
| Título del sitio | Identifica el sitio. Asigne a cada grupo de informes un título de sitio único. |
| Dirección URL base | Especifica el sitio web principal del grupo de informes. La URL básica no afecta al filtrado de referentes. En su lugar, use [filtros de URL internos](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md). |
| Zona horaria | Determina la fecha y la hora asociadas con los datos del informe.  Si se cambia la zona horaria de un grupo de informes activo, se creará un pico o un hueco en los datos del informe. Para minimizar el impacto, Adobe recomienda cambiar de zona horaria durante las horas de menor actividad; de este modo, se evita alterar los datos.  Por ejemplo, si cambia la zona horaria del grupo de informes de Turquía a Portugal a las 3 de la tarde, la hora actual del grupo de informes pasará a ser la 1. Dado que los informes ya han recopilado los datos de la 1, en los informes aparecerá un pico de tráfico entre la 1 y las 3.  Por otra parte, si cambia la zona horaria del grupo de informes de Portugal a España a las 3 de la tarde, la hora actual del grupo de informes pasará a ser las 4. En los informes no aparecerá ningún dato entre las 3 y las 4 de la tarde el día que se cambie la hora. |
| Página predeterminada | Si el informe [!UICONTROL Páginas más populares] contiene direcciones URL en lugar de nombres de páginas, esta configuración evita que varias URL representen a la misma página. Por ejemplo: las direcciones URL `https://example.com` y `https://example.com/index.html` suelen ser la misma página. Puede quitar los nombres de archivo predeterminados para que estas dos direcciones URL se muestren como `https://example.com`.  Si se deja en blanco, los siguientes nombres de archivo se eliminarán de las direcciones URL: index.htm, index.html, index.cgi, index.asp, default.htm, default.html, default.cgi, default.asp, home.htm, home.html, home.cgi y home.asp.  Para no desactivar por completo la depuración de nombre de archivo, ingrese un valor que nunca esté presente en las direcciones URL. |
| Reemplazar el último octeto de direcciones IP por 0 | Cuando está habilitado, reemplaza el último octeto de direcciones IP por un cero. Esto ocurre antes de que se rellenen los informes relacionados con la ubicación geográfica, por lo que puede afectar a la precisión de estos informes. |
| Confusión de IP | Convierte las direcciones IP en cadenas irreconocibles, lo que esencialmente las elimina de los almacenes de datos de Adobe. Cuando la confusión de IP está habilitada, las direcciones IP originales se pierden de forma permanente. <br> **Nota**: Las direcciones IP se confunden en cualquier lugar de Analytics, incluido el Data Warehouse. Sin embargo, la configuración de la IP en Target se controla de forma independiente, por lo que no influye en Target.<br> Si la confusión de IP está habilitada, todo el procesamiento necesario, incluido el filtrado/exclusión de la IP, las reglas de bots y las búsquedas de segmentación geográfica, se realiza antes de que la dirección IP se confunda. No es necesario que cambie nada al habilitar la confusión de IP.<ul><li>Si activa la opción **Deshabilitado**, se respeta la dirección IP de los datos.</li><li>Si activa la opción **Confundir dirección IP**, se cambia la IP a dos puntos seguidos de un valor hash (p. ej., `::1932023538`).</li><li>Si activa la opción **Eliminar dirección IP**, se sustituye la dirección IP por `::X.X.X.X` en los datos después de la búsqueda geográfica.</li></ul>**Nota**: esta configuración podría requerir cambios en las [reglas de bots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) o en las [exclusiones de IP](/help/admin/admin/exclude-ip.md) personalizadas.<br> **Nota**: Los datos recopilados mediante Web SDK pueden tener una confusión de IP aplicada en el Edge Network a través de [configuración de flujo de datos](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es#@advanced-options). Si la confusión de la IP se aplica en el Edge Network, ya se confunde cuando llega a Analytics. Esta ofuscación afecta tanto a las reglas como a las búsquedas geográficas. |
| Almacenamiento del ID de transacción | Permite utilizar las fuentes de datos de [ID de la transacción](/help/import/data-sources/transactionid.md). |
| Habilitar Data Warehouse | Permite habilitar la IU de Data Warehouse en Analytics > Herramientas > Almacén de datos. |
| Opción Zip | Permite especificar el código postal en lugar de usar el que produce nuestra búsqueda geográfica de IP. |
| Compatibilidad con caracteres multibyte | La compatibilidad con caracteres multibyte almacena los caracteres del grupo de informes en UTF-8. El sistema, al recibir los datos del conjunto de caracteres de la página web, los convierte al conjunto de caracteres UTF-8, para que pueda utilizar cualquier idioma en los informes de marketing. Para cambiar la compatibilidad de caracteres multibyte en un grupo de informes existente, póngase en contacto con el equipo de cuentas de Adobe o el Servicio de atención al cliente. |
| Activado | Especifica si este grupo de informes está activado o no. |
| Moneda base | Permite especificar la [moneda](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/currencycode.html?lang=es) base para este grupo de informes. |
| ID de organización | El ID asociado con la compañía que ha seleccionado en Experience Cloud. Se trata de una cadena alfanumérica de 24 caracteres seguida de @AdobeOrg (que debe incluirse). |
