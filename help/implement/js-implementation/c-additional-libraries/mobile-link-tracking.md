---
description: 'null'
keywords: Analytics Implementation;link reference;redir
title: Medición de vínculos personalizados con protocolos móviles
topic: Developer and implementation
uuid: eb82de26-da2e-41c2-8924-59b6b5ccef28
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Medición de vínculos personalizados con protocolos móviles

Muchos usuarios de dispositivos móviles descargan archivos en sus dispositivos, como podcasts, tonos de llamada y archivos similares. Como muchos de estos dispositivos no admiten JavaScript, la medición de vínculos debe implementarse a través de redirecciones. Si desea usar las redirecciones, debe modificar los vínculos href en el código html para incluir el elemento REDIR. Los vínculos personalizados tienen el formato general siguiente:

```
https://<your_Namespace>.112.2o7.net/b/ss/<RSID>/4/REDIR/
?url=<destination_URL>&pe=<link_type>&pev1=<current_URL>&pev2=<link_name>
```

A la hora de crear referencias de vínculo, tenga presente lo siguiente:

* El valor URL debe tener codificación de dirección URL.
* Debe establecer un parámetro pageName o de dirección URL de página (g).
* Las variables dinámicas pueden leer el parámetro de dirección URL, pero no establecerlo.
* Si no se establece ninguna cookie, los servidores de Adobe realizan una negociación de cookies normal.
* Para rastrear vínculos, debe incluir los parámetros pe, pev1 y pev2.

Una dirección URL de medición de vínculos personalizada tiene un aspecto similar a este:

```
<a href=" https://johnny_appleseed.122.2o7.net/b/ss/appleseedpodcasts/4/REDIR/
?url=http%3A%2F%2Fwww.johnny_appleseed.org%2Fmpegs%2Fplanting_apple_trees.mpeg&pe=lnk_d
&pev1=http%3A%2F%2Fwww.johnny_appleseed.org%2Fmpegs%2Fplanting_apple_trees.mpeg&pev2=pl anting_apple_trees&">Planting an Apple Tree</a>
```

Para obtener más información, consulte el [documento técnico Redirecciones de seguimiento de vínculos de salida](https://marketing.adobe.com/resources/help/en_US/whitepapers/redirects/).
