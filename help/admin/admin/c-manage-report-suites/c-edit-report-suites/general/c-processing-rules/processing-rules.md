---
description: Las reglas de procesamiento simplifican la recopilación de datos y administran el contenido a medida que se envía a los informes.
subtopic: Processing rules
title: Resumen de las reglas de procesamiento
feature: Processing Rules
role: Admin
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 97%

---

# Resumen de las reglas de procesamiento

Las reglas de procesamiento simplifican la recopilación de datos y administran el contenido a medida que se envía a los informes. Las reglas de procesamiento ayudan a simplificar la interacción con los grupos de TI y los desarrolladores Web, porque ofrecen una interfaz para:

* Definir un evento en la página de información general del producto
* Rellenar una campaña utilizando un parámetro de cadena de consulta
* Concatenar una categoría y un nombre de página en una propiedad para crear informes más fácilmente
* Copiar una eVar a una propiedad para ver las rutas
* Corregir las secciones de sitios mal escritas
* Obtener términos de búsqueda interna o un ID de campaña de la cadena de consulta para una eVar



>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Información general sobre las reglas de procesamiento](https://video.tv.adobe.com/v/327638/?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## Permisos de reglas de procesamiento {#section_8A4846688050453784DAE4D89355169A}

Los administradores tienen **de forma predeterminada** permiso para utilizar reglas de procesamiento. Además, pueden conceder este mismo derecho a los demás usuarios desde la interfaz de Herramientas de administración. Para obtener instrucciones, consulte []

![Reglas de procesamiento](assets/processing-rules.png)

## Simplificar la recopilación de datos con datos de contexto {#section_09EEA03612D24C15839631AA9E9668D8}

Las variables de datos de contexto son un tipo de variable y están disponibles solamente para las reglas de procesamiento. Para utilizar variables de datos de contexto, su implementación envía los pares de datos clave/valor, y se utilizan reglas de procesamiento para capturar estos valores en variables estándar de Analytics. Esto evita a los programadores tener que entender exactamente qué propiedad o eVar debería contener cada valor.

```js
s.contextData['author'] = "Robert Munch";
s.contextData['section'] = "Books";
s.contextData['genre'] = "Youth";
```

Una vez configurado el código, puede establecer reglas de procesamiento para asignar valores a variables. Por ejemplo:

1. Mapa `author` a `eVar2`
2. Mapa `section` a `prop1` y `eVar3`
3. Si `author` y `section` existen, establecer `event5`

Consulte [contextData](/help/implement/vars/page-vars/contextdata.md) en la guía del usuario Implementar para obtener más información.

## Transformar datos de visitas y activar eventos con reglas de procesamiento {#section_8284E72E999244E091CD7FB1A22342B6}

Las reglas de procesamiento pueden supervisar los valores entrantes para transformar errores tipográficos comunes y definir eventos según los datos de los informes. Las props se pueden copiar en eVars, los valores se pueden concatenar para los informes y se pueden definir eventos.

## Uso de variables de datos de contexto en informes {#section_BD098BC503024A0B8703596628071134}

Una vez que las variables de datos de contexto se definen en la implementación, se deben copiar en variables como las eVar para poder utilizarse en la creación de informes.

Consulte [Copiar una variable de datos de contexto en una eVar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md) y [Definir un evento con una variable de datos de contexto](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md) para obtener más información.

## Limitaciones conocidas

**Uso del signo de intercalación (^) en reglas de procesamiento.** Si desea utilizar signos de intercalación en reglas de procesamiento como delimitadores o para otros fines, cada signo de intercalación individual debe estar representado por dos signos de intercalación. Por ejemplo, represente un solo signo de intercalación como ^^, un doble signo de intercalación como ^^^^, etc.