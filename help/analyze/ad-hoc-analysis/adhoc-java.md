---
description: Instrucciones sobre cómo ejecutar Ad Hoc Analysis con Java 11.
title: Ejecutar Ad Hoc Analysis en Java 11
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Ejecutar Ad Hoc Analysis en Java 11

Debe seguir pasos adicionales cuando ejecute Análisis ad hoc con Java 11 en comparación con la ejecución con Java 8.

## Requisitos previos

Trabaje con su equipo de TI para asegurarse de que se dispone de lo siguiente:

* Java 11 debe estar instalado, con el conjunto de variables de entorno *JAVA_HOME* configurado
* JavaFX debe estar instalado, con la variable de entorno *PATH_TO_FX_SDK* apuntando al directorio del SDK de JavaFX. Por ejemplo, *PATH_TO_FX_SDK=/homedir/javafx-sdk-11.0.2* en un Mac o *PATH_TO_FX_SDK=C:\Users\username\javafx-sdk-11.0.2* en un PC.

## Instalación de la Análisis ad hoc para Java 11

1. Vaya a **[!UICONTROL Analytics > Tools > Ad Hoc Analysis]**.
1. Haga clic en **[!UICONTROL Ad Hoc Analysis (Java 11)]**. Esto descarga un archivo zip.
1. Descomprima el archivo descargado.
1. **Seleccione el archivo**.bat (PC) o .sh (Mac). Seleccione el archivo del centro de datos adecuado mirando el número que sigue a “sc” en la URL de Adobe Analytics. (3 = LON, 4 = SIN, 5 = PNW) Si utiliza un PC, compruebe si está ejecutando un sistema operativo Windows de 32 bits o de 64 bits en “Acerca de su PC”. A continuación, seleccione el archivo .bat correspondiente.
1. **Ejecute el archivo** seleccionado. Para PC: Haga doble clic en el archivo .bat. Para Mac: Haga clic con el botón derecho en el archivo .sh y seleccione **[!UICONTROL Open With > Other... > Utilities > (Enable all applications) > select Terminal > Open]**.
1. Inicie sesión en el Ad Hoc Analysis.

>[!NOTE] La versión Java 11 del Ad Hoc Analysis no admite los métodos de autenticación Federated y Enterprise ID.

## Características no admitidas en el Ad Hoc Analysis (Java 11)

Existen algunas limitaciones conocidas en la versión Java 11 compatible con Ad Hoc Analysis:

* No se admiten los métodos de autenticación de Federated &amp; Enterprise ID.
* Los sistemas operativos Linux no son compatibles.
* Cuando utilice Mac, no use el menú de aplicación de Mac (incluido *cmd + Q*). Esto puede hacer que la Análisis ad hoc se cierre sin previo aviso. En su lugar, utilice el menú dentro de la Análisis ad hoc.
* La visualización de Análisis del sitio no se admite al ejecutar una Análisis ad hoc en MacOS.

## Preguntas más frecuentes

**P: Aparece un error “No se puede encontrar el archivo \bin\javaw” (ejemplo abajo), ¿qué tengo que hacer?**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

R: Si le ocurre este error, trabaje con su equipo de TI para establecer la variable de entorno *JAVA_HOME* necesaria para ejecutar el Ad Hoc Analysis en Java 11.
