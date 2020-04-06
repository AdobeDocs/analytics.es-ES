---
description: Las reglas de bots permiten eliminar del grupo de informes el tráfico que generan las arañas de Web y los bots conocidos. La eliminación del tráfico de bots puede proporcionar una medición más precisa de la actividad del usuario en el sitio web.
subtopic: Bot rules
title: Resumen sobre reglas de Bot
topic: Admin tools
uuid: 3cb9e29d-1c37-43de-b7ac-34441093a60e
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Resumen sobre reglas de Bot

Las reglas de bots le permiten eliminar el tráfico del grupo de informes generado por arañas web y bots conocidos. La eliminación del tráfico de bots puede proporcionar una medición más precisa de la actividad del usuario en el sitio web.

Una vez definidas las reglas de bots, todo el tráfico entrante se compara con las reglas definidas. El tráfico que coincide con cualquiera de estas reglas no se recopila en el grupo de informes y no se incluye en las métricas de tráfico.

Para actualizar o cargar reglas de bots, vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**. Seleccione el grupo de informes correcto y, a continuación, vaya a **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Bot Rules]**.

La eliminación del tráfico de bots generalmente reduce el volumen de las métricas de tráfico y conversión. Muchos clientes consideran que la eliminación del tráfico de bots produce un aumento de tasas de conversión y de otras métricas de uso. Antes de eliminar el tráfico de bots, comuníquese con las partes interesadas para asegurarse de que pueden realizar los ajustes necesarios en los indicadores de rendimiento clave como resultado de este cambio. Si es posible, recomendamos eliminar primero el tráfico de bots de un grupo de informes pequeño para así realizar una estimación del impacto potencial.

Los datos del tráfico de bots se almacenan en un repositorio independiente para mostrarlos en los informes Bots y Páginas de bots. Existen dos opciones para activar el filtrado de bots:

