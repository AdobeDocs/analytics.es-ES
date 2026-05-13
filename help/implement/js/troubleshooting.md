---
title: Solución de problemas de implementación de JavaScript
description: Obtenga más información sobre problemas comunes y prácticas recomendadas para solucionar problemas de la implementación de JavaScript.
feature: Implementation Basics
exl-id: e7181e78-65bf-446d-8d5c-b47323dbec1d
role: Developer
TQID: https://experienceleague.adobe.com/U97L94cxnWYpnqsJ3FJh7EBbdIHpFHxfJP7uqoqrGgU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 702
ht-degree: 93%

---

# Solución de problemas de implementación de JavaScript

A continuación se indican varias razones por las que su empresa podría tener problemas para obtener datos correctamente en Adobe Analytics.

## Uso de comillas

La mayoría de las variables enviadas a Adobe son cadenas. En JavaScript, puede utilizar comillas simples o dobles.

### Combinación de comillas para definir una variable

Como práctica recomendada, asegúrese de ser coherente con los tipos de comillas que utiliza. Si una comilla simple designa el inicio de una cadena, debe utilizarse una comilla simple para cerrarla.

Por ejemplo, tanto `s.eVar1 = 'Value'` como `s.eVar1 = "Value"` son ejemplos válidos. En cambio, `s.eVar1 = 'Value"` no es válido.

### Inclusión de comillas simples o dobles en una cadena

A veces, queremos incluir una comilla simple o doble en una cadena. Por ejemplo: Quiere incluir el valor `Alex's sale` o `John the "Hunter"` en los informes. Existen dos métodos para incluir estos valores:

* **Utilice el otro tipo de comillas**: Por ejemplo, `s.eVar1 = "Alex's sale"` y `s.eVar1 = 'John the "Hunter"'` son ejemplos válidos.
* **Omisión de las comillas**: Utilice una barra invertida para omitir las comillas. `s.eVar1 = 'Alex\'s sale'` y `s.eVar1 = "John the \"Hunter\""` son dos ejemplos válidos.

### Evitar el uso de comillas curvas

Algunos programas convierten automáticamente las comillas neutras (`"..."` y `'...'`) en comillas curvas (`"..."` y `'...'`). Evite utilizar editores de documentos (como Microsoft Word) o transferir fragmentos de código por correo electrónico. Las comillas curvas no se pueden usar en JavaScript.

## Referencia al objeto Analytics

Todas las variables enviadas a Adobe utilizan el objeto Analytics. La mayoría de las implementaciones utilizan el objeto `s`. Compruebe que, al hacer referencia a variables, incluye el objeto de Analytics en la referencia.

Por ejemplo, `s.eVar1 = 'Value'` es válido, mientras que `eVar1 = 'Value'` no lo es.

## Defina cada variable una vez

Cuando se ejecuta una función de seguimiento (`s.t()`), AppMeasurement toma todas las variables definidas y las compila en una solicitud de imagen. Si define una variable más de una vez en la implementación, solo se utilizará el valor más reciente. Compruebe que todos los valores de las variables contengan el valor correcto cuando se ejecute la función de seguimiento.

## Corrección del uso de mayúsculas y minúsculas en las variables

Algunas variables utilizan letras mayúsculas. Las variables JavaScript distinguen entre mayúsculas y minúsculas. Compruebe que utiliza las mayúsculas y minúsculas correctas al definir variables. Por ejemplo, `s.eVar1 = 'Value'` es válido, mientras que `s.evar1 = 'Value'` no lo es.

## Complementos

Algunas empresas utilizan complementos para mejorar su implementación de Adobe Analytics. Al actualizar las versiones de AppMeasurement, no olvide volver a incluir los complementos instalados. El código creado en el [!UICONTROL Administrador de códigos] no contiene ningún código del complemento. Realice una copia del código existente en caso de que necesite volver a una versión anterior de AppMeasurement.

## Espacios en blanco en valores de variable

En HTML, hay varios caracteres que crean un espacio en blanco. Estos incluyen un espacio, una tabulación y un retorno de carro (o salto de línea). Consideremos el siguiente ejemplo:

```html
<head>
  <title>
    Home Page
  </title>
</head>
<body>
<script language="javascript">
  s.pageName = document.title;
</script>
</body>
```

En este caso, `document.title` rellena `s.pageName`, que debería recibir el valor &quot;Home Page&quot;. Sin embargo, algunos exploradores pueden interpretar el espacio en blanco de forma diferente. El resultado puede ser uno de los dos ejemplos siguientes:

```js
s.pageName = "Home Page";
```

```js
s.pageName = "        Home Page";
```

Estos dos valores de variable se consideran independientes en Adobe Analytics. Sin embargo, el espacio en blanco se elimina automáticamente con fines de visualización. El resultado es un informe que muestra dos elementos de línea &quot;Página principal&quot; aparentemente idénticos. Compruebe que los valores de las variables no contengan espacios en blanco antes o después del valor deseado.

## Solicitudes de imagen truncadas

Las implementaciones que rellenan muchas variables con valores largos a veces se pueden ejecutar en solicitudes de imagen truncadas. Algunos exploradores más antiguos, como Internet Explorer, imponen un límite de 2083 caracteres en las direcciones URL de solicitudes de imágenes. Si su organización se enfrenta a solicitudes de imagen muy largas, intente lo siguiente:

* **Utilice el servicio de Experience Cloud ID**: Las bibliotecas de AppMeasurement 1.4.1 y posteriores envían automáticamente solicitudes de imagen mediante el POST HTTP si son demasiado largas. Los datos enviados mediante este método no se truncan independientemente de la longitud. Consulte [Servicio de Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es) para obtener más información.
* **Usar reglas de procesamiento**: Las [reglas de procesamiento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) pueden copiar valores de una variable a otra. Este método evita que se establezca el mismo valor en varias variables. Por ejemplo:

  Ejecutar siempre:<br>
Sobrescribir el valor de prop1 con eVar1<br>
Sobrescribir el valor de eVar2 con eVar1<br>
Sobrescribir el valor de prop2 con eVar1<br>

  Luego establezca eVar1 en la implementación:

  ```js
  s.eVar1 = "The quick brown fox jumps over the lazy dog";
  ```

* **Utilice variables dinámicas**: Si la implementación rellena muchas variables con el mismo valor, puede utilizar [variables dinámicas](/help/implement/vars/page-vars/dynamic-variables.md) para acortar la dirección URL de la solicitud:

  ```js
  s.eVar1 = "The quick brown fox jumps over the lazy dog";
  s.eVar2 = "D=v1";
  s.prop1 = "D=v1";
  s.prop2 = "D=v1";
  ```

* **Use clasificaciones**: Si los nombres de producto o de página son inusualmente largos, puede utilizar un código o valor de identificación y, a continuación, utilizar las [clasificaciones](/help/components/classifications/classifications-overview.md) para mostrar un nombre más descriptivo.
