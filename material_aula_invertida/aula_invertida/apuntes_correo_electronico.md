# Administración Avanzada de Servicios de Correo Electrónico

## 📚 Introducción

El correo electrónico es uno de los servicios más críticos en cualquier infraestructura de red empresarial. Como administrador de sistemas, debes dominar no solo la instalación de servidores de correo, sino también comprender los protocolos, la seguridad y los mecanismos de autenticación que garantizan la entregabilidad y protección contra amenazas.

## 🎯 Objetivos de Aprendizaje

Al finalizar este tema, serás capaz de:

- Identificar y configurar los agentes MUA, MTA y MDA
- Comprender el diálogo SMTP y sus extensiones
- Configurar servidores Postfix y Dovecot
- Implementar registros de autenticación SPF, DKIM y DMARC
- Diagnosticar problemas comunes en servicios de correo

## 📧 Arquitectura del Correo Electrónico

### Modelo Store-and-Forward

A diferencia de la mensajería instantánea, el correo electrónico funciona mediante un modelo de **almacenamiento y reenvío**. Esto significa que los mensajes se entregan incluso si el destinatario no está en línea, gracias a la persistencia en servidores intermedios.

### Los Tres Agentes Fundamentales

#### 1. Mail User Agent (MUA)
- **Función**: Interfaz con el usuario final
- **Ejemplos**: Microsoft Outlook, Mozilla Thunderbird, Mutt, Alpine
- **Responsabilidades**:
  - Composición de mensajes
  - Gestión del buzón local
  - Interacción con protocolos de recuperación (POP3/IMAP)

#### 2. Mail Transport Agent (MTA)
- **Función**: Enrutamiento de mensajes entre servidores
- **Ejemplos**: Postfix, Exim, Sendmail
- **Responsabilidades**:
  - Actuar como cliente y servidor SMTP
  - Consultar registros MX del DNS
  - Decidir si entregar localmente o reenviar

#### 3. Mail Delivery Agent (MDA)
- **Función**: Entrega final al buzón del usuario
- **Ejemplos**: Dovecot, Procmail
- **Responsabilidades**:
  - Depositar mensajes en Maildir o mbox
  - Aplicar filtros de entrada
  - Organizar el correo antes de la consulta

#### 4. Mail Submission Agent (MSA)
- **Función**: Recepción de correos desde clientes locales
- **Puerto**: 587 (con autenticación obligatoria)
- **Característica**: Exige autenticación antes del relevo

## 🔌 Protocolos Esenciales

### SMTP (Simple Mail Transfer Protocol)

**Puerto estándar**: 25 (MTA a MTA)  
**Puerto submission**: 587 (MUA a MTA con autenticación)  
**Puerto SMTPS**: 465 (SSL/TLS implícito)

#### Diálogo SMTP Básico

```
Cliente: EHLO mail.emisor.com
Servidor: 250-mail.receptor.com
Servidor: 250-STARTTLS
Servidor: 250 AUTH PLAIN LOGIN

Cliente: MAIL FROM:<usuario@emisor.com>
Servidor: 250 OK

Cliente: RCPT TO:<destino@receptor.com>
Servidor: 250 OK

Cliente: DATA
Servidor: 354 End data with <CR><LF>.<CR><LF>

Cliente: Subject: Prueba
Cliente: 
Cliente: Contenido del mensaje
Cliente: .
Servidor: 250 Message accepted

Cliente: QUIT
Servidor: 221 Bye
```

#### Códigos de Respuesta SMTP Importantes

| Código | Significado | Descripción |
|--------|-------------|-------------|
| 220 | Servicio listo | El servidor está preparado |
| 250 | Acción completada | Comando ejecutado con éxito |
| 354 | Inicio de entrada de datos | Listo para recibir el mensaje |
| 421 | Servicio no disponible | Error temporal, reintentar |
| 550 | Buzón no disponible | Error permanente, no reintentar |

### POP3 (Post Office Protocol v3)

**Puerto**: 110 (sin cifrar)  
**Puerto seguro**: 995 (SSL/TLS)

**Características**:
- Descarga mensajes al cliente
- Por defecto, elimina del servidor
- Ideal para un solo dispositivo
- Almacenamiento local en el cliente

