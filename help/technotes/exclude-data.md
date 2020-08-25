---
title: Excluir datos en Adobe Analytics
description: Obtenga información sobre varios métodos para excluir datos antes y después de la recopilación de datos.
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---


# Excluir datos en Adobe Analytics

La exclusión de datos se utiliza generalmente para evitar que los esfuerzos de prueba de la organización rellenen los datos de producción o para evitar que los datos no deseados inflen falsamente los informes. Utilice cualquiera de los siguientes métodos para excluir datos de Adobe Analytics según el caso de uso.

## Excluir datos posteriores a la recopilación de datos

Los siguientes métodos son formas de excluir datos en Analytics sistema de informes después de que los servidores de recopilación de datos de Adobe reciban solicitudes de imagen. Los datos excluidos mediante estos métodos siguen contando para las llamadas al servidor facturables.

* **Excluir por dirección IP**: Adobe Analytics proporciona funcionalidad básica para excluir datos de direcciones IP o intervalos en un grupo de informes. Consulte [Excluir por dirección IP](/help/admin/admin/exclude-ip.md) en la guía del usuario del administrador.
* **Reglas** de bots: Las reglas de bots toman el tráfico de las cadenas conocidas de agente de usuario de bots y las excluyen de los informes de Analytics. Los datos excluidos mediante reglas de bots se colocan en el informe Bots. Se pueden crear reglas de bots personalizadas para excluir datos adicionales. See [Bot Rules](/help/admin/admin/bot-removal/bot-rules.md) in the Admin user guide.
* **Reglas** de VISTA: Según las necesidades de su organización, las visitas que coincidan con sus necesidades se envían a otro grupo de informes dedicado a recibir datos excluidos. Las reglas de VISTA se utilizan comúnmente con las direcciones IP, pero no se limitan a ellas. Puede utilizar cualquier dimensión para incluir o excluir datos en los grupos de informes. Las reglas de VISTA están sujetas a costes adicionales; póngase en contacto con el administrador de cuentas de su organización para obtener más información.
* **Cookies** de exclusión: Todos los visitantes del sitio pueden exclusión voluntariamente el rastreo en Adobe Analytics visitando una página específica del servidor de seguimiento. Consulte [Implementación de vínculos](/help/implement/js/opt-out.md) de exclusión en la guía de usuario Implementación.

>[!TIP]
>
>Las reglas de procesamiento no pueden excluir datos ni enviarlos a otro grupo de informes. Sin embargo, determinadas variables se pueden establecer condicionalmente y se puede utilizar un segmento para excluir esos datos del sistema de informes.

## Excluir la recopilación de datos previos a los datos

Si desea evitar que determinadas visitas lleguen a los servidores de recopilación de datos de Analytics, utilice la [`abort`](/help/implement/vars/config-vars/abort.md) variable. Este indicador evita que se envíe la solicitud de imagen. Las llamadas al servidor facturables no se incrementan para solicitudes de imagen anuladas, ya que no llegan a los servidores de recopilación de datos de Adobe.
