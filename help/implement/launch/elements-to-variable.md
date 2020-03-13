---
description: 'null'
title: Asignación de elementos de datos a variables de Analytics
uuid: null
translation-type: tm+mt
source-git-commit: bb9648f4886ac26c77d89f850f7a68d40a9b4ffc

---


# Asignación de elementos de datos de inicio a variables de Analytics


Después de [asignar los objetos de capa de datos a Elementos](https://docs.adobe.com/content/help/en/analytics/implementation/layer-to-elements.md)de datos de lanzamiento, puede asignar elementos de datos a variables [de](https://docs.adobe.com/content/help/en/analytics/implementation/vars/overview.html)Analytics.

Para asignar elementos de datos de Launch a variables de Analytics:

1. Si corresponde, asigne el elemento de datos a una variable global. Algunos elementos de datos, como Nombre *de* página, se aplican a todas las páginas de una propiedad. En casos como este, puede configurar la variable globalmente haciendo lo siguiente:

2. En Iniciar, desplácese hacia abajo y haga clic en **Extensiones Catálogo**.

   ![Catálogo de extensiones](assets/extensions.png)

3. Haga clic en **Configurar** en Analytics.

   ![Extensión de Analytics](assets/configure.png)


4. En **eVars** en Variables **** globales, seleccione la [eVar que ha configurado](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) para asociarse a la variable. Seleccione **Establecer como** y haga clic en el icono de barras en el campo situado más a la derecha para especificar el elemento de datos.

   ![Especificar eVar](assets/evars.png)

5. En la ventana emergente **Seleccionar elemento** de datos, seleccione el elemento de datos que desee aplicar a la variable.

6. Haga clic en **Guardar**.


Como alternativa, si el elemento de datos no está asociado con una variable global, puede simplemente [crear una regla](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) que asigne los elementos de datos a props o evars.