### IMAP (Internet Message Access Protocol)

**Puerto**: 143 (sin cifrar)  
**Puerto seguro**: 993 (SSL/TLS)

**Características**:
- Sincronización bidireccional
- Mensajes permanecen en el servidor
- Soporte para múltiples dispositivos
- Gestión de carpetas en el servidor

## 🌐 El Rol Crítico del DNS

### Registros MX (Mail Exchanger)

Los registros MX especifican qué servidores reciben correo para un dominio:

```
ejemplo.com.    IN  MX  10  mail1.ejemplo.com.
ejemplo.com.    IN  MX  20  mail2.ejemplo.com.
```

- **Prioridad**: Número más bajo = mayor prioridad
- **Función**: Indica dónde entregar el correo para un dominio

### Registros PTR (Resolución Inversa)

```
5.113.0.203.in-addr.arpa.  IN  PTR  mail.ejemplo.com.
```

**Importancia**: Muchos servidores rechazan correos de IPs sin resolución inversa válida.

## 🔐 Seguridad y Autenticación

### SPF (Sender Policy Framework)

**Registro DNS TXT** que autoriza qué servidores pueden enviar correo por tu dominio:

```
ejemplo.com.  IN  TXT  "v=spf1 ip4:203.0.113.5 mx -all"
```

**Calificadores**:
- `+all` - Permitir todo (¡NUNCA usar!)
- `-all` - Fallo estricto (rechazar)
- `~all` - SoftFail (marcar pero no rechazar)
- `?all` - Neutral

### DKIM (DomainKeys Identified Mail)

**Firma criptográfica** en las cabeceras del mensaje:

1. El servidor emisor firma el mensaje con clave privada
2. Publica la clave pública en DNS
3. El receptor verifica la firma

**Registro DNS**:
```
selector._domainkey.ejemplo.com.  IN  TXT  "v=DKIM1; k=rsa; p=MIGfMA0GCS..."
```

### DMARC (Domain-based Message Authentication)

**Unifica SPF y DKIM** proporcionando políticas claras:

```
_dmarc.ejemplo.com.  IN  TXT  "v=DMARC1; p=reject; rua=mailto:admin@ejemplo.com"
```

**Políticas**:
- `p=none` - Solo monitorear
- `p=quarantine` - Marcar como spam
- `p=reject` - Rechazar completamente

**Alineación**: El dominio en `From:` debe coincidir con el validado por SPF/DKIM.

## ⚙️ Configuración de Postfix

### Instalación en Debian/Ubuntu

```bash
sudo apt update
sudo apt install postfix bsd-mailx
```

**Modo recomendado**: "Sitio de Internet"

### Archivo `/etc/postfix/main.cf`

Parámetros críticos:

```conf
# Identidad del servidor
myhostname = mail.ejemplo.com
mydomain = ejemplo.com
myorigin = $mydomain

# Dominios para entrega local
mydestination = $myhostname, localhost.$mydomain, localhost, $mydomain

# Redes autorizadas para relay sin autenticación
mynetworks = 127.0.0.0/8, 192.168.10.0/24

# Restricciones de relay
smtpd_recipient_restrictions = 
    permit_mynetworks,
    permit_sasl_authenticated,
    reject_unauth_destination

# Tamaño máximo de mensaje (10MB)
message_size_limit = 10485760
```

### Archivo `/etc/postfix/master.cf`

Habilitar submission (puerto 587):

```conf
submission inet n       -       y       -       -       smtpd
  -o syslog_name=postfix/submission
  -o smtpd_tls_security_level=encrypt
  -o smtpd_sasl_auth_enable=yes
  -o smtpd_recipient_restrictions=permit_sasl_authenticated,reject
```

### Comandos Útiles de Postfix

```bash
# Verificar configuración
postfix check

# Recargar configuración
sudo systemctl reload postfix

# Ver cola de correo
postqueue -p

# Eliminar un mensaje de la cola
postsuper -d [ID_MENSAJE]

# Forzar envío de cola
postqueue -f

# Convertir archivo de texto a base de datos
postmap /etc/postfix/virtual
```

## 📬 Configuración de Dovecot

