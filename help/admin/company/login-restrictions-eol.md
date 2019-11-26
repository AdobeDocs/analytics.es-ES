---
title: Fin de vida útil para [!UICONTROL aplicar restricciones de inicio de sesión IP]
description: Obtenga información sobre el tiempo de finalización de la vida útil y las implicaciones para [!UICONTROL aplicar restricciones de inicio de sesión IP]
translation-type: tm+mt
source-git-commit: 490a856effac7ec3ff2430dff0ffdcee587bf933

---


# Fin de vida útil para [!UICONTROL aplicar restricciones de inicio de sesión IP]

La función **[Aplicar restricciones](/help/admin/company/security-manager.md)** de inicio de sesión IP de Adobe Analytics permite incluir en la lista blanca direcciones IP específicas (que se consideran seguras) para permitir inicios de sesión exitosos y el acceso a su entorno de Adobe Analytics. En muchos casos, esta función se utiliza para configurar una dirección IP corporativa como la única dirección IP segura desde la que los usuarios pueden iniciar sesión. Por lo tanto, para utilizar Adobe Analytics, esto requiere que los usuarios estén en una oficina corporativa o que inicien sesión en la red a través de VPN.

Estamos planeando finalizar la vida útil de esta función en octubre de 2020.

## ¿Por qué estamos acabando de usar esta función?

Esta función se rompe en algunas circunstancias con la migración de inicio de sesión de Experience Cloud o el inicio de sesión de Experience Cloud. Se sabe que se produce un error en los clientes que utilizan Atributos **** del cliente o Biblioteca **[!UICONTROL de]** audiencias.

Además, si posee varias soluciones de Experience Cloud, puede eludir este requisito si inicia sesión en Experience Cloud con una de las otras soluciones, ya que esta función no existe o no se admite fuera de Analytics. Los usuarios también pueden evitar esto a través de la falsificación de IP.

Por último, Adobe cuenta con una solución alternativa funcional y muy superior mediante el inicio de sesión único y Federated ID. Esta función le proporciona un mayor control y seguridad sobre la experiencia de inicio de sesión de los usuarios. Consulte a continuación para obtener más información.

## ¿Cómo le afecta la eliminación de esta función?

Esta función se eliminará en octubre de 2020 para cualquier cliente que tenga **[!UICONTROL configurado las restricciones]** de inicio de sesión de la IP de aplicación. En ese momento, ya no se aplicará ninguna restricción de inicio de sesión IP que aún exista. Si todavía necesita restringir el inicio de sesión por dirección IP, debe revisar e implementar la solución recomendada de inicio de sesión único y Federated ID (más información y recursos a continuación).

Además, la configuración **[!UICONTROL Aplicar restricciones]** de inicio de sesión IP se eliminará del **[!UICONTROLAadministrador &gt; Configuración de la empresa &gt; Administrador]** de seguridad en la interfaz de usuario de Analytics (como se muestra a continuación).

![](assets/sec-manager2.png)

## ¿Cuáles son sus otras opciones?

Como se ha indicado anteriormente, esta función de Analytics finalizará su vida útil. Para darle tiempo para implementar SSO e Federated ID, hemos retrasado la fecha de EOL hasta octubre de 2020.

Tanto los SSO como los Federated ID son soluciones superiores a la función de restricción de inicio de sesión IP que tenemos en la actualidad y le proporcionarán más control, seguridad y características. Para obtener información sobre cómo configurar los SSO/Federated ID, tenemos disponible la siguiente documentación de ayuda. Le recomendamos que los lea a fondo y trabaje con su departamento de TI para implementarlos:

* [Inicio de sesión único y Experience Cloud](https://spark.adobe.com/page/JeSB8EPEQIvjD/)
* [Consola de administración: documentación de configuración de identidad](https://helpx.adobe.com/enterprise/using/set-up-identity.html)
* [Consola de administración: tutorial de configuración de identidad (vídeo)](https://helpx.adobe.com/enterprise/how-to/identity-directories-domains.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&ref=helpx.adobe.com)
* [Tutorial sobre la configuración de Federated ID (vídeo)](https://helpx.adobe.com/enterprise/how-to/identity-configure-ids.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&ref=helpx.adobe.com)
* [Inicio de sesión único: preguntas frecuentes](https://helpx.adobe.com/enterprise/using/sso-faq.html)
* [Tipos de identidad compatibles con Adobe](https://helpx.adobe.com/enterprise/using/identity.html)

Si desea seguir expresando su compatibilidad con las restricciones de inicio de sesión IP y solicitar que Experience Cloud la proporcione, puede votar por esta función en nuestra página [](https://forums.adobe.com/ideas/11648)de foro.