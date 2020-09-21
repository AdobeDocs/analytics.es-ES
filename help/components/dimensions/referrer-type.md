---
title: Tipo de referente
description: El tipo de remitente del reenvío, según la procedencia del visitante.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '423'
ht-degree: 100%

---


# Tipo de referente

La dimensión “tipo de Remitente del reenvío” indica en qué canales genéricos hicieron clic los visitantes para llegar a su sitio. Adobe mantiene las reglas para cada elemento de dimensión, a diferencia de los [canales de marketing](marketing-channel.md), donde su organización mantiene reglas para cada canal.

## Rellene esta dimensión con datos

Esta dimensión hace referencia a varias tablas de búsqueda internas de Adobe. Cada valor se basa en el [remitente del reenvío](referrer.md) de la visita, que depende de los [filtros de URL internos](/help/admin/admin/internal-url-filter-admin.md). Asegúrese de que la dimensión de remitente del reenvío y los filtros de URL internos están correctamente configurados.

## Elementos de dimensión

Los elementos de dimensión incluyen el tipo de remitente del reenvío de la visita. Los valores específicos incluyen los siguientes:

* **Escritos o marcados**: No existen datos de remitente del reenvío para la visita.
* **Motores de búsqueda**: El remitente del reenvío proviene de un motor de búsqueda reconocido que incluye una cadena de consulta de palabra clave.
* **Redes sociales:** Los datos de Remitente del reenvío pertenecían a una red social reconocida por Adobe.
* **Otros sitios web**: Los datos del Remitente del reenvío no pertenecían a un motor de búsqueda o a una red social que Adobe reconozca.
* **Disco duro**: El Remitente del reenvío se originó a partir de una copia local de una página web en el disco duro del visitante.
* **Correo electrónico**: Remitente del reenvío originado desde una dirección URL con un protocolo de `imap://` o `mail://`. No incluye los servicios de correo electrónico en línea, ya que suelen utilizar el protocolo `https://`.

### Redes sociales

La siguiente lista hace referencia a la tabla de búsqueda “Redes sociales” que utiliza Adobe. Adobe proporciona esta lista como cortesía a los clientes de Adobe Analytics. Si desea recomendar que Adobe agregue un dominio a esta lista, pida a un delegado de asistencia técnica de su organización que se ponga en contacto con el Servicio de atención al cliente.

>[!NOTE]
>
>Esta lista es diferente a la lista predeterminada de las redes sociales en las [reglas de procesamiento de canal de marketing](../c-marketing-channels/c-rules.md).

