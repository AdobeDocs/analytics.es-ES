---
title: Licencias de certificados SSL
description: Procedimientos de certificado para certificados administrados por el cliente
translation-type: tm+mt
source-git-commit: 290838566b86f71902abd303b5c43dd2661d3ce1

---


# Licencias de certificados SSL/TLS

Adobe recomienda administrar el certificado sin ningún costo adicional a través del programa [de certificados administrados de](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html)Adobe.  El programa de certificados administrados de Adobe está completamente automatizado y garantiza que los certificados se renueven a tiempo, de modo que no se vean afectados por certificados caducados.

Si elige no utilizar el programa [de certificados administrados de](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html) Adobe, es responsable de proporcionar un certificado SSL/TLS para utilizar con cookies de origen.

Si proporciona su propio certificado, es su responsabilidad adquirirlo y mantenerlo.  El certificado SSL/TLS debe incluir una licencia de servidor ilimitada.

Para garantizar la seguridad del certificado, obtenga una solicitud [CSR] de firma de certificado de Adobe y organice con la autoridad de certificación deseada la firma del certificado.  Proporcione a Adobe el certificado firmado para la implementación.  Al seguir este proceso, se mantiene la seguridad de la clave del certificado.  El Servicio de atención al cliente de Adobe le ayudará en este proceso.

Como parte del mantenimiento del certificado, al menos un mes antes de que caduque el certificado, organice con la autoridad de certificación deseada para obtener un certificado renovado y proporcionárselo a Adobe.  Este certificado debe utilizar el mismo CSR utilizado anteriormente.  Póngase en contacto con Adobe si necesita una copia del CSR o desea que se genere un nuevo CSR con una nueva clave.

Puede ponerse en contacto con el servicio de atención al cliente en customercare@adobe.com o en el 1-800-497-0335.

Entre las autoridades de certificación más utilizadas se encuentran DigiCert, Comodo y GeoTrust.
