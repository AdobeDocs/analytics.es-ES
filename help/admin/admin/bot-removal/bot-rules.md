---
description: Las reglas de bots permiten eliminar de un grupo de informes el tráfico generado por arañas de web y bots conocidos. Al eliminar el tráfico de bots, la medición de la actividad de los usuarios en el sitio web es más exacta.
seo-description: Las reglas de bots permiten eliminar de un grupo de informes el tráfico generado por arañas de web y bots conocidos. Al eliminar el tráfico de bots, la medición de la actividad de los usuarios en el sitio web es más exacta.
seo-title: Reglas de bots
solution: Analytics
subtopic: Reglas de bots
title: Reglas de bots
topic: Herramientas de administración
uuid: 3 cb 9 e 29 d -1 c 37-43 de-b 7 ac -34441093 a 60 e
translation-type: tm+mt
source-git-commit: 4a627e268994d0152a19fb44e9bc06ea7ebc64c6

---


# Reglas de bots

Las reglas de bots permiten eliminar el tráfico del grupo de informes generado por arañas y bots conocidos. Al eliminar el tráfico de bots, la medición de la actividad de los usuarios en el sitio web es más exacta.

Una vez definidas las reglas de bots, todo el tráfico entrante se compara con las reglas definidas. El tráfico que coincida con alguna de estas reglas no se recogerá en el grupo de informes ni se incluirá en las métricas de tráfico.

To update or upload bot rules, navigate to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**. Select the correct Report Suite, and then go to **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Bot Rules]**.

Por lo general, al eliminar el tráfico de bots se reduce el volumen de las métricas de conversión y tráfico. Muchos clientes consideran que eliminar el tráfico de bots provoca tasas de conversión superiores y aumenta otras métricas de uso. Antes de eliminar el tráfico de bots, es necesario ponerse en contacto con los interesados para asegurarse de que realicen los ajustes necesarios en los indicadores de rendimiento clave con relación a este cambio. Si es posible, se recomienda eliminar en primer lugar el tráfico de bots de un grupo de informes pequeño para realizar una estimación de los posibles efectos.

>[!NOTE] Se recomienda definir no más de 500 reglas de bots por grupo de informes. La interfaz de usuario permite definir 500 reglas manualmente. Una vez alcanzado este límite, las reglas deben gestionarse de forma masiva mediante las opciones de [Importar archivo](../../../admin/admin/bot-removal/t-upload-bot-rules.md#task_95868D8564564E6A996163335C119806) y Exportar reglas de bots.

Los datos del tráfico de bots se almacenan en un repositorio independiente para mostrarlos en los informes [!UICONTROL Bots] y [!UICONTROL Páginas de bots].

| Tipo de regla | Descripción |
|--- |--- |
| IAB | Selecting [!UICONTROL Include IAB] uses the IAB's (International Advertising Bureau's) International Spiders &amp; Bots List to remove bot traffic. La IAB actualiza esta lista mensualmente. <br>Para enviar un bot a la lista de IAB, visite [IAB](https://www.iab.net/sites/spiders/form.php). <br>Adobe no puede proporcionar la lista detallada de bots de la IAB a los clientes, pero se puede usar el informe de bots para ver una lista de los bots que han accedido a un sitio. |
| Reglas de bots personalizadas | Consulte [Crear una regla de bots personalizada](../../../admin/admin/bot-removal/t-create-bot-rules.md). |

## Efecto de las reglas de bots en la recopilación de datos {#section_F01A3130E7A04A9993371CF26F6586F2}

Las reglas de bots se aplican a todos los datos de análisis. Los datos que quitan las reglas de bots solo se pueden ver en los informes Bots y Páginas de bots.

VISTA rules are applied after Bot Rules (see [Processing Order](../../../admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md#concept_8A6BBEA7F50C40C8A8D8755D4F579B1E)).

**Procesamiento de visitas intensivas:** si en una visita se registran más de 100 entradas, el informe determinará si el tiempo en segundos asignado a la visita es inferior o igual al número de entradas que contiene. En este caso, debido al costo de las visitas intensivas que requieren un procesamiento prolongado, el informe comienza de nuevo con una nueva lista. Por lo general, las visitas intensivas se deben a ataques de bots y no se consideran eventos de exploración de visitantes corrientes.

>[!NOTE]
>
>Las visitas marcadas como *`bots`* se facturan como [llamadas al servidor](https://docs.adobe.com/content/help/en/analytics/admin/server-call-usage/overage-overview.html).

## Influencia de la confusión de IP en el filtrado para bots {#section_92E60B95BE8940D983F28C79E0CD6B12}

La lista de bots de la IAB se basa exclusivamente en agente usuario, por lo que el filtrado en función de esa lista no afecta a los ajustes de confusión de IP. Para el filtrado de bots que no son IAB (reglas personalizadas), IP puede formar parte de los criterios de filtrado. Si filtra bots con IP, el filtrado de bots ocurre después de que el último octeto ha sido eliminado si ese ajuste está habilitado, pero antes de las otras opciones de confusión de IP, como la eliminación de la IP completa o la sustitución con algún ID único.

Si la confusión de la IP está habilitada, la exclusión de la IP se produce antes de que la dirección IP se confunda, por lo que los clientes no necesitan cambiar nada cuando habilitan la confusión de la IP.

Si se elimina el último octeto, será antes del filtrado de la IP. Como tal, el último octeto se sustituye por un 0 y las reglas de exclusión de la IP se deben actualizar para coincidir con las direcciones de IP que tengan un cero al final. Un * coincidente debe corresponder a un 0.