### Instalación

```bash
sudo apt install dovecot-imapd dovecot-pop3d
```

### Archivo `/etc/dovecot/conf.d/10-mail.conf`

```conf
# Ubicación y formato de buzones
mail_location = maildir:~/Maildir
```

### Formatos de Almacenamiento

#### mbox
- **Estructura**: Un archivo único por buzón
- **Problemas**: Bloqueo de archivos, corrupción en buzones grandes
- **Uso**: Sistemas legacy

#### Maildir
- **Estructura**: Un archivo por mensaje
- **Ventajas**: Sin bloqueo, mejor rendimiento, más fiable
- **Uso**: Recomendado para sistemas modernos

### Autenticación SASL con Postfix

Dovecot proporciona autenticación para Postfix:

**`/etc/dovecot/conf.d/10-master.conf`**:
```conf
service auth {
  unix_listener /var/spool/postfix/private/auth {
    mode = 0660
    user = postfix
    group = postfix
  }
}
```

**En Postfix `/etc/postfix/main.cf`**:
```conf
smtpd_sasl_type = dovecot
smtpd_sasl_path = private/auth
smtpd_sasl_auth_enable = yes
```

## 🔒 Cifrado con TLS

### Generar Certificado con Let's Encrypt

```bash
sudo apt install certbot
sudo certbot certonly --standalone -d mail.ejemplo.com
```

### Configurar TLS en Postfix

```conf
# Certificados
smtpd_tls_cert_file = /etc/letsencrypt/live/mail.ejemplo.com/fullchain.pem
smtpd_tls_key_file = /etc/letsencrypt/live/mail.ejemplo.com/privkey.pem

# Nivel de seguridad
smtpd_tls_security_level = may
smtp_tls_security_level = may

# Habilitar TLS
smtpd_use_tls = yes
smtp_use_tls = yes
```

### Configurar TLS en Dovecot

```conf
ssl = yes
ssl_cert = </etc/letsencrypt/live/mail.ejemplo.com/fullchain.pem
ssl_key = </etc/letsencrypt/live/mail.ejemplo.com/privkey.pem
```

## 🛡️ Protección contra Spam

### SpamAssassin

**Análisis bayesiano** de contenido:

```bash
sudo apt install spamassassin spamc
```

Integración con Postfix mediante filtro de contenido.

### ClamAV + Amavis

**Escaneo de virus** en adjuntos:

```bash
sudo apt install clamav clamav-daemon amavisd-new
```

Amavis coordina el escaneo antes de la entrega final.

### Greylisting

**Técnica**: Rechazar temporalmente correos de remitentes desconocidos.

**Efecto**: Servidores legítimos reintentarán, spammers generalmente no.

## 🚨 Errores Comunes y Soluciones

### 1. Open Relay

**Problema**: Servidor permite relay a cualquiera  
**Solución**: Configurar correctamente `smtpd_recipient_restrictions`

```conf
smtpd_recipient_restrictions = 
    permit_mynetworks,
    permit_sasl_authenticated,
    reject_unauth_destination
```

### 2. Correos Rechazados por Gmail

**Error**: `550-5.7.26 This message does not have authentication information`

**Solución**:
1. Implementar registro SPF
2. Configurar DKIM con OpenDKIM
3. Crear política DMARC

### 3. Puerto Bloqueado por Firewall

**Diagnóstico**:
```bash
sudo nmap localhost
sudo ufw status
```

**Solución**:
```bash
sudo ufw allow 25/tcp
sudo ufw allow 587/tcp
sudo ufw allow 993/tcp
```

### 4. Problemas de Permisos en Maildir

**Error**: Dovecot no puede escribir en buzones

**Solución**:
```bash
sudo chown -R vmail:vmail /var/mail/vmail
sudo chmod -R 700 /var/mail/vmail
```

## 📊 Monitorización y Diagnóstico

### Logs del Sistema

```bash
# Ver logs en tiempo real
sudo tail -f /var/log/mail.log

# Buscar un mensaje específico
sudo grep "ID_MENSAJE" /var/log/mail.log

# Ver errores recientes
sudo grep "error" /var/log/mail.log | tail -20
```

### Herramientas de Diagnóstico

