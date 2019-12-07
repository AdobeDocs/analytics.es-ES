---
description: Adobe ofrece algunas prácticas recomendadas para actualizar el código de Analytics.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Reemplazar el código de Analytics
topic: Developer and implementation
uuid: d3ea6585-199f-4dbe-9ee8-15b204689f2f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Reemplazar el código de Analytics

Adobe ofrece algunas prácticas recomendadas para actualizar el código de Analytics.

Con frecuencia, los clientes utilizan el [!UICONTROL Administrador de códigos] de Adobe para reemplazar su código por la versión más reciente. Este es un procedimiento recomendado siempre que tenga en mente algunas cosas.

## Uso de una ID de servidor de recopilación de datos incorrecta {#section_1726CEB1ABEC408492569B06664410C8}

En ocasiones se envían archivos [!DNL s_code.js] genéricos que no se han generado desde el Administrador de códigos de Adobe a los que implementan el código en el sitio. Como resultado, se utiliza una ID de servidor de recopilación de datos incorrecta (como se muestra en la variable [!UICONTROL s.dc]) en la cuenta. Es mejor generar el nuevo código directamente desde el [!UICONTROL Administrador de códigos] para un grupo de informes determinado en lugar de reutilizar código de un grupo de informes diferente. Esta es la mejor manera de asegurarse de que la variable [!UICONTROL s.dc] se rellena correctamente.

## Complementos {#section_53650E52D6A54A4795F95E491E7548D1}

Algunos clientes implementan complementos para mejorar su experiencia con Adobe. Cuando reemplace código, no olvide que tiene complementos como parte de ese código. El código creado en el [!UICONTROL Administrador de códigos] no contiene ningún código de complemento, por lo que es necesario migrar todos los complementos manualmente a la nueva base de código. Cree una copia del código existente por si algo sucediera y necesitara revertir el código anterior.
