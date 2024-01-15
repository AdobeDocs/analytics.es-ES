---
description: Esta sección contiene directrices para probar las reglas de procesamiento, así como una lista de errores comunes que se deben evitar.
subtopic: Processing rules
title: Consejos y sugerencias de reglas de procesamiento
feature: Processing Rules
role: Admin
exl-id: e663d98b-dcfd-4420-84ac-07ddfe55a3f2
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 100%

---

# Consejos y sugerencias de reglas de procesamiento

Esta sección contiene directrices para probar las reglas de procesamiento, así como una lista de errores comunes que se deben evitar.

## Prueba de reglas de procesamiento {#section_F092D2FECDE24082AE9FC6F8BE87F29F}

Esta sección contiene algunas pautas de ayuda para probar reglas de procesamiento antes de implementarlas en la producción.

**Probar reglas que lean términos de búsqueda**

Para cualquier criterio basado en una búsqueda como, por ejemplo, si prop1 contiene “novedades”, vaya al informe prop 1 y busque “novedades” y vea si hay alguna coincidencia inesperada.

**Probar reglas que leen variables**

Cree una página HTML en blanco en el escritorio, incluya el elemento s_code de su sitio y defina la variable `s.account` en un grupo de informes dev. Si sus reglas se basan en un referente, dominio de referencia, etc., tome algunas URL de ejemplo del informe de referentes activo, defina la variable `s.referrer` con uno de esos valores y cargue la página. Igualmente, si la regla se basa en el valor URL de la página, defina `s.pageURL`. Este mismo proceso se puede utilizar para todas las variables.

**Usar un grupo de informes dev**

Se recomienda configurar las reglas de procesamiento en un grupo de informes dev para garantizar que funcionen correctamente. Si es posible, es recomendable copiar las reglas en un pequeño grupo de informes de producción antes de una implementación amplia.

## Comprobar valores vacíos {#section_EE84A5525E26415787930723B0CAAE0F}

Cuando cree una regla, tenga en cuenta la posibilidad de que existan valores vacíos. Si no agrega una condición que compruebe si hay algún valor vacío, puede sobrescribir accidentalmente variables con valores vacíos.

![](assets/tips-set-value-acquisition-code.png)

También es importante tener en cuenta el orden de procesamiento. En el ejemplo siguiente, parece que la eVar personalizada de nombre de página anterior se definirá en la URL si el nombre de la página no está presente. Sin embargo, la URL está ubicada en el nombre de la página después de aplicar las reglas de procesamiento, por lo que en este caso, el nombre de la página está vacío si no se define en la página.

![](assets/tips-copy-page-name-to-evar.png)

## Evitar la sobrescritura de valores {#section_49FCCA31E31A433EA2EF5EAF91443DAF}

En el ejemplo siguiente, se usan dos variables de datos de contexto en el sitio para capturar términos de búsqueda: search_keyword y search_term. No obstante, en función de la configuración, el valor search_keyword siempre se sobrescribe, incluso si search_term está vacío.

Esta regla debe reconfigurarse para probar cada variable de datos de contexto de un valor antes de rellenar el término de búsqueda interna y, opcionalmente, concatenar los dos valores si hay un caso de uso para mantenerlos a los dos.

![](assets/tips-search-keyword.png)

## Codificar términos de búsqueda en UTF-8 o Unicode {#section_3BBBE1FB8FEA48589362452DE51DB575}

Los términos de búsqueda extraídos de una cadena de consulta deben codificarse correctamente. De lo contrario, no coincidirán con las reglas de procesamiento.

![](assets/tips-multibyte.png)

## Comienza con, Contiene y Termina con {#section_80CE853244FC435B844A09EA51868D8D}

Seleccione la condición de coincidencia apropiada para encontrar la condición más restrictiva que coincida correctamente. Puede buscar valores en un informe antes de crear una regla para asegurarse de que no haya coincidencias no deseadas. Por ejemplo, debe buscar en el informe Prop2 para encontrar todas las ubicaciones en las que coincida esta condición antes de habilitar esta regla.

![](assets/tips-startswith.png)

## Aplicación de las reglas de procesamiento al copiar visitas usando VISTA

Si tiene una regla VISTA configurada para copiar visitas a otro grupo de informes, las visitas se envían aunque haya reglas de procesamiento definidas en el otro grupo de informes.

Si tiene reglas de procesamiento definidas en el grupo de informes original, pueden aplicarse o no en función de cómo configuraron la regla VISTA los servicios de ingeniería. Para averiguarlo, puede preguntarle a su especialista en implementaciones si la regla de VISTA copia los valores “pre” o “post” en el grupo de informes original. Si se copia un valor “pre”, las reglas de procesamiento definidas en el grupo de informes original no se aplican. Si se copia el valor “post”, las reglas de procesamiento se aplican antes de que se copie la visita.
