---
description: Las reglas de bots permiten eliminar de un grupo de informes el tráfico generado por arañas de web y bots conocidos. La eliminación del tráfico de bots puede proporcionar una medida más precisa de la actividad del usuario en el sitio web.
title: Comprensión y configuración de reglas de bots
feature: Bot Removal
role: Admin
exl-id: 1c0009f6-2746-4ef1-8dcb-e2693617e91e
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '1668'
ht-degree: 68%

---

# Comprensión y configuración de reglas de bots

Las reglas de bots le permiten eliminar el tráfico del grupo de informes generado por arañas web y bots conocidos. La eliminación del tráfico de bots puede proporcionar una medida más precisa de la actividad del usuario en el sitio web.

Una vez definidas las reglas del bot, todo el tráfico entrante se compara con las reglas definidas. El tráfico que coincida con cualquiera de estas reglas no se recopila en el grupo de informes y no se incluye en las métricas de tráfico.

Por lo general, al eliminar el tráfico de bots se reduce el volumen de las métricas de conversión y tráfico. Muchos clientes de descubren que la eliminación del tráfico de bots aumenta las tasas de conversión y aumenta otras métricas de uso.

Los datos del tráfico de bots se almacenan en un repositorio independiente para mostrarlos en los informes Bots y Páginas de bots.

>[!NOTE]
>
>El Edge Network de Adobe Experience Platform proporciona un [servicio de detección de bots](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=es) que identifica las visitas identificadas como de bots. El proceso de detección de bots que se utiliza en Adobe Analytics es independiente y no hace referencia a la puntuación de bots incluida en los datos que llegan a través del Edge Network. Sin embargo, los dos sistemas utilizan la misma lista de bots de la IAB.

## Actualizar o cargar reglas de bots

>[!IMPORTANT]
>
>Antes de eliminar el tráfico de bots, es necesario ponerse en contacto con los interesados para asegurarse de que realicen los ajustes necesarios en los indicadores de rendimiento clave con relación a este cambio. Si es posible, recomendamos eliminar primero el tráfico de bots de un grupo de informes pequeño para así realizar una estimación del impacto potencial.


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configurar reglas de bots](https://video.tv.adobe.com/v/3418507/?quality=12&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


Para actualizar o cargar reglas de bots:

1. Vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]**.

1. Seleccione el grupo de informes donde desee actualizar las reglas de bots y, a continuación, seleccione **[!UICONTROL Editar configuración]** > **[!UICONTROL General]** > **[!UICONTROL Reglas de bots]**.