* `12seconds.tv`
* `t.163.com`
* `4travel.jp`
* `advogato.org`
* `ameba.jp`
* `anobii.com`
* `asmallworld.net`
* `avforums.com`
* `backtype.com`
* `badoo.com`
* `bebo.com`
* `bigadda.com`
* `bigtent.com`
* `biip.no`
* `blackplanet.com`
* `blogspot.com`
* `blogster.com`
* `blomotion.jp`
* `bolt.com`
* `brightkite.com`
* `buzznet.com`
* `cafemom.com`
* `care2.com`
* `classmates.com`
* `cloob.com`
* `collegeblender.com`
* `cyworld.co.kr`
* `cyworld.com.cn`
* `dailymotion.com`
* `yozm.daum.net`
* `delicious.com`
* `deviantart.com`
* `digg.com`
* `diigo.com`
* `disqus.com`
* `draugiem.lv`
* `facebook.com`
* `faceparty.com`
* `fc2.com`
* `flickr.com`
* `flixster.com`
* `fotolog.com`
* `foursquare.com`
* `friendfeed.com`
* `friendsreunited.com`
* `friendsreunited.co.uk`
* `friendster.com`
* `fubar.com`
* `gaiaonline.com`
* `geni.com`
* `goodreads.com`
* `plus.google.com`
* `plus.url.google.com`
* `grono.net`
* `habbo.com`
* `hatena.ne.jp`
* `t.hexun.com`
* `hi5.com`
* `hyves.nl`
* `ibibo.com`
* `identi.ca`
* `t.ifeng.com`
* `imeem.com`
* `hotnews.infoseek.co.jp`
* `instagram.com`
* `intensedebate.com`
* `irc-galleria.net`
* `iwiw.hu`
* `jaiku.com`
* `kaixin001.com`
* `kaixin002.com`
* `kakaku.com`
* `kanshin.com`
* `kozocom.com`
* `last.fm`
* `linkedin.com`
* `livejournal.com`
* `lnkd.in`
* `me2day.net`
* `meetup.com`
* `mister-wong.com`
* `mixi.jp`
* `mixx.com`
* `mouthshut.com`
* `multiply.com`
* `mumsnet.com`
* `myheritage.com`
* `mylife.com`
* `myspace.com`
* `myyearbook.com`
* `nasza-klasa.pl`
* `matome.naver.jp`
* `netlog.com`
* `nettby.no`
* `netvibes.com`
* `nextdoor.com`
* `nicovideo.jp`
* `ning.com`
* `odnoklassniki.ru`
* `ok.ru`
* `orkut.com`
* `pakila.jp`
* `t.people.com.cn`
* `photobucket.com`
* `pinterest.com (and all international domains)`
* `plaxo.com`
* `plurk.com`
* `po.st`
* `t.qq.com`
* `mp.weixin.qq.com`
* `boards.qwant.com`
* `reddit.com`
* `renren.com`
* `blog.seesaa.jp`
* `t.sina.com.cn`
* `skyrock.com`
* `slideshare.net`
* `smcb.jp`
* `smugmug.com`
* `t.sohu.com`
* `sonico.com`
* `studivz.net`
* `stumbleupon.com`
* `t.co`
* `tabelog.com`
* `tagged.com`
* `taringa.net`
* `thefancy.com`
* `toutiao.com`
* `tripit.com`
* `trombi.com`
* `trytrend.jp`
* `tuenti.com`
* `tumblr.com`
* `twine.com`
* `twitter.com`
* `uhuru.jp`
* `viadeo.com`
* `vimeo.com`
* `vk.com`
* `wayn.com`
* `weibo.com`
* `weourfamily.com`
* `wer-kennt-wen.de`
* `wordpress.com`
* `xanga.com`
* `xing.com`
* `answers.yahoo.com`
* `yammer.com`
* `yaplog.jp`
* `yelp.com`
* `yelp.co.uk`
* `youku.com`
* `youtube.com`
* `yuku.com`
* `zooomr.com`
* `zhihu.com`

### Motores de búsqueda en el elemento de dimensión “Otros sitios web”

Cuando vea dominios específicos en la dimensión “tipo de Remitente del reenvío”, puede haber dominios que deberían aparecer en “Motores de búsqueda” enumerados en “Otros sitios web”. Por ejemplo: puede ver `'google.com'` en “Otros sitios web”.

* **Dominios de motor de búsqueda en el elemento de dimensión “Motores de búsqueda”**: El remitente del reenvío cumplió todos los criterios para clasificarse como motor de búsqueda por parte de Adobe. El dominio de referencia es un motor de búsqueda válido *y* la dirección URL de referencia contiene un parámetro de cadena de consulta de palabra clave.
* **Dominios de motor de búsqueda en el elemento de dimensión “Otros sitios web”**: La dirección URL de referencia no cumplía todos los criterios para clasificarse como motor de búsqueda. Algunos ejemplos comunes incluyen subdominios dedicados a otras funcionalidades además de la búsqueda. Por ejemplo: `mail.google.com` o `autos.yahoo.com` no son motores de búsqueda, pero residen en un dominio de nivel superior comúnmente asociado con la búsqueda. Estos subdominios no incluyen una cadena de consulta de palabras clave, por lo que se incluyen en “Otros sitios web” en lugar de en “Motores de búsqueda”.
