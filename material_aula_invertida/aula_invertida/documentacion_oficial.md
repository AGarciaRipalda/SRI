# Enlaces a Documentación Oficial

## 📚 Documentación Esencial

Esta recopilación de enlaces te proporcionará acceso directo a la documentación oficial y recursos técnicos de referencia para la administración de servicios de correo electrónico.

---

## 🔧 Postfix - Mail Transport Agent

### Documentación Oficial Postfix

#### Página Principal
- **Postfix.org**: [https://www.postfix.org/](https://www.postfix.org/)
- Sitio oficial del proyecto Postfix

#### Parámetros de Configuración
- **Postfix Configuration Parameters**: [https://www.postfix.org/postconf.5.html](https://www.postfix.org/postconf.5.html)
- Referencia completa de todos los parámetros disponibles en `main.cf`
- **Uso**: Consulta obligatoria para entender cada directiva

#### Ejemplos de Configuración Estándar
- **Standard Configuration Examples**: [https://www.postfix.org/STANDARD_CONFIGURATION_README.html](https://www.postfix.org/STANDARD_CONFIGURATION_README.html)
- Configuraciones tipo para diferentes escenarios
- Incluye ejemplos de relay, virtual hosting, etc.

#### Diferencia entre main.cf y master.cf
- **Server Fault - Postfix master.cf vs main.cf**: [https://serverfault.com/questions/462825/postfix-master-cf-versus-main-cf](https://serverfault.com/questions/462825/postfix-master-cf-versus-main-cf)
- Explicación clara de las diferencias entre ambos archivos

---

## 📬 Dovecot - Mail Delivery Agent

### Documentación Oficial Dovecot

#### Wiki Principal
- **Dovecot Documentation**: [https://doc.dovecot.org/](https://doc.dovecot.org/)
- Documentación completa y actualizada

#### Mecanismos de Autenticación
- **Authentication Mechanisms**: [https://doc.dovecot.org/main/core/config/auth/mechanisms/overview.html](https://doc.dovecot.org/main/core/config/auth/mechanisms/overview.html)
- Guía sobre PLAIN, CRAM-MD5, OAuth2, etc.
- **Crítico** para configurar autenticación segura

#### Integración Dovecot LDA con Postfix
- **Dovecot LDA with Postfix**: [https://doc.dovecot.org/2.3/configuration_manual/howto/dovecot_lda_postfix/](https://doc.dovecot.org/2.3/configuration_manual/howto/dovecot_lda_postfix/)
- Cómo usar Dovecot como agente de entrega local

#### Dovecot SASL con Postfix
- **Postfix and Dovecot SASL**: [https://doc.dovecot.org/main/howto/sasl/postfix.html](https://doc.dovecot.org/main/howto/sasl/postfix.html)
- Configuración de autenticación SASL entre Postfix y Dovecot

---

## 🔐 Seguridad y Autenticación

### SPF (Sender Policy Framework)

#### RFC 7208 - SPF Specification
- **IETF RFC 7208**: [https://datatracker.ietf.org/doc/html/rfc7208](https://datatracker.ietf.org/doc/html/rfc7208)
- Especificación oficial del protocolo SPF

### DKIM (DomainKeys Identified Mail)

#### RFC 6376 - DKIM Specification
- **IETF RFC 6376**: [https://datatracker.ietf.org/doc/html/rfc6376](https://datatracker.ietf.org/doc/html/rfc6376)
- Especificación oficial de DKIM

#### Configuración DKIM con OpenDKIM
- **EasyDMARC - Configure DKIM with Postfix**: [https://easydmarc.com/blog/how-to-configure-dkim-opendkim-with-postfix/](https://easydmarc.com/blog/how-to-configure-dkim-opendkim-with-postfix/)
- Guía práctica paso a paso

- **DMARCReport Guide**: [https://dmarcreport.com/blog/complete-dmarcreport-guide-configuring-dkim-opendkim-postfix-mail-server-secure/](https://dmarcreport.com/blog/complete-dmarcreport-guide-configuring-dkim-opendkim-postfix-mail-server-secure/)
- Tutorial completo con ejemplos

### DMARC (Domain-based Message Authentication)

#### Sitio Oficial DMARC
- **DMARC.org**: [https://dmarc.org/](https://dmarc.org/)
- Recursos, especificaciones y mejores prácticas

#### RFC 7489 - DMARC Specification
- **IETF RFC 7489**: [https://datatracker.ietf.org/doc/html/rfc7489](https://datatracker.ietf.org/doc/html/rfc7489)
- Especificación oficial del protocolo

#### Guías de Configuración DMARC
- **Mimecast - Cómo crear registro DMARC**: [https://www.mimecast.com/es/content/how-to-create-a-dmarc-record/](https://www.mimecast.com/es/content/how-to-create-a-dmarc-record/)
- Guía paso a paso en español

- **PowerDMARC - Configuración SPF, DKIM, DMARC**: [https://powerdmarc.com/es/cpanel-dmarc-spf-dkim-setup-guide/](https://powerdmarc.com/es/cpanel-dmarc-spf-dkim-setup-guide/)
- Tutorial completo de configuración

- **Mailjet - SPF, DKIM y DMARC**: [https://www.mailjet.com/es/blog/entregabilidad/spf-dkim-dmarc-como-configurar/](https://www.mailjet.com/es/blog/entregabilidad/spf-dkim-dmarc-como-configurar/)
- Explicación clara de por qué y cómo configurar

#### Alineación RFC 5322
- **PowerDMARC - DKIM RFC 5322 Alignment**: [https://powerdmarc.com/es/fix-dkim-rfc-5322-alignment/](https://powerdmarc.com/es/fix-dkim-rfc-5322-alignment/)
- Solución de problemas de alineación

- **DMARC.org - From Addresses**: [https://dmarc.org/2016/07/how-many-from-addresses-are-there/](https://dmarc.org/2016/07/how-many-from-addresses-are-there/)
- Diferencias entre 5321.From y 5322.From

- **Suped - 5321.from vs 5322.from**: [https://www.suped.com/knowledge/email-deliverability/technical/what-are-the-differences-between-5321from-and-5322from-in-email-headers](https://www.suped.com/knowledge/email-deliverability/technical/what-are-the-differences-between-5321from-and-5322from-in-email-headers)
- Explicación técnica detallada

### TLS/SSL

#### RFC 3207 - SMTP STARTTLS
- **IETF RFC 3207**: [https://www.ietf.org/rfc/rfc3207.txt](https://www.ietf.org/rfc/rfc3207.txt)
- Especificación de STARTTLS para SMTP

---

## 📧 Protocolos de Correo

### SMTP (Simple Mail Transfer Protocol)

#### RFC 5321 - SMTP Protocol
- **IETF RFC 5321**: [https://datatracker.ietf.org/doc/html/rfc5321](https://datatracker.ietf.org/doc/html/rfc5321)
- Especificación oficial del protocolo SMTP

#### Comandos y Códigos SMTP
- **Mailtrap - SMTP Commands and Responses**: [https://mailtrap.io/blog/smtp-commands-and-responses/](https://mailtrap.io/blog/smtp-commands-and-responses/)
- Guía completa de comandos SMTP

- **SamLogic - SMTP Commands Reference**: [https://www.samlogic.net/articles/smtp-commands-reference.htm](https://www.samlogic.net/articles/smtp-commands-reference.htm)
- Referencia de HELO, EHLO, MAIL, RCPT, DATA, etc.

#### Códigos de Error SMTP
- **SendPulse - Errores SMTP**: [https://sendpulse.com/latam/knowledge-base/smtp/smtp-errors-codes](https://sendpulse.com/latam/knowledge-base/smtp/smtp-errors-codes)
- Cómo arreglar errores comunes

- **Mailpro - Errores SMTP**: [https://es.mailpro.com/blog/errores-comunes-de-smtp](https://es.mailpro.com/blog/errores-comunes-de-smtp)
- Guía de solución de problemas

### RFC 5322 - Internet Message Format
- **IETF RFC 5322**: [https://datatracker.ietf.org/doc/html/rfc5322](https://datatracker.ietf.org/doc/html/rfc5322)
- Formato de mensajes de correo electrónico

### Comparativa de Protocolos
- **Suma Recursos - POP3, IMAP, SMTP**: [https://sumarecursos.com/blog/pop3-imap-smtp-guia-configuracion/amp/](https://sumarecursos.com/blog/pop3-imap-smtp-guia-configuracion/amp/)
- Guía clara para elegir y configurar

- **Mailpro - Diferencia SMTP, IMAP, POP3**: [https://es.mailpro.com/faq/diferencia-smtp-imap-pop3](https://es.mailpro.com/faq/diferencia-smtp-imap-pop3)
- Explicación de las diferencias

- **Arsys - Protocolos de correo**: [https://www.arsys.es/blog/principales-protocolos-de-correo-electronico-pop3-smtp-e-imap](https://www.arsys.es/blog/principales-protocolos-de-correo-electronico-pop3-smtp-e-imap)
- Artículo en español sobre los principales protocolos

---

## 🛡️ Antispam y Antivirus

### SpamAssassin
- **Apache SpamAssassin**: [https://spamassassin.apache.org/](https://spamassassin.apache.org/)
- Sitio oficial del proyecto

### ClamAV
- **ClamAV**: [https://www.clamav.net/](https://www.clamav.net/)
- Motor antivirus de código abierto

### Integración Amavis + SpamAssassin + ClamAV

- **Tecmint - Antivirus y Spam en Postfix**: [https://www.tecmint.com/integrate-clamav-and-spamassassin-to-protect-postfix-mails-from-viruses/](https://www.tecmint.com/integrate-clamav-and-spamassassin-to-protect-postfix-mails-from-viruses/)
- Tutorial completo de integración

- **EasyEngine - Amavis, SpamAssassin, ClamAV**: [https://easyengine.io/tutorials/mail/server/amavis-spamassassin-clamav/](https://easyengine.io/tutorials/mail/server/amavis-spamassassin-clamav/)
- Configuración paso a paso

- **LinuxBabe - Amavis y ClamAV en Ubuntu**: [https://www.linuxbabe.com/mail-server/postfix-amavis-spamassassin-clamav-ubuntu](https://www.linuxbabe.com/mail-server/postfix-amavis-spamassassin-clamav-ubuntu)
- Guía específica para Ubuntu

---

## 📖 Tutoriales Completos

### Configuración Completa de Servidor de Correo

#### Linode
- **How to Setup an Email Server**: [https://www.linode.com/docs/guides/how-to-setup-an-email-server/](https://www.linode.com/docs/guides/how-to-setup-an-email-server/)
- Tutorial profesional y completo

#### DigitalOcean
- **Configure Mail Server with Postfix, Dovecot, MySQL**: [https://www.digitalocean.com/community/tutorials/how-to-configure-a-mail-server-using-postfix-dovecot-mysql-and-spamassassin](https://www.digitalocean.com/community/tutorials/how-to-configure-a-mail-server-using-postfix-dovecot-mysql-and-spamassassin)
- Incluye usuarios virtuales con MySQL

#### Contabo
- **Servidor de correo en Linux**: [https://contabo.com/blog/es/como-configurar-un-servidor-de-correo-en-linux/](https://contabo.com/blog/es/como-configurar-un-servidor-de-correo-en-linux/)
- Tutorial en español

#### Civo
- **Setting up Postfix with Dovecot**: [https://www.civo.com/learn/setting-up-a-postfix-mail-server-with-dovecot](https://www.civo.com/learn/setting-up-a-postfix-mail-server-with-dovecot)
- Guía moderna y actualizada

#### Álvaro VF
- **Instalación servidor de correo**: [https://www.alvarovf.com/servicios/vps/2021/02/17/instalacion-servidor-correo.html](https://www.alvarovf.com/servicios/vps/2021/02/17/instalacion-servidor-correo.html)
- Tutorial en español, muy detallado

#### Alquimista de Sistemas
- **SASL, Postfixadmin, Dovecot y Filtros**: [https://alquimistadesistemas.com/instalar-sasl-postfixpostfixadmindovecot-y-filtros-de-spam-en-debian.html](https://alquimistadesistemas.com/instalar-sasl-postfixpostfixadmindovecot-y-filtros-de-spam-en-debian.html)
- Configuración avanzada en español

#### Lynksthings
- **Servidor de correo: Postfix y Dovecot**: [https://www.lynksthings.com/posts/sysadmin/mailserver-postfix_dovecot/](https://www.lynksthings.com/posts/sysadmin/mailserver-postfix_dovecot/)
- Guía práctica y concisa

#### CloudSigma
- **Mail Server Configuration Tutorial**: [https://blog.cloudsigma.com/mail-server-configuration-tutorial-how-to-use-postfix-dovecot-mysql-and-spamassassin/](https://blog.cloudsigma.com/mail-server-configuration-tutorial-how-to-use-postfix-dovecot-mysql-and-spamassassin/)
- Tutorial profesional completo

#### Hetman Recovery
- **Postfix con Dovecot en Ubuntu**: [https://hetmanrecovery.com/es/blog/how-to-install-and-configure-postfix-mail-server-with-dovecot-on-linux-ubuntu.htm](https://hetmanrecovery.com/es/blog/how-to-install-and-configure-postfix-mail-server-with-dovecot-on-linux-ubuntu.htm)
- En español, muy detallado

### Configuración con Usuarios Virtuales

#### ArchWiki
- **Virtual User Mail System**: [https://wiki.archlinux.org/title/Virtual_user_mail_system_with_Postfix,_Dovecot_and_Roundcube](https://wiki.archlinux.org/title/Virtual_user_mail_system_with_Postfix,_Dovecot_and_Roundcube)
- Incluye Roundcube (webmail)

- **Postfix (Español)**: [https://wiki.archlinux.org/title/Postfix_(Espa%C3%B1ol)](https://wiki.archlinux.org/title/Postfix_(Espa%C3%B1ol))
- Documentación en español

### Guías Específicas

#### GitHub Gist
- **Postfix + Dovecot con SPF, DKIM, DMARC**: [https://gist.github.com/howyay/57982e6ba9eedd3a5662c518f1b985c7](https://gist.github.com/howyay/57982e6ba9eedd3a5662c518f1b985c7)
- Configuración completa de seguridad

#### Rigacci.org
- **Postfix, SpamAssassin, ClamAV, Dovecot**: [https://rigacci.org/wiki/doku.php/doc/appunti/linux/sa/postfix_spamassassin_clamav_dovecot](https://rigacci.org/wiki/doku.php/doc/appunti/linux/sa/postfix_spamassassin_clamav_dovecot)
- Guía técnica avanzada

#### Sysadblog
- **Ejercicios con Postfix**: [https://sysadblog.onrender.com/posts/ejercicios_con_postfix/](https://sysadblog.onrender.com/posts/ejercicios_con_postfix/)
- Prácticas y ejercicios

---

## 🔍 Troubleshooting y Resolución de Problemas

### Postfix

- **Linode - Troubleshooting Postfix, Dovecot, MySQL**: [https://www.linode.com/docs/guides/troubleshooting-problems-with-postfix-dovecot-and-mysql/](https://www.linode.com/docs/guides/troubleshooting-problems-with-postfix-dovecot-and-mysql/)
- Solución de problemas comunes

- **Server Fault - Postfix MySQL Unknown User**: [https://serverfault.com/questions/418766/postfix-mysql-unknown-user-error](https://serverfault.com/questions/418766/postfix-mysql-unknown-user-error)
- Error específico con usuarios virtuales

### Dovecot

- **VADOSWARE - Issues with Thunderbird and Dovecot**: [https://vadosware.io/post/issues-with-thunderbird-and-dovecot/](https://vadosware.io/post/issues-with-thunderbird-and-dovecot/)
- Problemas de compatibilidad

- **HubSpot - Troubleshoot IMAP Connection**: [https://knowledge.hubspot.com/es/connected-email/troubleshoot-imap-inbox-connection](https://knowledge.hubspot.com/es/connected-email/troubleshoot-imap-inbox-connection)
- Solucionar errores de conexión IMAP

### SASL

- **Server Fault - Postfix Dovecot SASL Configuration**: [https://serverfault.com/questions/416270/what-is-wrong-in-my-postfix-dovecot-sasl-configuration](https://serverfault.com/questions/416270/what-is-wrong-in-my-postfix-dovecot-sasl-configuration)
- Problemas de configuración SASL

- **Unix StackExchange - No SASL Authentication Mechanisms**: [https://unix.stackexchange.com/questions/763565/ubuntu-server-22-04-postfix-dovecot-error-postfix-smtpd-fatal-no-sasl-authenti](https://unix.stackexchange.com/questions/763565/ubuntu-server-22-04-postfix-dovecot-error-postfix-smtpd-fatal-no-sasl-authenti)
- Error fatal de SASL en Ubuntu 22.04

### DMARC

- **Google Workspace - Solucionar problemas DMARC**: [https://support.google.com/a/answer/10032578?hl=es-419](https://support.google.com/a/answer/10032578?hl=es-419)
- Guía oficial de Google

- **WordPress - DMARC RFC 5322/5321 Alignment**: [https://wordpress.org/support/topic/dmard-having-both-and-identical-rfc-5322-from-address-and-rfc-5321-from-address/](https://wordpress.org/support/topic/dmard-having-both-and-identical-rfc-5322-from-address-and-rfc-5321-from-address/)
- Problema de alineación

- **Easy365Manager - RFC 5321 and RFC 5322**: [https://www.easy365manager.com/rfc-5321-and-rfc-5322/](https://www.easy365manager.com/rfc-5321-and-rfc-5322/)
- Entender DKIM y SPF

---

## 📊 Comparativas y Análisis

### Postfix vs Dovecot
- **DEV Community - Postfix vs Dovecot**: [https://dev.to/shrsv/postfix-vs-dovecot-key-differences-for-building-email-systems-55k2](https://dev.to/shrsv/postfix-vs-dovecot-key-differences-for-building-email-systems-55k2)
- Diferencias clave entre ambos

---

## 🎥 Recursos Multimedia Complementarios

### Videos Recomendados en YouTube

Estos videos complementan el material escrito:

- **Configuración Postfix-Dovecot**: [https://www.youtube.com/watch?v=EduZ1nbjvcs](https://www.youtube.com/watch?v=EduZ1nbjvcs)
- **Servidor de correo completo**: [https://www.youtube.com/watch?v=KqHiLGgaoIQ](https://www.youtube.com/watch?v=KqHiLGgaoIQ)
- **Dominando el correo en Ubuntu**: [https://www.youtube.com/watch?v=XJapmlmHqqc](https://www.youtube.com/watch?v=XJapmlmHqqc)

---

## 🛠️ Herramientas Online

### Verificación y Testing

- **MXToolbox**: [https://mxtoolbox.com/](https://mxtoolbox.com/)
  - Verificación completa de configuración de correo
  - Comprobación de registros DNS
  - Test de listas negras (blacklists)

- **Mail-tester**: [https://www.mail-tester.com/](https://www.mail-tester.com/)
  - Puntuación de spam de tus correos
  - Análisis de autenticación
  - Recomendaciones de mejora

- **DMARC Analyzer**: [https://www.dmarcanalyzer.com/](https://www.dmarcanalyzer.com/)
  - Análisis de reportes DMARC
  - Monitorización de autenticación

---

## 📝 Cómo Usar Esta Documentación

### Para Estudio Inicial
1. Comienza con los **tutoriales completos** (Linode, DigitalOcean)
2. Lee las **especificaciones RFC** de los protocolos principales
3. Consulta las **guías oficiales** de Postfix y Dovecot

### Durante la Configuración
1. Ten abierta la **referencia de parámetros** de Postfix
2. Consulta los **ejemplos de configuración estándar**
3. Usa las **guías de integración** SASL y TLS

### Para Resolución de Problemas
1. Revisa las secciones de **troubleshooting**
2. Busca en **Server Fault** y **Stack Exchange**
3. Verifica con **herramientas online**

### Para Profundizar
1. Lee los **RFCs completos**
2. Estudia las **guías avanzadas** (usuarios virtuales, clustering)
3. Experimenta con **diferentes configuraciones**

---

## 🔖 Marcadores Recomendados

Guarda estos enlaces en tu navegador para acceso rápido:

1. **Postfix Configuration Parameters**: Para consultas rápidas de parámetros
2. **Dovecot Wiki**: Para configuración de autenticación
3. **MXToolbox**: Para verificar tu configuración
4. **RFC 5321 (SMTP)**: Para entender el protocolo
5. **DMARC.org**: Para implementar autenticación

---

**Última actualización**: Febrero 2026  
**Mantenido por**: Módulo SRI - ASIR

> **Nota**: Todos estos enlaces han sido verificados y son recursos oficiales o de alta calidad técnica. Si encuentras algún enlace roto, por favor repórtalo al profesor.
