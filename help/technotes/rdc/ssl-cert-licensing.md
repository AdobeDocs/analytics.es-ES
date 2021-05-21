---
title: Licencias de certificados SSL
description: Procedimientos de certificados para los certificados administrados por el cliente
exl-id: 7d1373c8-6f7b-4ce7-a555-d3d506e08d17
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '260'
ht-degree: 100%

---

# Licencias de certificados SSL/TLS

Adobe recomienda administrar el certificado sin ningún coste adicional a través del [programa de certificados administrados de Adobe](https://docs.adobe.com/content/help/es-ES/core-services/interface/ec-cookies/cookies-first-party.html). El programa de certificados administrados de Adobe está completamente automatizado y garantiza que los certificados se renueven a tiempo. De este modo, se evitan consecuencias derivadas de la presencia de certificados caducados.

Si elige no utilizar el [programa de certificados administrados de Adobe](https://docs.adobe.com/content/help/es-ES/core-services/interface/ec-cookies/cookies-first-party.html), es responsabilidad suya proporcionar el certificado SSL/TLS que se vaya a usar con las cookies de origen.

Si proporciona su propio certificado, es su responsabilidad adquirirlo y mantenerlo.  El certificado SSL/TLS debe incluir una licencia de servidor ilimitada.

Para garantizar la seguridad del certificado, obtenga una solicitud de firma de certificado ([CSR]) de Adobe y póngase en contacto con la autoridad de certificación que desee para la firma del certificado.  Para la implementación, proporcione a Adobe el certificado firmado.  Si sigue este proceso, mantendrá la seguridad de la clave del certificado.  El Servicio de atención al cliente de Adobe le ayudará durante el proceso.

Como parte del mantenimiento del certificado, al menos un mes antes de su fecha de caducidad, póngase en contacto con la autoridad de certificación que desee para obtener un certificado renovado y proporcióneselo a Adobe.  Este certificado debe usar el mismo CSR utilizado anteriormente.  Póngase en contacto con Adobe si necesita una copia del CSR o si desea que se genere un nuevo CSR con una nueva clave.

Puede ponerse en contacto con el servicio de atención al cliente en customercare@adobe.com o en el 1-800-497-0335.

Entre las autoridades de certificación más utilizadas se encuentran DigiCert, Comodo y GeoTrust.
