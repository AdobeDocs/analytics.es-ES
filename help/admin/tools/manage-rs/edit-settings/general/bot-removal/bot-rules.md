---
description: Las reglas de bots permiten eliminar de un grupo de informes el tráfico generado por arañas de web y bots conocidos. La eliminación del tráfico de bots puede proporcionar una medida más precisa de la actividad del usuario en el sitio web.
title: Comprensión y configuración de reglas de bots
feature: Bot Removal
role: Admin
exl-id: 1c0009f6-2746-4ef1-8dcb-e2693617e91e
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '1669'
ht-degree: 37%

---

# Comprensión y configuración de reglas de bots

Las reglas de bots le permiten eliminar el tráfico del grupo de informes generado por arañas web y bots conocidos. La eliminación del tráfico de bots puede proporcionar una medida más precisa de la actividad del usuario en el sitio web.

Una vez definidas las reglas del bot, todo el tráfico entrante se compara con las reglas definidas. El tráfico que coincida con cualquiera de estas reglas no se recopila en el grupo de informes y no se incluye en las métricas de tráfico.

La eliminación del tráfico de bots suele reducir el volumen de tráfico y las métricas de conversión. Muchos clientes de descubren que la eliminación del tráfico de bots aumenta las tasas de conversión y aumenta otras métricas de uso.

Los datos del tráfico de bots se almacenan en un repositorio independiente para mostrarlos en los informes Bots y Páginas de bots.

>[!NOTE]
>
>Adobe Experience Platform Edge Network proporciona un [servicio de detección de bots](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=es) que identifica las visitas identificadas como de bots. El proceso de detección de bots que se utiliza en Adobe Analytics es independiente y no hace referencia a la puntuación de bots incluida en los datos que llegan a través de Edge Network. Sin embargo, los dos sistemas utilizan la misma lista de bots de la IAB.

## Actualizar o cargar reglas de bots

>[!IMPORTANT]
>
>Antes de eliminar el tráfico de bots, póngase en contacto con las partes interesadas para asegurarse de que pueden realizar los ajustes necesarios en los indicadores de rendimiento clave como resultado de este cambio. Si es posible, recomendamos eliminar primero el tráfico de bots de un grupo de informes pequeño para así realizar una estimación del impacto potencial.


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configurar reglas de bots](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/administration/manage-report-suites/configure-bot-rules-in-analytics){target="_blank"} para ver un vídeo de demostración.

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

