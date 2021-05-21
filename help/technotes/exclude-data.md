---
title: Excluir datos en Adobe Analytics
description: Conozca varios métodos sobre cómo excluir datos antes y después de la recopilación de datos.
exl-id: dee5bf3b-8bb3-48eb-908d-b4a981f17bfb
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '352'
ht-degree: 100%

---

# Excluir datos en Adobe Analytics

La exclusión de datos se utiliza habitualmente para impedir que los esfuerzos de prueba de su organización rellenen los datos de producción o para evitar que los datos no deseados inflen indebidamente los informes. Utilice cualquiera de los siguientes métodos para excluir datos de Adobe Analytics según el caso de uso.

## Excluir datos después de la recolección de datos

Los siguientes métodos son formas de excluir datos en la creación de informes de Analytics después de que los servidores de recopilación de datos de Adobe reciban solicitudes de imagen. Los datos excluidos mediante estos métodos siguen contando en las llamadas facturables al servidor.

* **Excluir por dirección IP**: Adobe Analytics proporciona funcionalidad básica para excluir datos de direcciones IP o rangos en un grupo de informes. Consulte [Excluir por dirección IP](/help/admin/admin/exclude-ip.md) en la guía del usuario de administración.
* **Reglas de bots**: Las reglas de bots toman el tráfico de cadenas conocidas del agente de usuario de bots y las excluyen de los informes de Analytics. Los datos excluidos mediante reglas de bots se colocan en el informe Bots. Se pueden crear reglas de bots personalizadas para excluir datos adicionales. Consulte [Reglas de bots](/help/admin/admin/bot-removal/bot-rules.md) en la guía del usuario de administración.
* **Reglas de VISTA**: Según las necesidades de su organización, las visitas que coincidan con sus necesidades se envían a otro grupo de informes dedicado a la recepción de datos excluidos. Las reglas de VISTA generalmente se utilizan contra direcciones IP, pero no se limitan a ellas. Puede utilizar cualquier dimensión para incluir o excluir datos en grupos de informes. Las reglas de VISTA están sujetas a costes adicionales; póngase en contacto con el administrador de cuentas de su organización para obtener más información.
* **Cookies de exclusión**: Todos los visitantes del sitio pueden renunciar voluntariamente al seguimiento en Adobe Analytics si visitan una página específica del servidor de seguimiento. Consulte [Implementar vínculos de exclusión](/help/implement/js/opt-out.md) en la guía del usuario de implementación.

>[!TIP]
>
>Las reglas de procesamiento no pueden excluir datos ni enviar datos a otro grupo de informes. Sin embargo, se pueden configurar ciertas variables de forma condicional y se puede utilizar un segmento para excluir esos datos de la creación de informes.

## Excluir datos antes de la recopilación de datos

Si desea evitar que determinadas visitas lleguen a los servidores de recopilación de datos de Analytics, utilice la variable [`abort`](/help/implement/vars/config-vars/abort.md). Este indicador evita que se envíe la solicitud de imagen. Las llamadas facturables al servidor no se incrementan en el caso de solicitudes de imagen anuladas, ya que no llegan a los servidores de recopilación de datos de Adobe.
