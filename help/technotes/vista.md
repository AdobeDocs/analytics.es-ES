---
title: Reglas VISTA en Adobe Analytics
description: Más información sobre las reglas VISTA y sus funcionalidades.
exl-id: fab2acc3-b037-48f9-bb20-625ccb75b4cc
feature: Analytics Basics
TQID: https://experienceleague.adobe.com/x3pRtt4sTKGPnD30xXJWIX6OEjaDWHED-S2-0BXCcDg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 354
ht-degree: 57%

---

# Reglas VISTA en Adobe Analytics

Las reglas VISTA son una forma alternativa de modificación de datos personalizados que se pueden aplicar entre la recopilación de datos y el procesamiento. Consulte [Orden de procesamiento](processing-order.md) para obtener más información sobre la fase exacta de la canalización de datos que se aplican a las reglas VISTA. Las reglas VISTA solo afectan a los datos actuales a medida que se recopilan, no altera los datos existentes.

Algunos casos de uso comunes de las reglas VISTA son:

* Copiar una visita de Analytics de un grupo de informes a otro, si lo desea, modificar los datos del grupo de informes copiado
* Exclusión de IP personalizada que supera los casos de uso ofrecidos por [Excluir por dirección IP](/help/admin/tools/exclude-ip.md)
* Modificar condicional o globalmente cualquier valor de variable
* Duplicar valores de variables a otras variables
* Cargar archivos a un sitio FTP de Adobe que pueda afectar a los valores de las variables

Muchos casos de uso para las reglas VISTA ya los ofrece [Reglas de procesamiento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md), [Reglas de bots](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md), [Grupos de informes virtuales](/help/components/vrs/vrs-about.md) o simplemente actualizando su implementación de Adobe Analytics. Adobe recomienda las reglas VISTA solo como último recurso.

>[!IMPORTANT]
>
>La implementación y configuración de reglas VISTA requieren un acuerdo de pago entre su organización y Adobe Professional Services. Póngase en contacto con el equipo de cuenta de Adobe si desea crear o actualizar una regla VISTA.
>
>Tenga en cuenta:
>
>* La creación de reglas VISTA incluye solo la implementación inicial. Las actualizaciones de mantenimiento en curso o de reglas VISTA requieren una participación de pago independiente.
>
>* Las reglas VISTA dependen de condiciones específicas de los datos. Por ejemplo, los cambios en la implementación de Adobe Analytics, los tipos de datos o las longitudes de cadenas que se recopilan, los cambios en las tablas utilizadas para DB VISTA u otros cambios en los patrones de datos de entrada podrían hacer que una regla VISTA deje de funcionar según lo esperado. Adobe recomienda revisar las reglas VISTA regularmente para determinar si son necesarias actualizaciones o eliminaciones.

## Crear una regla VISTA {#create}

Debe trabajar con Adobe Professional Services para crear una regla VISTA. Póngase en contacto con el equipo de cuenta de Adobe si desea crear una regla VISTA.

## Ver las reglas VISTA existentes {#see}

Adobe no dispone de una IU para ver las reglas VISTA existentes. Póngase en contacto con el equipo de cuenta de Adobe o con el Servicio de atención al cliente con el grupo de informes deseado para recuperar una lista de reglas VISTA existentes.
