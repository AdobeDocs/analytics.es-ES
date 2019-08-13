---
description: Las reglas de bots personalizadas permiten filtrar el tráfico en función de las condiciones definidas.
seo-description: Las reglas de bots personalizadas permiten filtrar el tráfico en función de las condiciones definidas.
seo-title: Crear una regla de bots personalizada
solution: Analytics
subtopic: Reglas de bots
title: Crear una regla de bots personalizada
topic: Herramientas de administración
uuid: abbc 5 c 7 e -912 f -4660-a 02 b -0431 a 740 ec 70
translation-type: tm+mt
source-git-commit: 4a627e268994d0152a19fb44e9bc06ea7ebc64c6

---


# Crear una regla de bots personalizada

Las reglas de bots personalizadas permiten filtrar el tráfico en función de las condiciones definidas.

Las reglas de bots personalizadas se definen usando los tipos de condición siguientes:

* Agente de usuario
* Dirección IP
* Rango IP

Para una sola regla se pueden definir varias condiciones. Las diversas condiciones se comparan usando “or”. Por ejemplo, si proporciona un valor para agente de usuario y dirección IP, el tráfico se considera tráfico de bots si se cumple cualquiera de las condiciones.

## Agente de usuario

Una condición de agente de usuario comprueba el valor de agente de usuario para ver si **[!UICONTROL comienza con]** o **contiene]la cadena especificada.[!UICONTROL ** Si se selecciona **[!UICONTROL contiene], la subcadena se hace coincidir si tiene lugar en cualquier parte del agente de usuario.**

Se pueden incluir valores opcionales en la lista **[!UICONTROL no contiene]para definir valores que el agente de usuario no debe contener para que la coincidencia tenga éxito.** Se pueden especificar varios valores incluyendo un valor por línea. Si el agente de usuario cumple con los criterios especificados en la cadena de coincidencia, pero además contiene una cadena en la lista “no contiene”, no se considerará una coincidencia.

El campo **[!UICONTROL contiene]está limitado a 100 caracteres.** La lista no contiene está limitada a 255 caracteres menos un carácter separador para cada línea nueva. (Esto es igual al número de cadenas - 1. Para especificar 4 cadenas *no contiene* se necesitan 3 caracteres separador). Todas las coincidencias de cadena distinguen entre mayúsculas y minúsculas.

## Dirección IP (incluyendo coincidencias de comodín)

Hace coincidir una dirección IP o varias direcciones en el mismo bloque usando comodines (*). Proporcione los valores numéricos de la dirección IP que desee hacer coincidir. Sustituya * en los valores que desee hacer coincidir usando un comodín. La lista siguiente contiene ejemplos de cadena de coincidencia de dirección IP:

```
10.10.10.1
10.10.10.*
```

## Rango de direcciones IP

Proporcione el rango inicial y final de las direcciones IP para buscar coincidencias. Sustituya * en los valores que desee hacer coincidir usando un comodín.

## Definición de una regla de bots personalizada

1. Go to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]**, select one or more report suites and click **[!UICONTROL General]** &gt; **[!UICONTROL Bot Rules]**.
1. Click **[!UICONTROL Add Rule]** and define one or more match conditions.
1. Haga clic en **[!UICONTROL Guardar]**. El cambio puede tardar 30 minutos en implementarse.

>[!Note]
>La interfaz de usuario permite definir 500 reglas manualmente. Una vez alcanzado este límite, es necesario gestionar las reglas de forma masiva mediante las opciones Importar archivo y Exportar reglas Bot.
