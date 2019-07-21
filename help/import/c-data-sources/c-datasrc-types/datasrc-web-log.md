---
description: Este tipo de fuentes de datos permite importar archivos de registro de servidor web estándar.
seo-description: Este tipo de fuentes de datos permite importar archivos de registro de servidor web estándar.
seo-title: Registro Web
solution: Analytics
subtopic: Fuentes de datos
title: Registro Web
topic: Desarrollador e implementación
uuid: a 0 efed 57-6 d 1 b -43 d 8-97 ce-dc 31009805 e 0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Registro Web

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