Las reglas de bots estándar IAB se pueden habilitar marcando la casilla [!UICONTROL Habilitar reglas de filtrado de bots IAB]. Esta selección eliminará los bots de la Lista internacional de arañas web y bots de la IAB (International Advertising Bureau&#39;s) para eliminar el tráfico de bots. Adobe actualiza esta lista de la IAB mensualmente.

![](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/assets/bot-iab-checkbox.png)

Adobe no puede proporcionar la lista detallada de bots de la IAB a los clientes, pero se puede usar el informe de bots para ver una lista de los bots que han accedido a un sitio. Para enviar un bot a la lista de la IAB, visite [IAB](https://www.iab.com).

Para obtener información sobre cómo habilitar reglas de bots estándar IAB en un grupo de informes, consulte [Actualizar o cargar reglas de bots](#update-or-upload-bot-rules).

## Reglas de bots personalizadas

>[!NOTE]
>
>: La interfaz de usuario permite definir 500 reglas manualmente. Una vez alcanzado este límite, es necesario gestionar las reglas de forma masiva mediante las opciones Importar archivo y Exportar reglas Bot.

Las reglas de bots personalizadas le permiten filtrar el tráfico en función de las condiciones que defina. Para comenzar el proceso de habilitar reglas de bots personalizadas en un grupo de informes, consulte [Actualizar o cargar reglas de bots](#update-or-upload-bot-rules).

Las reglas de bots personalizadas se definen con los siguientes tipos de condición:

* Agente de usuario
* Dirección IP
* Intervalo IP

Se pueden definir varias condiciones para una sola regla. Se hacen coincidir varias condiciones utilizando &quot;or&quot;. Por ejemplo, si proporciona un valor para Agente de usuario y Dirección IP, el tráfico se considera tráfico de bots si se cumple cualquiera de las condiciones.

### Agente de usuario

Una condición de agente de usuario comprueba el valor de agente de usuario para ver si **[!UICONTROL comienza con]** o **[!UICONTROL contiene]** la cadena especificada. Si se selecciona **[!UICONTROL contiene]**, la subcadena tendrá una coincidencia si se produce en cualquier parte del agente de usuario.

Se pueden incluir valores opcionales en la lista **[!UICONTROL no contiene]** para definir valores que el agente de usuario no debe contener para que la coincidencia tenga éxito. Se pueden especificar varios valores incluyendo un valor por línea. Si el agente de usuario cumple los criterios especificados en la cadena de coincidencia, pero también contiene una cadena en la lista no contiene, no se considera una coincidencia.

El campo **[!UICONTROL contiene]** está limitado a 100 caracteres. La lista no contiene está limitada a 255 caracteres menos un carácter separador para cada nueva línea. (Es igual al número de cadenas - 1. Si especifica 4 *no contiene* cadenas, se requieren 3 caracteres separadores.) Todas las coincidencias de cadena no distinguen entre mayúsculas y minúsculas.

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

Para importar de forma masiva reglas de bots, puede cargar un archivo CSV que defina las reglas.

1. Para iniciar el proceso de cargar reglas de bots en un grupo de informes, consulte [Actualizar o cargar reglas de bots](#update-or-upload-bot-rules).

1. Cree un archivo CSV con las columnas siguientes, en la fila 1 de la hoja de cálculo y en el orden presentado:

   | Columna 1, Fila 1 | Columna 2, Fila 1 | Columna 3, Fila 1 | Columna 4, Fila 1 | Columna 5, Fila 1 | Columna 6, Fila 1 |
   |--- |--- |---|---|---|---|
   | Nombre de Bot | IP Begin | IP End | Regla<br>(contiene o empieza con)</br> | Inclusión de agente de usuario | Exclusión del agente de usuario <br>(límite de 255 caracteres)</br> |

   Puede definir tres tipos de reglas de bots:

   * El agente de usuario contiene o empieza por
   * Coincidencia de dirección IP única o comodín
   * Coincidencia de intervalo de IP

   Cada fila del archivo de importación puede contener solo una de las siguientes definiciones de bots:

   >[!NOTE]
   >
   >   Para hacer coincidir un bot con una combinación de reglas unidas con una condición OR (por ejemplo, agente de usuario o dirección IP), proporcione un nombre idéntico para todas las reglas que desee combinar en el campo Nombre del bot. Las coincidencias Y no son compatibles.


   * **El agente de usuario contiene o empieza por**: Proporcione una sola cadena de agente de usuario que coincida en la columna Agent Include. Especifique el tipo de coincidencia que desea que se realice colocando *contains* o *starts with* en el campo Agent Match Rule. En la columna Agent Exclude se puede incluir un valor opcional que defina una o varias cadenas delimitadas por paréntesis (`|`) que el agente no contenga. Las coincidencias de cadenas no distinguen entre mayúsculas y minúsculas. Las columnas IP Start y IP End deben estar vacías.

   * **Coincidencia de dirección IP única o comodín**: Para hacer coincidir una dirección IP única (`10.10.10.1`) o una dirección IP comodín (`10.10.*.*`), introduzca el mismo valor en las columnas IP Start e IP End. Match Rule, Agent Include y Agent Exclude deben estar vacías.

   * **Coincidencia de intervalo de IP**: defina un intervalo de direcciones IP con las columnas IP Start e IP End. Se pueden usar comodines para buscar coincidencias de rangos IP, por ejemplo de `10.10.10.*` a `10.10.20.*`. Match Rule, Agent Include y Agent Exclude deben estar vacías.

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

**Procesamiento de visitas con visitas de alta visita:** Si se producen más de 100 visitas en una visita, los informes determinan si el tiempo de la visita en segundos es menor o igual que el número de visitas en la visita. En esta situación, debido al coste de procesar visitas largas e intensas, los informes comienzan de nuevo con una nueva visita. Las visitas de alta visita suelen estar causadas por ataques de bots y no se consideran una navegación normal de los visitantes.

>[!NOTE]
>
>Las visitas marcadas como *`bots`* se facturan como [llamadas al servidor.](/help/admin/tools/server-call-usage/overage-overview.md)

## Influencia de la confusión de IP en el filtrado para bots {#section_92E60B95BE8940D983F28C79E0CD6B12}

La lista de bots de la IAB se basa únicamente en el agente de usuario, por lo que el filtrado basado en esa lista no se ve afectado por la configuración de confusión de IP. Para el filtrado de bots que no son de la IAB (reglas personalizadas), la dirección IP puede formar parte de los criterios de filtrado. Si se filtran bots mediante IP, el filtrado de bots se produce después de eliminar el último octeto si esa configuración está habilitada, pero antes de las demás opciones de confusión de IP, como eliminar toda la IP o reemplazarla por algún ID único.

Si la confusión de la IP está habilitada, la exclusión de la IP se produce antes de que la dirección IP se confunda, por lo que los clientes no necesitan cambiar nada cuando habilitan la confusión de la IP.

Si se elimina el último octeto, será antes del filtrado de la IP. Como tal, el último octeto se sustituye por un 0 y las reglas de exclusión de la IP se deben actualizar para coincidir con las direcciones de IP que tengan un cero al final. Un coincidente &#42; debe corresponder a un 0.
