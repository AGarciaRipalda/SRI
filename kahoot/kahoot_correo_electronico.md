# Kahoot - Administración Avanzada de Servicios de Correo Electrónico

## Banco de Preguntas Técnicas para Kahoot

Este documento contiene 50 preguntas técnicas diseñadas para evaluar la comprensión profunda de los mecanismos de correo electrónico. Cada pregunta incluye 4 opciones de respuesta y una explicación técnica detallada.

---

### Pregunta 1
**¿Qué agente es responsable de enrutar mensajes entre servidores?**

- A) MUA (Mail User Agent)
- B) MTA (Mail Transport Agent) ✓
- C) MDA (Mail Delivery Agent)
- D) MSA (Mail Submission Agent)

**Explicación**: El MTA (Mail Transport Agent) utiliza el protocolo SMTP para mover el correo a través de las redes entre diferentes servidores. Software como Postfix o Exim actúan como MTAs.

---

### Pregunta 2
**¿Cuál es el puerto estándar para SMTP Submission (MUA a MTA)?**

- A) 25
- B) 465
- C) 587 ✓
- D) 993

**Explicación**: El puerto 587 se prefiere para el envío de clientes (submission) con autenticación obligatoria. El puerto 25 es para tráfico MTA a MTA, y 465 es SMTPS (SSL implícito).

---

### Pregunta 3
**¿Qué registro DNS especifica el servidor de correo de un dominio?**

- A) A (Address)
- B) MX (Mail Exchanger) ✓
- C) PTR (Pointer)
- D) CNAME (Canonical Name)

**Explicación**: Los registros MX indican la prioridad y el host receptor del dominio. Sin registros MX correctos, el correo no puede ser entregado.

---

### Pregunta 4
**¿Qué protocolo sincroniza las carpetas del servidor con el cliente?**

- A) SMTP
- B) POP3
- C) IMAP ✓
- D) HTTP

**Explicación**: IMAP (Internet Message Access Protocol) permite mantener la estructura de carpetas en el servidor de forma persistente y sincronizada entre múltiples dispositivos.

---

### Pregunta 5
**¿Qué comando SMTP inicia la transferencia del contenido del correo?**

- A) MAIL FROM
- B) RCPT TO
- C) DATA ✓
- D) EHLO

**Explicación**: Tras el comando DATA, el servidor espera las cabeceras y el cuerpo del mensaje, finalizando con un punto (.) en una línea solitaria.

---

### Pregunta 6
**¿Qué significa el código de respuesta SMTP 550?**

- A) Servicio listo
- B) Acción completada
- C) Buzón no disponible / Acceso denegado ✓
- D) Servicio no disponible temporalmente

**Explicación**: El código 550 es un error permanente que indica que la transacción no puede completarse, típicamente porque el buzón no existe o el acceso está denegado.

---

### Pregunta 7
**¿Qué registro SPF indica un "SoftFail" si la IP no está autorizada?**

- A) -all
- B) ~all ✓
- C) +all
- D) ?all

**Explicación**: La tilde (~) en "~all" indica que el correo debe marcarse como sospechoso pero no necesariamente rechazarse. Es menos estricto que "-all".

---

### Pregunta 8
**¿En qué archivo de Postfix se habilitan servicios como smtps o submission?**

- A) main.cf
- B) master.cf ✓
- C) aliases
- D) virtual

**Explicación**: El archivo master.cf controla los demonios individuales de Postfix y los puertos en los que escuchan. main.cf controla el comportamiento global.

---

### Pregunta 9
**¿Qué extensión permite enviar archivos binarios por correo?**

- A) SMTP
- B) MIME ✓
- C) ASCII
- D) UTF-8

**Explicación**: MIME (Multipurpose Internet Mail Extensions) codifica datos no textuales (imágenes, videos, etc.) en formato ASCII para su transmisión por correo electrónico.

---

### Pregunta 10
**¿Qué herramienta se usa para generar firmas DKIM en Postfix?**

- A) SpamAssassin
- B) OpenDKIM ✓
- C) ClamAV
- D) Amavis

**Explicación**: OpenDKIM es el software estándar para implementar firmas criptográficas DKIM en el flujo de correo de Postfix.

---

### Pregunta 11
**¿Qué protocolo de acceso descarga los correos y suele borrarlos del servidor?**

