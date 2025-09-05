---
description: Las reglas de procesamiento simplifican la recopilación de datos y administran el contenido a medida que se envía a los informes.
subtopic: Processing rules
title: Resumen de las reglas de procesamiento
feature: Processing Rules
role: Admin
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 3%

---

# Resumen de las reglas de procesamiento

Las reglas de procesamiento permiten modificar la forma en que se recopilan los datos antes de que se escriban en un grupo de informes.

**[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** > Seleccionar grupo de informes > **[!UICONTROL Editar configuración]** > **[!UICONTROL General]** > **[!UICONTROL Reglas de procesamiento]**

>[!WARNING]
>
>Las reglas de procesamiento afectan directamente a la recopilación de datos y pueden causar pérdida de datos si se utilizan incorrectamente. Pruebe siempre las reglas de procesamiento en un grupo de informes de desarrollo antes de habilitarlas en un grupo de informes de producción para mitigar los problemas de calidad de los datos.

Los dos casos de uso principales de las reglas de procesamiento son:

* **Use el flujo de trabajo de implementación de la variable de datos de contexto**: En lugar de establecer variables directamente en la implementación, puede usar [Variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md) para establecer pares de clave/valor. Por ejemplo, en lugar de configurar:

  ```js
  s.eVar1 = "Robert Munch";
  s.eVar2 = "Books";
  s.eVar3 = "Youth";
  ```

  En su lugar, puede establecer:

  ```js
  s.contextData['author'] = "Robert Munch";
  s.contextData['section'] = "Books";
  s.contextData['genre'] = "Youth";
  ```

  A continuación, puede asignar las variables de datos de contexto a las dimensiones y métricas deseadas en la IU de Analytics.

  Al comunicarse con los desarrolladores de su organización para implementar Analytics en una propiedad, el uso de variables de datos de contexto simplifica el proceso de comunicación. Los desarrolladores pueden implementar cada par clave/valor una vez, y usted como administrador de Analytics puede asegurarse de que los datos llegan a la variable de implementación correcta.

* **Modificar datos a medida que se recopilan**: este caso de uso tiene una amplia gama de aplicaciones, como correcciones temporales a la calidad de los datos o para ayudar a rellenar los huecos de implementación. Consulte [Casos de uso de reglas de procesamiento](pr-use-cases.md) para obtener más información y ejemplos específicos.

## Permisos

Los administradores de productos tienen acceso a las reglas de procesamiento de forma predeterminada. Puede conceder acceso a las reglas de procesamiento a los no administradores incluyéndolas en un perfil de producto que incluya el elemento de permiso **[!UICONTROL Reglas de procesamiento]**. Consulte [Permisos de perfil de producto para las herramientas de grupos de informes](/help/admin/admin-console/permissions/report-suite-tools.md) para obtener más información.

## Consideraciones al crear o editar reglas de procesamiento

Al crear o editar reglas de procesamiento, tenga en cuenta lo siguiente:

* **Posibles valores vacíos**: cuando cree una regla, tenga en cuenta los casos en los que el valor de sobrescritura esté vacío. Por ejemplo, si tiene una regla que sobrescribe eVar1 con eVar2 y eVar2 está vacía, ambas variables aparecen en blanco. Adobe recomienda agregar una condición que compruebe si hay un valor de variable antes de utilizarlo para sobrescribir otro valor.
* **Aplicar inmediatamente al guardar**: Las reglas de procesamiento se aplican a los datos recopilados en el momento en que los guarda. No se aplican de forma retroactiva a los datos que ya se han recopilado.
* **Orden de procesamiento dentro de las reglas**: Si tiene varias reglas de procesamiento, el orden en que se ejecuten es importante. Si utiliza una variable determinada en varias reglas, asegúrese de que se ejecutan en el orden correcto. Si sobrescribe eVar3 en la regla 1, ese valor eVar3 original no estará disponible en ninguna regla posterior.
* **Orden de procesamiento dentro de la canalización de recopilación de datos**: consulte [Orden de procesamiento de datos en Adobe Analytics](/help/technotes/processing-order.md) para saber dónde se aplican las reglas de procesamiento en la canalización de recopilación de datos general.
* **Codificación**: adhiera a la codificación UTF-8 en casi todos los casos.
* **Distinción entre mayúsculas y minúsculas**: las comparaciones de cadenas en reglas de procesamiento no distinguen entre mayúsculas y minúsculas. Los valores de cadena que utiliza para sobrescribir valores utilizan las mismas reglas que para rellenar directamente la variable.
* **Grupo de informes único**: Cuando edita las reglas de procesamiento, se aplican solo a un grupo de informes. Si se seleccionan varios grupos de informes en el Administrador del grupo de informes, se fuerza la selección de un único grupo de informes. Una vez que haya creado o editado las reglas de procesamiento deseadas, puede [copiar esas reglas en otros grupos de informes](pr-copy.md).
* **Sin exclusión de datos**: la exclusión de datos no es una característica prevista de las reglas de procesamiento. Considere la posibilidad de usar [`abort`](/help/implement/vars/config-vars/abort.md) en el nivel de recopilación de datos o de usar [reglas VISTA](/help/technotes/vista.md) después de recopilar los datos.
* **Variables disponibles**: No todas las dimensiones y métricas están disponibles en las reglas de procesamiento. Consulte [Dimensiones y métricas disponibles para las reglas de procesamiento](pr-variables.md) para obtener una lista completa de las que se admiten.
* **Número de reglas permitidas**: Cada grupo de informes puede contener hasta 150 reglas. Cada regla puede contener hasta 30 condiciones.

>[!MORELIKETHIS]
>
>![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Asignación de variables de datos de contexto a props y eVars con reglas de procesamiento](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/implementation/implementation-basics/map-contextdata-variables-into-props-and-evars-with-processing-rules){target="_blank"}
