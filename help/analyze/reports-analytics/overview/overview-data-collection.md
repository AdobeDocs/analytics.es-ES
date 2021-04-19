---
description: Obtenga más información sobre cómo se recopilan los datos para Adobe Analytics.
subtopic: Get started
title: Información sobre la recopilación de datos
uuid: 4dd9a23d-ad49-4841-8f4c-32c3993851f2
feature: Conceptos básicos de Reports & Analytics y conceptos básicos de Analytics
role: Business Practitioner, Administrator
exl-id: 34a7be55-519a-4e04-95a3-99b0f6e04b3e
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 97%

---

# Información sobre la recopilación de datos

Obtenga más información sobre cómo se recopilan los datos para Adobe Analytics.

Cada página que de la que Adobe realiza un seguimiento tiene un pequeño fragmento de código JavaScript autorizado por Adobe. El administrador de cuentas proporciona dicho código.

En un nivel superior, el proceso de recopilación de datos fluye de la siguiente manera:

![](assets/data_collection.png)

1. Un visitante entra en una página web que contiene el código de recopilación de datos.
1. Conforme se carga la página, el código de recopilación de datos envía una solicitud de imagen (que se denomina señalización web) a los servidores de recopilación de datos de Adobe. La solicitud de imagen contiene los datos que desea recopilar acerca de la interacción del visitante con el sitio web.
1. Adobe almacena los datos en grupos de informes. Puede iniciar sesión para acceder a los datos del grupo de informes y generar informes relacionados con la actividad de los visitantes en el sitio web.

La recopilación de datos es muy rápida y no se percibe en los tiempos de carga de las páginas. Los datos recopilados incluyen las vistas de páginas resultantes de hacer clic en los botones **Actualizar** o **Atrás**. El código JavaScript se ejecuta incluso cuando la página se recupera de la caché.

Consulte [Recopilación de datos en Analytics](/help/import/home.md).