- A) SMTP
- B) IMAP
- C) POP3 ✓
- D) LMTP

**Explicación**: POP3 (Post Office Protocol v3) está diseñado para almacenamiento local en el cliente del usuario, descargando y típicamente eliminando los mensajes del servidor.

---

### Pregunta 12
**¿Cuál es el puerto estándar de IMAP cifrado con SSL/TLS (IMAPS)?**

- A) 143
- B) 993 ✓
- C) 995
- D) 587

**Explicación**: IMAPS proporciona una capa de seguridad implícita sobre el puerto 993. El puerto 143 es IMAP sin cifrar.

---

### Pregunta 13
**¿Qué directiva de Postfix define qué dominios se entregan localmente?**

- A) myhostname
- B) mynetworks
- C) mydestination ✓
- D) relayhost

**Explicación**: La directiva mydestination evita que el servidor intente reenviar al exterior correos que debe procesar él mismo localmente.

---

### Pregunta 14
**¿Qué comando SMTP se usa para finalizar la conexión?**

- A) EXIT
- B) CLOSE
- C) QUIT ✓
- D) BYE

**Explicación**: El comando QUIT indica al servidor que la sesión ha terminado y puede cerrar el socket TCP.

---

### Pregunta 15
**¿Qué es un "Open Relay"?**

- A) Un servidor muy rápido
- B) Un servidor que permite reenviar correo a cualquiera ✓
- C) Un servidor con cifrado
- D) Un servidor con autenticación

**Explicación**: Un Open Relay es una vulnerabilidad grave que permite a spammers usar el servidor para enviar correo masivo, resultando en inclusión en listas negras.

---

### Pregunta 16
**¿Qué registro DNS asocia una IP con un nombre de dominio (inversa)?**

- A) A
- B) MX
- C) PTR ✓
- D) TXT

**Explicación**: El registro PTR es fundamental para que los receptores confíen en la identidad del servidor emisor mediante resolución DNS inversa.

---

### Pregunta 17
**¿Qué protocolo añade una capa de autenticación a SMTP e IMAP?**

- A) TLS
- B) SSL
- C) SASL ✓
- D) OAuth

**Explicación**: SASL (Simple Authentication and Security Layer) permite negociar mecanismos de seguridad como contraseñas cifradas o tokens de autenticación.

---

### Pregunta 18
**¿Cuál es la principal ventaja de Maildir sobre mbox?**

- A) Ocupa menos espacio
- B) Es más rápido
- C) No requiere bloqueo de archivos (locking) ✓
- D) Es más antiguo

**Explicación**: Al usar archivos individuales por correo, Maildir evita la corrupción de buzones grandes y los problemas de bloqueo concurrente.

---

### Pregunta 19
**¿Qué tag de DMARC indica la dirección para informes agregados?**

- A) ruf
- B) rua ✓
- C) p
- D) sp

**Explicación**: El tag "rua" (rua=mailto:admin@dominio.com) permite recibir estadísticas diarias agregadas de fallos de autenticación.

---

### Pregunta 20
**¿Qué motor de filtrado usa reglas bayesianas para detectar spam?**

- A) ClamAV
- B) Amavis
- C) SpamAssassin ✓
- D) Postfix

**Explicación**: SpamAssassin analiza patrones estadísticos y asigna una puntuación de probabilidad de que el mensaje sea basura (spam).

---

### Pregunta 21
**¿Qué significa el código SMTP 250?**

- A) Error temporal
- B) Acción completada correctamente ✓
- C) Buzón lleno
- D) Conexión rechazada

**Explicación**: El código 250 es la confirmación de éxito de casi cualquier comando SMTP (MAIL FROM, RCPT TO, DATA, etc.).

---

### Pregunta 22
**¿Qué puerto usa POP3 de forma segura (SSL/TLS)?**

- A) 110
- B) 995 ✓
- C) 993
- D) 465

**Explicación**: El puerto 995 proporciona POP3 con cifrado SSL/TLS implícito para la descarga segura de mensajes.

---

### Pregunta 23
**¿Qué cabecera técnica rastrea cada salto de un correo?**

- A) From
- B) To
- C) Received ✓
- D) Subject