```bash
# Probar conexión SMTP
telnet mail.ejemplo.com 25

# Verificar registros MX
dig MX ejemplo.com

# Verificar registro SPF
dig TXT ejemplo.com

# Verificar DKIM
dig TXT selector._domainkey.ejemplo.com

# Verificar DMARC
dig TXT _dmarc.ejemplo.com
```

### Herramientas Online

- **MXToolbox**: Verificación completa de configuración de correo
- **Mail-tester**: Puntuación de spam de tus correos
- **DMARC Analyzer**: Análisis de reportes DMARC

## 📝 Gestión de Usuarios

### Aliases

**Archivo**: `/etc/aliases`

```
postmaster: root
webmaster: root
admin: usuario1,usuario2
soporte: ticket-system@ejemplo.com
```

**Aplicar cambios**:
```bash
sudo newaliases
```

### Usuarios Virtuales con MySQL

Para entornos con miles de usuarios:

```sql
CREATE DATABASE mailserver;
CREATE TABLE virtual_users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    email VARCHAR(255) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL,
    domain VARCHAR(255) NOT NULL
);
```

Configurar Postfix para consultar la base de datos.

## 🌐 Webmail con Roundcube

### Instalación

```bash
sudo apt install roundcube roundcube-plugins
```

### Características

- Interfaz web moderna
- Cliente IMAP completo
- Acceso desde cualquier navegador
- Gestión de contactos y calendario

## ✅ Checklist de Configuración

- [ ] Servidor instalado y funcionando
- [ ] Hostname configurado correctamente (`hostname -f`)
- [ ] Registros DNS configurados (MX, A, PTR)
- [ ] Certificados SSL/TLS instalados
- [ ] Autenticación SASL funcionando
- [ ] Registro SPF publicado
- [ ] DKIM configurado y firmando
- [ ] Política DMARC definida
- [ ] Firewall configurado (puertos abiertos)
- [ ] Antispam y antivirus activos
- [ ] Logs monitorizados
- [ ] Backups configurados

## 🎓 Conceptos Clave para Recordar

1. **Envelope vs Headers**: El "sobre" (MAIL FROM) es diferente de las cabeceras visibles (From:)
2. **Cadena de Confianza**: DNS → TLS → SASL → SPF/DKIM/DMARC
3. **Never Open Relay**: Siempre usar `reject_unauth_destination`
4. **Maildir > mbox**: Para sistemas modernos
5. **Puerto 587**: Para submission con autenticación
6. **Alineación DMARC**: El dominio visible debe coincidir con el autenticado

## 📚 Recursos Adicionales

### RFCs Importantes

- **RFC 5321**: SMTP Protocol
- **RFC 5322**: Internet Message Format
- **RFC 3207**: SMTP STARTTLS
- **RFC 7208**: SPF
- **RFC 6376**: DKIM
- **RFC 7489**: DMARC

### Comandos de Referencia Rápida

```bash
# Postfix
postfix check          # Verificar configuración
postconf -n            # Ver configuración activa
postqueue -p           # Ver cola
mailq                  # Alias de postqueue -p
postsuper -d ALL       # Vaciar cola

# Dovecot
doveconf -n            # Ver configuración activa
doveadm user lista     # Listar usuarios
doveadm mailbox list -u usuario  # Listar buzones

# Testing
echo "Test" | mail -s "Asunto" destino@ejemplo.com
telnet localhost 25
openssl s_client -connect mail.ejemplo.com:587 -starttls smtp
```

## 🔍 Práctica Recomendada

Antes de la clase presencial:

1. **Ver el video** proporcionado (enlace en el material)
2. **Leer estos apuntes** completos
3. **Intentar instalar** Postfix y Dovecot en una VM
4. **Anotar dudas** específicas para resolver en clase
5. **Probar comandos** básicos de diagnóstico

En clase trabajaremos en:

- Configuración avanzada de seguridad
- Resolución de problemas reales
- Integración con otros servicios
- Casos prácticos empresariales

---

**Última actualización**: Febrero 2026  
**Módulo**: Servicios de Red e Internet (SRI)  
**Ciclo**: ASIR - Administración de Sistemas Informáticos en Red
