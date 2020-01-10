---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
solution: null
title: Variables dinámicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.currencyCode

La variable determina la tasa de conversión que se aplicará a los ingresos.

Todos los importes monetarios se almacenan en la moneda que elija. Si esa moneda es la misma que la especificada en *`currencyCode`*, o *`currencyCode`* está vacía, no se aplica ninguna conversión.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|--- |--- |--- |--- |
| N/A | cc | Conversión &gt; Compras &gt; Ingresos Todos los informes de conversión con los ingresos o los valores monetarios | "USD" |

Si su sitio permite que los visitantes compren en diferentes monedas, debe usar la variable *`currencyCode`* para asegurarse de que los ingresos se almacenan en la moneda apropiada. Por ejemplo, si la moneda base del grupo de informes es USD y vende un artículo por 40 euros, debe rellenar *`currencyCode`* con la divisa “EUR” en la página HTML. En cuanto la recopilación de datos recibe los datos, usa la tasa de conversión actual para convertir los 40 euros en su equivalente en USD.

Se recomienda rellenar la variable *`currencyCode`* en la página HTML en lugar del archivo JavaScript si vende en varias monedas. Si desea utilizar sus propias tasas de conversión en lugar de las tasas de conversión utilizadas por Adobe, establezca el valor *`currencyCode`* para que sea igual a la moneda base del grupo de informes. Después, convierta todos los ingresos antes de enviarlos a [!DNL Analytics].

La conversión monetaria se aplica tanto a los eventos de ingresos como monetarios. Estos son eventos que se usan para sumar valores similares a los ingresos, como los impuestos y el envío. Los eventos de ingresos y monetarios se especifican en la cadena de productos. Para obtener más información sobre los productos, consulte [eventos](https://docs.adobe.com/content/help/es-ES/analytics/implementation/analytics-basics/ref-events.html).

## Sintaxis y valores posibles

```js
s.currencyCode="currency_code"
```

## Ejemplos

```js
s.currencyCode="GBP"
```

```js
s.currencyCode="EUR"
```

## Parámetros de configuración

Adobe [!DNL Customer Care] puede cambiar la configuración predeterminada de su grupo de informes. Cuando se cambia la moneda base de un grupo de informes, los ingresos existentes en el sistema no se convierten. Los valores de ingresos nuevos se convertirán convenientemente.

## Problemas, preguntas y consejos

* Si observa cantidades sorprendentemente grandes de ingresos en los informes, asegúrese de que la variable *`currencyCode`* y la moneda base del grupo de informes estén configuradas correctamente.
* La variable *`currencyCode`* no es persistente, lo que significa que la variable debe pasarse en la misma solicitud de imagen igual que los ingresos y otras métricas relativas a monedas.
* No deben usarse eventos monetarios con otros fines que no sean monetarios. Si necesita contar valores arbitrarios o dinámicos que no son monetarios, use el tipo de evento [!UICONTROL numérico].
* Si la variable *`currencyCode`* está vacía, no se aplica ninguna conversión.

Para obtener más información, consulte [Códigos de moneda](https://docs.adobe.com/content/help/es-ES/analytics/admin/admin-tools/currency.html).