**Explicación**: Los MTAs añaden la cabecera "Received" con su IP y marca de tiempo en cada salto, permitiendo rastrear la ruta completa del mensaje.

---

### Pregunta 24
**¿Qué comando se usa en Debian para refrescar los aliases de correo?**

- A) postfix reload
- B) newaliases ✓
- C) postmap
- D) postqueue

**Explicación**: El comando "newaliases" convierte el archivo /etc/aliases de texto plano en una base de datos binaria indexada para Postfix.

---

### Pregunta 25
**¿Qué es el "Greylisting"?**

- A) Filtro de virus
- B) Rechazo temporal de correos de remitentes desconocidos ✓
- C) Lista negra permanente
- D) Cifrado de mensajes

**Explicación**: Greylisting obliga a los servidores legítimos a reintentar el envío, mientras que los spammers suelen desistir tras el primer rechazo temporal.

---

### Pregunta 26
**¿Qué estándar protege el cuerpo del mensaje de ser alterado?**

- A) SPF
- B) DKIM ✓
- C) DMARC
- D) TLS

**Explicación**: DKIM (DomainKeys Identified Mail) crea una firma criptográfica que cubre las cabeceras críticas y el cuerpo del mensaje.

---

### Pregunta 27
**¿Qué protocolo usa Mailman para hablar con Postfix?**

- A) SMTP
- B) IMAP
- C) LMTP ✓
- D) POP3

**Explicación**: LMTP (Local Mail Transfer Protocol) es una versión optimizada de SMTP para entregas locales a aplicaciones como Mailman.

---

### Pregunta 28
**¿Cuál es la política DMARC más estricta?**

- A) p=none
- B) p=quarantine
- C) p=reject ✓
- D) p=monitor

**Explicación**: La política "p=reject" instruye al receptor a descartar totalmente el correo si falla la autenticación SPF o DKIM.

---

### Pregunta 29
**¿Qué comando SMTP permite verificar si existe un usuario en el sistema?**

- A) EXPN
- B) VRFY ✓
- C) RCPT
- D) MAIL

**Explicación**: VRFY (verify) permite verificar usuarios, pero por seguridad suele estar deshabilitado para evitar recolección de direcciones por atacantes.

---

### Pregunta 30
**¿Qué puerto usa SMTP para transporte entre servidores (sin cifrado obligatorio)?**

- A) 25 ✓
- B) 465
- C) 587
- D) 993

**Explicación**: El puerto 25 es el puerto por defecto para el tráfico de red de correo global entre MTAs.

---

### Pregunta 31
**¿Qué directiva de Dovecot especifica dónde se guardan los correos?**

- A) mail_home
- B) mail_location ✓
- C) mail_path
- D) mail_dir

**Explicación**: La directiva "mail_location" define la ruta y el formato (Maildir:~/Maildir o mbox:~/mail) donde se almacenan los mensajes.

---

### Pregunta 32
**¿Qué es un MUA?**

- A) Mail Transfer Agent
- B) Mail User Agent ✓
- C) Mail Utility Application
- D) Mail Universal Access

**Explicación**: MUA (Mail User Agent) es la aplicación cliente (Thunderbird, Outlook, Mutt) que usa el destinatario para leer y componer correos.

---

### Pregunta 33
**¿Qué comando IMAP permite leer solo la cabecera de un mensaje?**

- A) GET
- B) READ
- C) FETCH ✓
- D) RETRIEVE

**Explicación**: El comando FETCH de IMAP permite optimizar el ancho de banda descargando solo las cabeceras o partes específicas del mensaje.

---

### Pregunta 34
**¿Qué significa el código SMTP 421?**

- A) Acción completada
- B) El servicio no está disponible temporalmente ✓
- C) Buzón no encontrado
- D) Autenticación requerida

**Explicación**: El código 421 indica un problema temporal en el servidor receptor que sugiere reintentar el envío más tarde.

---

### Pregunta 35
**¿Qué registro DNS es necesario para validar la firma DKIM?**

- A) Registro A
- B) Registro MX
- C) Registro TXT con la clave pública ✓
- D) Registro PTR

**Explicación**: El selector y el dominio forman el nombre del host DNS donde se publica la clave pública DKIM en un registro TXT.

---

### Pregunta 36
**¿Qué es el "Envelope From"?**