| Tipo de regla | Descripción |
|--- |--- |
| Reglas de bots estándar IAB | Selecting [!UICONTROL Enable IAB Bot Filtering Rules] uses the [IAB&#39;s](https://www.iab.com) (International Advertising Bureau&#39;s) International Spiders &amp; Bots List to remove bot traffic. La mayoría de los clientes selecciona esta opción como mínimo. |
| Reglas de bots personalizadas | Puede definir y agregar reglas de bots personalizadas basadas en agentes de usuario, direcciones IP o intervalos de IP. |

## Reglas de bots estándar IAB

Las reglas estándar de bots IAB se pueden activar marcando la casilla de verificación [!UICONTROL Enable IAB Bot Filtering Rules] . Esta selección eliminará los bots de la Lista internacional de arañas web y bots de la IAB (International Advertising Bureau&#39;s) para eliminar el tráfico de bots. La IAB actualiza esta lista mensualmente.

![](assets/bot-iab-checkbox.png)

Adobe no puede proporcionar la lista detallada de bots de la IAB a los clientes, pero se puede usar el informe de bots para ver una lista de los bots que han accedido a un sitio. Para enviar un bot a la lista de la IAB, visite [IAB](https://www.iab.com).

## Reglas de bots personalizadas

>[!Note]: La interfaz de usuario permite definir 500 reglas manualmente. Una vez alcanzado este límite, es necesario gestionar las reglas de forma masiva mediante las opciones Importar archivo y Exportar reglas Bot.

Las reglas de bots personalizadas le permiten filtrar las condiciones basadas en el tráfico que defina.

Las reglas de bots personalizadas se definen con los siguientes tipos de condiciones:

* Agente de usuario
* Dirección IP
* Rango IP

Se pueden definir varias condiciones para una sola regla. Las condiciones múltiples se comparan usando &quot;o&quot;. Por ejemplo: si proporciona un valor para el agente de usuario y la dirección IP, el tráfico se considera tráfico bot si se cumple cualquiera de las condiciones.

### Agente de usuario

A User Agent condition checks the user agent value to see if it **[!UICONTROL starts with]** or **[!UICONTROL contains]** the specified string. If **[!UICONTROL contains]** is selected, the substring is matched if it occurs anywhere in the user agent.

Optional values can be included in the **[!UICONTROL does not contain]** list to define values that the user agent must not contain for a successful match. Se pueden especificar varios valores incluyendo un valor por línea. Si el agente de usuario cumple los criterios especificados en la cadena de coincidencia, pero también contiene una cadena en la lista no contiene, no se considera una coincidencia.

The **[!UICONTROL contains]** field is limited to 100 characters. La lista no contiene está limitada a 255 caracteres menos un carácter separador para cada nueva línea. (Es igual al número de cadenas - 1. Si especifica 4 *no contiene* cadenas, se requieren 3 caracteres separadores). Todas las coincidencias de cadenas distinguen entre mayúsculas y minúsculas.

### Dirección IP (incluyendo coincidencias de comodín)

Coincide con una dirección IP o varias direcciones en el mismo bloque utilizando caracteres comodín (*). Proporcione los valores numéricos de la dirección IP que desea que coincidan. Sustituya * por cualquier valor que desee hacer coincidir utilizando un comodín. La siguiente lista contiene ejemplos de cadena de coincidencia de direcciones IP:

```
10.10.10.1
10.10.10.*
```

### Rango de direcciones IP

Proporcione los rangos de inicio y fin de las direcciones IP para que coincidan. Sustituya * por cualquier valor que desee hacer coincidir utilizando un comodín.

### Definir una regla de bots personalizada

1. Vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Admin]**, seleccione uno o varios grupos de informes y haga clic en **[!UICONTROL General]** > **[!UICONTROL Bot Rules]**.
1. Click **[!UICONTROL Add Rule]** and define one or more match conditions.
1. Haga clic en **[!UICONTROL Save]**. El cambio puede tardar 30 minutos en implementarse.

## Cargar reglas de bots

Para importar reglas de bots de forma masiva, puede cargar un archivo CSV que defina las reglas.

Cree un archivo CSV con las columnas siguientes en el orden presentado:

| Columna 1 | Columna 2 | Columna 3 | Columna 4 | Columna 5 |
|--- |--- |---|---|---|
| Nombre de Bot | IP Start | IP End | Regla Agent Match <br>(contiene o empeza con)</br> | Agent Exclude<br>(límite de 255 caracteres)</br> |

Puede definir tres tipos de reglas de bots:

* El agente de usuario contiene o inicios con
* Coincidencia de comodín o dirección IP única
* Coincidencia de rango IP

Cada fila del archivo de importación puede contener solo una de las siguientes definiciones de bots:

* **Agente de usuario contiene o inicios con**: Proporcione una sola cadena de agente de usuario para que coincida en la columna Agent Include. Especifique el tipo de coincidencia que desea realizar colocando *contiene* o *inicios con* en el campo Agent Match Rule. En la columna Agent Exclude se puede incluir un valor opcional que defina una o varias cadenas delimitadas por paréntesis (`|`) que el agente no contenga. Las coincidencias de cadenas no distinguen entre mayúsculas y minúsculas. Las columnas Inicio IP y Fin IP deben estar vacías.

* **Coincidencia de dirección IP única o comodín**: Para hacer coincidir una dirección IP única (`10.10.10.1`) o una dirección IP comodín (`10.10.*.*`), introduzca el mismo valor en las columnas IP Start e IP End. Match Rule, Agent Include y Agent Exclude deben estar vacías.

* **Coincidencia** de rango IP: Defina un rango de direcciones IP usando las columnas Inicio IP y Fin IP. Se pueden usar comodines para buscar coincidencias de rangos IP, por ejemplo de `10.10.10.*` a `10.10.20.*`. Match Rule, Agent Include y Agent Exclude deben estar vacías.

### Varias reglas combinadas con OR

Para hacer coincidir un bot utilizando una combinación de reglas unidas con un O (por ejemplo, agente de usuario o dirección IP), proporcione un nombre idéntico para todas las reglas que desee combinar en el campo de nombre del bot. No se admiten coincidencias AND.

### Sobrescribir todas las reglas con un archivo de carga

Select the **[!UICONTROL Overwrite existing rules]** checkbox to delete all existing rules and replace them with the rules defined in the upload file.

### Exportar reglas

The **[!UICONTROL Export Uploaded Bot File]** button exports all rules defined in the UI in a CSV format.


## Efecto de las reglas de bots en la recopilación de datos {#section_F01A3130E7A04A9993371CF26F6586F2}

Las reglas de bots se aplican a todos los datos de análisis. Los datos que quitan las reglas de bots solo se pueden ver en los informes Bots y Páginas de bots.

Las reglas de VISTA se aplican después de las reglas de bots (consulte [Orden de procesamiento).](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md)

**Procesamiento de visitas de alta visita:** Si en una visita se producen más de 100 visitas, el sistema de informes determina si el tiempo de la visita en segundos es menor o igual al número de visitas en la visita. En esta situación, debido al costo de procesar visitas largas e intensas, el sistema de informes inicio con una nueva visita. Las visitas de mayor cantidad de visitas suelen estar provocadas por ataques de bots y no se consideran exploraciones de visitante normales.

>[!NOTE] Las visitas marcadas como *`bots`* se facturan como [llamadas al servidor.](/help/admin/c-server-call-usage/overage-overview.md)

## Influencia de la confusión de IP en el filtrado para bots {#section_92E60B95BE8940D983F28C79E0CD6B12}

La lista de bots de IAB se basa únicamente en el agente de usuario, por lo que el filtrado basado en esa lista no se ve afectado por la configuración de confusión de IP. Para el filtrado de bots que no son IAB (reglas personalizadas), la IP puede formar parte de los criterios de filtrado. Si filtra bots mediante IP, el filtrado de bots se produce después de que el último octeto se haya eliminado si esa configuración está habilitada, pero antes de las otras opciones de confusión de IP, como eliminar la IP completa o reemplazarla con algún ID único.

Si la confusión de IP está habilitada, la exclusión de IP se produce antes de que la dirección IP se confunda, por lo que los clientes no necesitan cambiar nada cuando habilitan la confusión de IP.

Si se elimina el último octeto, esto se realiza antes del filtrado de IP. Como tal, el último octeto se reemplaza por un 0 y las reglas de exclusión de IP deben actualizarse para que coincidan con las direcciones IP con un cero al final. Un * coincidente debe corresponder a un 0.