1. Utilice cualquiera de las siguientes opciones para actualizar o cargar reglas de bots para el grupo de informes:

   * Seleccione [!UICONTROL **Activar las reglas de filtrado de bots de la IAB**] para eliminar bots de la lista internacional de arañas web y bots de la IAB (International Advertising Bureau&#39;s) a fin de eliminar el tráfico de bots.

     Le recomendamos que seleccione esta opción como mínimo.

     Para obtener más información, consulte la sección siguiente, [Reglas de bots estándar IAB](#standard-iab-bot-rules).

   * Seleccione [!UICONTROL **Agregar regla**] para definir y agregar reglas de bots personalizadas basadas en agentes de usuario, direcciones IP o intervalos de IP.

     Para obtener más información, consulte la sección siguiente, [Reglas de bots personalizadas](#custom-bot-rules).

   * Junto al área [!UICONTROL **Seleccionar archivo de bots CSV para importar**], seleccione [!UICONTROL **Elegir archivo**] y, a continuación, seleccione el archivo CSV que define las reglas de bots.

     Para obtener más información, consulte la sección siguiente, [Cargar reglas de bots](#upload-bot-rules).

1. Seleccione [!UICONTROL **Guardar**].

## Reglas de bots estándar IAB

Las reglas de bots estándar IAB se pueden activar marcando la casilla [!UICONTROL Activar reglas de filtrado de bots IAB]. Esta selección eliminará los bots de la Lista internacional de arañas web y bots de la IAB (International Advertising Bureau&#39;s) para eliminar el tráfico de bots. Adobe actualiza esta lista de la IAB mensualmente.

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-iab-checkbox.png)

Adobe no puede proporcionar la lista detallada de bots de la IAB a los clientes, pero se puede usar el informe de bots para ver una lista de los bots que han accedido a un sitio. Para enviar un bot a la lista de la IAB, visite [IAB](https://www.iab.com).

Para obtener información sobre cómo habilitar reglas de bots estándar IAB en un grupo de informes, consulte [Actualizar o cargar reglas de bots](#update-or-upload-bot-rules).

## Reglas de bots personalizadas

>[!NOTE]
>
>: La interfaz de usuario permite definir 500 reglas manualmente. Una vez alcanzado este límite, es necesario gestionar las reglas de forma masiva mediante las opciones Importar archivo y Exportar reglas Bot.

Las reglas de bots personalizadas le permiten filtrar el tráfico en función de las condiciones que defina. Para comenzar el proceso de habilitar reglas de bots personalizadas en un grupo de informes, consulte [Actualizar o cargar reglas de bots](#update-or-upload-bot-rules).

Las reglas de bots personalizadas se definen usando los tipos de condición siguientes:

* Agente de usuario
* Dirección IP
* Rango IP

Para una sola regla se pueden definir varias condiciones. Las diversas condiciones se comparan usando “or”. Por ejemplo, si proporciona un valor para agente de usuario y dirección IP, el tráfico se considera tráfico de bots si se cumple cualquiera de las condiciones.

### Agente de usuario

Una condición de agente de usuario comprueba el valor de agente de usuario para ver si **[!UICONTROL comienza con]** o **[!UICONTROL contiene]** la cadena especificada. Si se selecciona **[!UICONTROL contiene]**, la subcadena tendrá una coincidencia si se produce en cualquier parte del agente de usuario.

Se pueden incluir valores opcionales en la lista **[!UICONTROL no contiene]** para definir valores que el agente de usuario no debe contener para que la coincidencia tenga éxito. Se pueden especificar varios valores incluyendo un valor por línea. Si el agente de usuario cumple con los criterios especificados en la cadena de coincidencia, pero además contiene una cadena en la lista “no contiene”, no se considerará una coincidencia.

El campo **[!UICONTROL contiene]** está limitado a 100 caracteres. La lista no contiene está limitada a 255 caracteres menos un carácter separador para cada línea nueva. (Esto es igual al número de cadenas - 1. Si especifica 4 *no contiene* cadenas, se requieren 3 caracteres separadores.) Todas las coincidencias de cadena no distinguen entre mayúsculas y minúsculas.

### Dirección IP (incluyendo coincidencias de comodín)

Hace coincidir una dirección IP o varias direcciones en el mismo bloque usando comodines (&#42;). Proporcione los valores numéricos de la dirección IP que desee hacer coincidir. Sustituya &#42; en los valores que desee hacer coincidir usando un comodín. La lista siguiente contiene ejemplos de cadena de coincidencia de dirección IP:

```
10.10.10.1
10.10.10.*
```

### Rango de direcciones IP

Proporcione el rango inicial y final de las direcciones IP para buscar coincidencias. Sustituya &#42; en los valores que desee hacer coincidir usando un comodín.

### Definir una regla de bots personalizada

1. Vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Administración]**, seleccione uno o varios grupos de informes y haga clic en **[!UICONTROL General]** > **[!UICONTROL Reglas Bot]**.
1. Haga clic en **[!UICONTROL Agregar regla]** y defina una o varias condiciones de coincidencia.
1. Haga clic en **[!UICONTROL Guardar]**. El cambio puede tardar 30 minutos en implementarse.

## Cargar reglas de bots

Para importar reglas de bots de forma masiva, puede cargarse un archivo CSV que defina las reglas.

1. Para iniciar el proceso de cargar reglas de bots en un grupo de informes, consulte [Actualizar o cargar reglas de bots](#update-or-upload-bot-rules).

1. Cree un archivo CSV con las columnas siguientes, en la fila 1 de la hoja de cálculo y en el orden presentado:

   | Columna 1, Fila 1 | Columna 2, Fila 1 | Columna 3, Fila 1 | Columna 4, Fila 1 | Columna 5, Fila 1 | Columna 6, Fila 1 |
   |--- |--- |---|---|---|---|
   | Nombre de Bot | IP Begin | IP End | Regla<br>(contiene o empieza con)</br> | Inclusión de agente de usuario | Exclusión del agente de usuario <br>(límite de 255 caracteres)</br> |

   Puede definir tres tipos de reglas de bots:

   * Agente de usuario contiene o comienza con
   * Coincidencia de dirección IP única o comodín
   * Coincidencia de rango de IP

   Cada fila del archivo de importación puede contener una sola de las siguientes definiciones de bots:

   >[!NOTE]
   >
   >   Para buscar coincidencias de un bot utilizando una combinación de reglas unidas con OR (por ejemplo, agente de usuario o dirección IP), proporcione un nombre idéntico para todas las reglas que desee combinar en el campo de nombre de bot. No se admiten coincidencias AND.


   * **Agente de usuario contiene o comienza con**: proporcione una cadena del agente de usuario único en la columna Agent Include. Especifique el tipo de coincidencia que desea estableciendo *contiene* o *comienza con* en el campo Agent Match Rule. En la columna Agent Exclude se puede incluir un valor opcional que defina una o varias cadenas delimitadas por paréntesis (`|`) que el agente no contenga. Las coincidencias de cadena distinguen entre mayúsculas y minúsculas. Las columnas IP Start e IP End deben estar vacías.

   * **Coincidencia de dirección IP única o comodín**: Para hacer coincidir una dirección IP única (`10.10.10.1`) o una dirección IP comodín (`10.10.*.*`), introduzca el mismo valor en las columnas IP Start e IP End. Match Rule, Agent Include y Agent Exclude deben estar vacías.

   * **Coincidencia de rango IP**: defina un intervalo de direcciones IP usando las columnas IP Start e IP End. Se pueden usar comodines para buscar coincidencias de rangos IP, por ejemplo de `10.10.10.*` a `10.10.20.*`. Match Rule, Agent Include y Agent Exclude deben estar vacías.

1. En la página Reglas de bots del Administrador del grupo de informes, junto al área [!UICONTROL **Seleccionar archivo CSV para importar**], seleccione [!UICONTROL **Elegir archivo**] y, a continuación, seleccione el archivo CSV que define las reglas de bots que desea importar.

1. (Opcional) Seleccione la casilla de verificación **[!UICONTROL Sobrescribir reglas existentes]** para eliminar todas las reglas existentes y reemplazarlas con las reglas definidas en el archivo de carga.

1. Seleccione [!UICONTROL **Importar archivo**].

1. En el área [!UICONTROL **Conjuntos de reglas**], revise las reglas que se importaron.

1. Seleccione [!UICONTROL **Guardar**].

## Exportar reglas de bots

Para exportar todas las reglas definidas en la interfaz de usuario en formato CSV:

1. Vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]**.

1. Seleccione el grupo de informes que contiene las reglas de bots que desea exportar y, a continuación, seleccione **[!UICONTROL Editar configuración]** > **[!UICONTROL General]** > **[!UICONTROL Reglas de bots]**.

1. Seleccione **[!UICONTROL Exportar reglas de bots]** y, a continuación, guarde el archivo CSV en el sistema de archivos.

## Efecto de las reglas de bots en la recopilación de datos {#section_F01A3130E7A04A9993371CF26F6586F2}

Las reglas de bots se aplican a todos los datos de análisis. Los datos que quitan las reglas de bots solo se pueden ver en los informes Bots y Páginas de bots.

Las reglas de VISTA se aplican después de las reglas de bots. Consulte [Reglas de procesamiento](/help/technotes/processing-order.md) en la guía de usuario sobre notas técnicas.

**Procesamiento de visitas intensivas:** si en una visita se registran más de 100 entradas, el informe determinará si el tiempo en segundos asignado a la visita es inferior o igual al número de entradas que contiene. En este caso, debido al costo de las visitas intensivas que requieren un procesamiento prolongado, el informe comienza de nuevo con una nueva lista. Por lo general, las visitas intensivas se deben a ataques de bots y no se consideran eventos de exploración de visitantes corrientes.

>[!NOTE]
>
>Las visitas marcadas como *`bots`* se facturan como [llamadas al servidor.](/help/admin/admin/c-server-call-usage/overage-overview.md)

## Influencia de la confusión de IP en el filtrado para bots {#section_92E60B95BE8940D983F28C79E0CD6B12}

La lista de bots de la IAB se basa exclusivamente en agente usuario, por lo que el filtrado en función de esa lista no afecta a los ajustes de confusión de IP. Para el filtrado de bots que no son IAB (reglas personalizadas), IP puede formar parte de los criterios de filtrado. Si filtra bots con IP, el filtrado de bots ocurre después de que el último octeto ha sido eliminado si ese ajuste está habilitado, pero antes de las otras opciones de confusión de IP, como la eliminación de la IP completa o la sustitución con algún ID único.

Si la confusión de la IP está habilitada, la exclusión de la IP se produce antes de que la dirección IP se confunda, por lo que los clientes no necesitan cambiar nada cuando habilitan la confusión de la IP.

Si se elimina el último octeto, será antes del filtrado de la IP. Como tal, el último octeto se sustituye por un 0 y las reglas de exclusión de la IP se deben actualizar para coincidir con las direcciones de IP que tengan un cero al final. Un coincidente &#42; debe corresponder a un 0.