- A) La dirección visible en el cliente
- B) El remitente declarado en MAIL FROM ✓
- C) El asunto del mensaje
- D) La fecha de envío

**Explicación**: El "Envelope From" es el remitente declarado en el comando SMTP MAIL FROM, usado para notificaciones de rebote (bounce).

---

### Pregunta 37
**¿Qué demonio de Postfix gestiona la cola de correo?**

- A) smtpd
- B) qmgr ✓
- C) cleanup
- D) master

**Explicación**: El Queue Manager (qmgr) decide cuándo y cómo se procesan los mensajes en espera en la cola de Postfix.

---

### Pregunta 38
**¿Qué herramienta de Linux permite enviar correos desde la terminal?**

- A) sendmail
- B) mail / mailx ✓
- C) telnet
- D) curl

**Explicación**: "mail" o "mailx" son MUAs básicos de línea de comandos útiles para scripts y pruebas rápidas.

---

### Pregunta 39
**¿Qué cifrado se inicia en el puerto 25 para subir el nivel de seguridad?**

- A) SSL
- B) STARTTLS ✓
- C) TLS
- D) HTTPS

**Explicación**: STARTTLS convierte una conexión SMTP plana existente en una cifrada mediante TLS, negociado durante la sesión.

---

### Pregunta 40
**¿Qué significa la alineación en DMARC?**

- A) Que el servidor esté sincronizado
- B) Que el dominio en From: coincida con el de SPF/DKIM ✓
- C) Que use el mismo puerto
- D) Que tenga el mismo tamaño

**Explicación**: La alineación asegura que el remitente visual (From:) sea el mismo dominio autenticado por SPF o DKIM, previniendo suplantación.

---

### Pregunta 41
**¿Cuál es la función de Procmail?**

- A) Enviar correos
- B) Es un MDA que filtra correos entrantes ✓
- C) Escanear virus
- D) Gestionar DNS

**Explicación**: Procmail es un MDA que permite automatizar acciones como mover mensajes a carpetas según reglas basadas en asunto, remitente, etc.

---

### Pregunta 42
**¿Qué puerto usa SMTP sobre SSL de forma implícita (SMTPS)?**

- A) 25
- B) 587
- C) 465 ✓
- D) 993

**Explicación**: El puerto 465 es el puerto tradicional para conexiones SMTP cifradas desde el inicio de la sesión (SSL implícito).

---

### Pregunta 43
**¿Qué es un alias de correo?**

- A) Un servidor secundario
- B) Una dirección virtual que redirige a buzones reales ✓
- C) Un protocolo de cifrado
- D) Un tipo de spam

**Explicación**: Los aliases son direcciones virtuales útiles para crear buzones funcionales como admin@, webmaster@ o soporte@ que redirigen a usuarios reales.

---

### Pregunta 44
**¿Qué comando de Dovecot verifica la sintaxis de la configuración?**

- A) dovecot check
- B) dovecot -n
- C) doveconf -n ✓
- D) dovecot test

**Explicación**: "doveconf -n" muestra la configuración actual de Dovecot y alerta sobre errores de formato o sintaxis.

---

### Pregunta 45
**¿Qué registro SPF autoriza a los servidores listados en el MX del dominio?**

- A) ip4
- B) mx ✓
- C) a
- D) include

**Explicación**: El mecanismo "mx" en SPF (v=spf1 mx -all) permite que cualquier IP listada en los registros MX del dominio sea válida para enviar.

---

### Pregunta 46
**¿Qué es el "Phishing"?**

- A) Un protocolo de correo
- B) Estafa para robar credenciales mediante correos falsos ✓
- C) Un tipo de cifrado
- D) Un servidor de correo

**Explicación**: El phishing explota la falta de autenticación de dominios legítimos para suplantar identidades y robar información sensible.

---

### Pregunta 47
**¿Qué parámetro de Postfix limita el tamaño máximo de un correo?**

- A) max_message_size
- B) message_size_limit ✓
- C) mailbox_size_limit
- D) queue_size_limit

**Explicación**: "message_size_limit" evita que el servidor se sature procesando adjuntos excesivamente grandes (por defecto 10MB).

---

### Pregunta 48
**¿Qué capa de transporte usa SMTP?**

- A) UDP
- B) TCP ✓
- C) ICMP
- D) IP

