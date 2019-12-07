---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# visitorID

Los visitantes se pueden identificar mediante la variable o por dirección IP o agente de usuario.


<!-- 

visitorID.xml

 -->

El *`visitorID`* puede tener hasta 100 caracteres alfanuméricos y no debe contener guiones.

Si configura explícitamente una ID personalizada, siempre se utilizará antes de los otros métodos de ID.

Este es el orden de uso: s.visitorID &gt; s_vi &gt; s_fid &gt; IP/UA.

| ** Tamaño máximo** | ** Parámetro depurador** | ** Informes rellenados** | ** Valor predeterminado** |
|---|---|---|---|
| 100 bytes | vid | n.d. | "" |

**Sintaxis y valores posibles** {#section_5F768C7AE6824557997E92B295C09280}

```js
s.visitorID="visitor_id"
```

> [!NOTE] La variable *`visitorID`* no debe contener guiones.

**Ejemplos** {#section_F7F07FEFAC3644A5A084D166ACE1315E}

```js
s.visitorID="abc123"
```

**Parámetros de configuración** {#section_582B376FE55C4BCA8F978E0F62B5DB54}

Ninguna
