---
description: Puede crear un nuevo grupo de informes seleccionando como modelo una plantilla predefinida o utilizando uno de los grupos de informes existentes.
title: Descargar la configuración del grupo de informes
feature: Report Suite Settings
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
exl-id: ea5f8543-058d-4e08-bc66-575e3a7460c2
TQID: https://experienceleague.adobe.com/9wZ2rIgzZtJduhFAx6XcD53H2qzB2SZMr0pbxCopBvk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
  - id: f52db89b-2666-4cad-9c50-9da4d3ffcfd0
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 541
ht-degree: 95%

---

# Descargar la configuración del grupo de informes

Puede crear un nuevo grupo de informes seleccionando como modelo una plantilla predefinida o utilizando uno de los grupos de informes existentes.

Descripción de los elementos utilizados al [crear un grupo de informes](/help/admin/tools/manage-rs/new-rs/t-create-a-report-suite.md).

>[!NOTE]
>
>La [documentación del grupo de informes virtuales](/help/components/vrs/c-workflow-vrs/vrs-create.md) le muestra cómo crear grupos de informes virtuales.

| Elemento | Descripción |
| --- | --- |
| ID del grupo de informes | Especifica un ID único que contiene solamente caracteres alfanuméricos. La ID no se puede cambiar una vez creada. Adobe establece el prefijo de ID necesario, que no se puede cambiar tampoco.  Cuando cree varios grupos de informes, asegúrese de que la convención de nomenclatura garantice ID de grupo de informes únicos. |
| Título del sitio | Identifica al grupo de informes en las Herramientas de administración. Este título también se utiliza en la lista desplegable Grupo de informes en el encabezado de grupo. |
| Zona horaria | Programa eventos y datos de marca de hora. |
| Dirección URL base | Define el dominio básico del grupo de informes (opcional). Esta URL funciona como filtro interno de URL si no se definen de forma explícita filtros internos de URL para el grupo de informes. |
| Página predeterminada | Reduce las repeticiones del valor Página predeterminada en las direcciones URL que encuentra (opcional). Si el informe Páginas más populares contiene direcciones URL en vez de nombres de páginas, esta opción evita que se registren varias URL para la misma página web.  Por ejemplo: las direcciones URL `https://example.com` y `https://example.com/index.html` suelen ser la misma página.<p> Puede quitar los nombres de archivo prescindibles para que ambas URL aparezcan como `https://example.com` en los informes. Si no se define este valor, Analytics quitará automáticamente los siguientes nombres de archivo de las direcciones URL: `index.htm`, `index.html`, `index.cgi`, `index.asp`, `default.htm`, `default.html`, `default.cgi`, `default.asp`, `home.htm`, `home.html`, `home.cgi` y `home.asp`. Para desactivar la depuración de nombres de archivos, especifique un valor de Página predeterminada que no aparezca nunca en las URL. |
| Fecha de lanzamiento | Informa a Adobe de la fecha en la que se espera que se active este grupo de informes. Si su programa de implementación cambia, indique el cálculo de tráfico actualizado mediante la herramienta Tráfico previsto permanente en  Administración del tráfico. |
| Vistas de la página estimadas por día | Indica la cantidad estimada de vistas de página que se espera que admita este grupo de informes cada día. Los volúmenes grandes de tráfico requieren un proceso de aprobación más largo. Para evitar que se retrase el procesamiento, indique una estimación lo más precisa que sea posible. |
| Moneda base | Especifica la divisa predeterminada que se usará para almacenar todos los datos monetarios. Analytics convierte las transacciones en otras monedas a la moneda base mediante la tasa de conversión vigente en el momento de recibir los datos. La creación de informes de análisis utiliza la variable de JavaScript currencyCode para identificar la moneda de una transacción determinada. |
| Habilitar el procesamiento de palabras japonesas | Habilita la compatibilidad con caracteres multibyte en el grupo de informes. Si se desactiva la compatibilidad con caracteres multibyte, el sistema supondrá que los datos están en formato `ISO-8859-1` Las páginas Web deben especificar su conjunto de caracteres en la variable de JavaScript charSet. <p>La compatibilidad con caracteres multibyte almacena los caracteres del grupo de informes en UTF-8. El sistema, al recibir los datos del conjunto de caracteres de la página web, los convierte al conjunto de caracteres UTF-8, para que pueda utilizar cualquier idioma en los informes de marketing.  Para cambiar la compatibilidad de caracteres multibyte en un grupo de informes existente, póngase en contacto con el equipo de cuentas de Adobe o el Servicio de atención al cliente. |
| Usar menú de navegación simplificado | Esta característica era parte de [Reports &amp; Analytics] (¿https://new.express.adobe.com/webpage/WFCyq7w8kijmB?), que ya no es compatible. |

{style="table-layout:auto"}