**Explicación**: SMTP usa TCP (Transmission Control Protocol) que garantiza que los datos lleguen íntegros y en el orden correcto.

---

### Pregunta 49
**¿Qué significa "FQDN"?**

- A) Fast Query Domain Name
- B) Full Qualified Domain Name ✓
- C) First Queue Delivery Node
- D) File Query Data Network

**Explicación**: FQDN (Fully Qualified Domain Name) es el nombre completo del host incluyendo su dominio (ej: mail.empresa.es).

---

### Pregunta 50
**¿Qué comando SMTP se envía después de recibir un éxito tras STARTTLS?**

- A) MAIL FROM
- B) EHLO ✓
- C) AUTH
- D) DATA

**Explicación**: El protocolo SMTP debe reiniciarse con EHLO después de establecer TLS para negociar capacidades sobre el túnel cifrado.

---

### Pregunta 51
**¿Qué archivo de Postfix contiene las restricciones de relay?**

- A) master.cf
- B) main.cf ✓
- C) access
- D) virtual

**Explicación**: En main.cf se configura "smtpd_recipient_restrictions" con directivas como permit_mynetworks, permit_sasl_authenticated, reject_unauth_destination.

---

### Pregunta 52
**¿Cuál es la diferencia principal entre SMTP y ESMTP?**

- A) ESMTP es más lento
- B) ESMTP añade capacidades extendidas (AUTH, STARTTLS, SIZE) ✓
- C) SMTP es más seguro
- D) No hay diferencia

**Explicación**: ESMTP (Extended SMTP) añade extensiones como autenticación (AUTH), cifrado (STARTTLS) y declaración de tamaño (SIZE).

---

### Pregunta 53
**¿Qué significa que un correo esté en estado "deferred" en la cola?**

- A) Ha sido entregado
- B) Está esperando reintento por error temporal ✓
- C) Ha sido rechazado permanentemente
- D) Está siendo escaneado

**Explicación**: "Deferred" indica que hubo un problema temporal (servidor destino ocupado, red caída) y Postfix reintentará el envío.

---

### Pregunta 54
**¿Qué herramienta online permite verificar la configuración completa de correo?**

- A) Google
- B) MXToolbox ✓
- C) Wikipedia
- D) GitHub

**Explicación**: MXToolbox proporciona verificación de registros DNS (MX, SPF, DKIM, DMARC), pruebas de listas negras y diagnóstico completo.

---

### Pregunta 55
**¿Qué RFC define el protocolo SMTP moderno?**

- A) RFC 821
- B) RFC 5321 ✓
- C) RFC 5322
- D) RFC 7208

**Explicación**: RFC 5321 es la especificación actual del protocolo SMTP. RFC 821 era la versión antigua, RFC 5322 define el formato de mensajes.

---

## Instrucciones para Importar a Kahoot

### Formato Requerido por Kahoot

Kahoot acepta importación mediante:
1. **Hoja de cálculo** (Excel/Google Sheets)
2. **Formato específico** con columnas: Question, Answer 1, Answer 2, Answer 3, Answer 4, Time limit, Correct answer(s)

### Pasos para Crear el Archivo de Importación

1. Crear una hoja de cálculo con las siguientes columnas:
   - **Question**: Texto de la pregunta
   - **Answer 1**: Primera opción
   - **Answer 2**: Segunda opción
   - **Answer 3**: Tercera opción
   - **Answer 4**: Cuarta opción
   - **Time limit**: Tiempo en segundos (20, 30, 60, etc.)
   - **Correct answer(s)**: Número de la respuesta correcta (1, 2, 3, o 4)

2. Copiar cada pregunta de este documento a la hoja de cálculo

3. Guardar como archivo Excel (.xlsx) o CSV

4. En Kahoot, ir a "Create" → "Import" → Seleccionar el archivo

### Recomendaciones

- **Tiempo límite**: 30-45 segundos para preguntas técnicas
- **Orden**: Mezclar aleatoriamente en Kahoot para evitar patrones
- **Explicaciones**: Activar "Show explanation" en Kahoot y copiar las explicaciones de este documento

---

**Total de Preguntas**: 55  
**Nivel**: Técnico avanzado  
**Tema**: Administración de Servicios de Correo Electrónico  
**Módulo**: SRI - ASIR
