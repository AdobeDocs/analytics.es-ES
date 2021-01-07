---
title: Preguntas más frecuentes sobre las clasificaciones
description: Preguntas más frecuentes sobre el uso de las clasificaciones.
translation-type: tm+mt
source-git-commit: a63b8ae3948ffd9a37058696aa1b1d4c923709ba
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 88%

---


# Preguntas más frecuentes sobre las clasificaciones

Preguntas más frecuentes sobre el uso de las clasificaciones.

## ¿Cómo clasifico el elemento de dimensión “0”?

Los archivos de clasificación cargados con un valor clave o un valor de clasificación de cero (`0`) dan como resultado un error. Incluye todos los valores que solo contienen ceros (`00`, `000`, etc.). Existen varios métodos para resolver este problema:

* **Implementar valores alternativos**: El uso de un valor de texto distinto de `"0"` es la mejor forma y la más sencilla de resolver este problema. Por ejemplo, cambie `s.campaign = "0";` en la implementación a `s.campaign = "Zero";`.

* **Usar reglas de procesamiento**: Puede modificar los elementos de dimensión entre la recopilación de datos y su almacenamiento en un grupo de informes. Cree la siguiente regla de procesamiento:

   *Si la [dimensión] es igual a `0`, sobrescriba el valor de la [dimensión] con el valor personalizado `Zero`.*

* **Solicitar una regla VISTA**: Un consultor de servicios de ingeniería configura una regla del lado del servidor para usted con un coste adicional. Póngase en contacto con el administrador de cuentas de su organización para solicitar una regla VISTA.

## ¿Puedo usar el importador de clasificaciones para clasificar los elementos de dimensión que aún no existen?

Sí, *sin embargo, al hacerlo se cuenta cada elemento de dimensión como una llamada al servidor facturable.*

* Los artículos de dimensión que ya existen no incurren en ningún coste adicional.
* El uso del generador de reglas de clasificación no clasifica elementos inexistentes y, por lo tanto, no incurre en ningún coste adicional.

## ¿Cómo clasifico los valores que contienen caracteres especiales?

Normalmente no se recomienda utilizar caracteres especiales como comas o comillas de doble en el sistema de informes. Sin embargo, en algunos casos su uso es necesario. Si los valores de sistema de informes contienen los caracteres que elija clasificar, siga estos pasos:

1. Inicie sesión en Adobe Analytics y, a continuación, vaya a **[!UICONTROL Administración]** > **[!UICONTROL Importador de clasificaciones]**.
2. Haga clic en la pestaña **[!UICONTROL Exportación del explorador.]**
3. Configure los ajustes de exportación y asegúrese de que la opción “Salida de cotización” NO está seleccionada.
4. Haga clic en **[!UICONTROL Exportar archivo]** y abra el archivo descargado en un editor de hojas de cálculo.
5. En la línea 1, localice la celda C1, que contiene el valor `v:2.0`. Cambie el valor a `v:2.1` y aplique las clasificaciones deseadas al libro.
6. Cargue el archivo como lo haría con cualquier otra clasificación.

## ¿Qué son las clasificaciones numéricas 2?

Las clasificaciones numéricas 2 permiten clasificar los elementos de dimensión como métricas basadas en el tiempo. Fueron retirados de la interfaz de usuario de Adobe Analytics en julio de 2019.
