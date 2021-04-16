---
description: Este tipo de fuentes de datos permite importar archivos de registro de servidor web estándar.
subtopic: Data sources
title: Registro web
topic-fix: Developer and implementation
uuid: a0efed57-6d1b-43d8-97ce-dc31009805e0
exl-id: 11c4f21a-de07-436e-a05e-ab6769cb3e21
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 100%

---

# Registro web

Este tipo de fuentes de datos permite importar archivos de registro de servidor web estándar.

Los tipos más comunes de registro de servidor web admitidos son:

| Nombre de columna | Descripción |
|--- |--- |
| Registro común de NCSA | Predeterminado de Apache |
| NCSA ampliado (combinado) | Apache |
| Registro ampliado de W3C | Utilizado por IIS 4.0 o posterior |
| Registro de Microsoft IIS | Utilizado por IIS 3.0 o anterior |

Los campos primarios del archivo de registro que procesa el sistema de fuentes de datos son la dirección IP, la fecha/hora de la solicitud y la dirección URL. En algunos pocos casos, por ejemplo el formato NCSA ampliado, el sistema también procesa los campos de referente y agente de usuario.

Los datos de registro web se pueden ver mediante los siguientes informes estándar de marketing: Visitas, Visitantes y Vistas de página. Como las métricas de informes se basan principalmente en cookies y los registros de servidor web se basan en la dirección IP, Adobe recomienda importar los datos de registro de servidor web a un grupo de informes separado que sea exclusivo para ese fin.

Para obtener más información sobre estos archivos de registro, consulte la documentación del servidor web.
