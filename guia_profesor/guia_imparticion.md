# Guía del Profesor - Administración Avanzada de Servicios de Correo Electrónico

## 📋 Información General

**Tema**: Administración Avanzada de Servicios de Correo Electrónico  
**Módulo**: Servicios de Red e Internet (SRI)  
**Ciclo**: ASIR - Administración de Sistemas Informáticos en Red  
**Metodología**: Aula Invertida (Flipped Classroom)  
**Duración Total**: 15 horas lectivas (distribuidas en 3 semanas)

---

## 🎯 Objetivos de Aprendizaje

Al finalizar este tema, el alumnado será capaz de:

1. **Identificar** los componentes de la arquitectura de correo (MUA, MTA, MDA, MSA)
2. **Configurar** servidores Postfix y Dovecot en entornos Linux
3. **Implementar** mecanismos de autenticación (SASL) y cifrado (TLS)
4. **Desplegar** registros de seguridad DNS (SPF, DKIM, DMARC)
5. **Diagnosticar** problemas comunes en servicios de correo
6. **Aplicar** medidas de protección contra spam y malware

---

## 📅 Planificación Temporal

### Semana 1: Preparación Individual (Trabajo Autónomo)

**Duración**: 3-4 horas (fuera del aula)

**Actividades del alumnado**:
- Lectura de apuntes en Markdown (60 min)
- Visualización del video tutorial (45 min)
- Instalación de Postfix y Dovecot en VM personal (90 min)
- Documentación de errores y dudas (30 min)

**Rol del profesor**:
- Publicar material con 1 semana de antelación
- Estar disponible en foro para dudas generales
- Recordar la obligatoriedad de la preparación previa

### Semana 2: Sesiones Presenciales

#### Sesión 1: Diagnóstico y Fundamentos (5 horas)

**Hora 1: Evaluación Inicial**
- **0:00-0:15** - Quiz Kahoot diagnóstico (20 preguntas básicas)
- **0:15-0:30** - Revisión de resultados y detección de lagunas
- **0:30-0:45** - Resolución de dudas del material previo
- **0:45-1:00** - Demostración en vivo: instalación básica

**Hora 2-3: Configuración Básica**
- **1:00-2:00** - Práctica guiada: Configuración de Postfix (main.cf)
- **2:00-2:30** - Práctica guiada: Configuración de Dovecot
- **2:30-3:00** - Pruebas de envío/recepción local

**Hora 4-5: DNS y Resolución**
- **3:00-4:00** - Configuración de registros MX y PTR
- **4:00-4:30** - Troubleshooting de problemas DNS
- **4:30-5:00** - Evaluación formativa y cierre

#### Sesión 2: Seguridad y Autenticación (5 horas)

**Hora 1: Autenticación**
- **0:00-0:30** - Repaso: SASL y su importancia
- **0:30-1:00** - Configuración Postfix-Dovecot SASL

**Hora 2-3: Cifrado TLS**
- **1:00-1:30** - Generación de certificados (Let's Encrypt simulado)
- **1:30-2:30** - Configuración TLS en Postfix y Dovecot
- **2:30-3:00** - Pruebas con STARTTLS

**Hora 4-5: SPF, DKIM, DMARC**
- **3:00-3:30** - Implementación de SPF
- **3:30-4:15** - Configuración de OpenDKIM
- **4:15-4:45** - Creación de política DMARC
- **4:45-5:00** - Verificación con herramientas online

#### Sesión 3: Protección y Troubleshooting (5 horas)

**Hora 1-2: Antispam y Antivirus**
- **0:00-1:00** - Instalación y configuración de SpamAssassin
- **1:00-2:00** - Integración de ClamAV con Amavis

**Hora 3-4: Troubleshooting**
- **2:00-2:30** - Análisis de logs (/var/log/mail.log)
- **2:30-3:00** - Gestión de colas con postqueue
- **3:00-3:30** - Casos prácticos de errores comunes
- **3:30-4:00** - Uso de herramientas de diagnóstico

**Hora 5: Evaluación Final**
- **4:00-4:30** - Quiz Kahoot completo (55 preguntas)
- **4:30-5:00** - Revisión y cierre del tema

### Semana 3: Consolidación y Entrega

**Actividades del alumnado**:
- Completar configuración en VM personal
- Documentar la instalación completa
- Realizar pruebas de entregabilidad
- Preparar entrega final

**Rol del profesor**:
- Tutorías individuales (opcional)
- Revisión de entregas
- Evaluación final

---

## 🔑 Conceptos Clave para el Éxito

### 1. Arquitectura de Agentes (CRÍTICO)

**Por qué es clave**: Sin entender la separación de responsabilidades entre MUA, MTA, MDA y MSA, el alumnado no comprenderá dónde configurar cada aspecto.

**Cómo enseñarlo**:
- Usar diagramas de flujo en la pizarra
- Trazar el recorrido de un correo desde origen a destino
- Identificar qué software (Postfix, Dovecot, Thunderbird) cumple cada rol

**Señal de comprensión**: El alumno puede explicar por qué Postfix no gestiona contraseñas directamente.

### 2. Envelope vs Headers (CRÍTICO)

**Por qué es clave**: La confusión entre el "sobre" (MAIL FROM) y las cabeceras visibles (From:) es la raíz de muchos errores de configuración y de no entender SPF/DKIM/DMARC.

**Cómo enseñarlo**:
- Mostrar una sesión SMTP en telnet
- Capturar con Wireshark y mostrar la diferencia
- Explicar que los spammers explotan esta diferencia

**Señal de comprensión**: El alumno entiende por qué DMARC requiere "alineación".

### 3. DNS como Pilar Fundamental (CRÍTICO)

**Por qué es clave**: El 80% de los problemas de correo en producción son por DNS mal configurado.

**Cómo enseñarlo**:
- Demostrar con `dig MX`, `dig TXT`, `dig PTR`
- Mostrar cómo un servidor busca el MX antes de enviar
- Explicar que sin PTR, muchos servidores rechazan el correo

**Señal de comprensión**: El alumno verifica DNS antes de culpar a Postfix.

### 4. Open Relay = Desastre (CRÍTICO)

**Por qué es clave**: Un Open Relay garantiza inclusión en listas negras en cuestión de horas.

**Cómo enseñarlo**:
- Mostrar qué es `reject_unauth_destination`
- Demostrar una prueba de Open Relay con telnet
- Explicar las consecuencias reales (IP bloqueada, dominio en blacklist)

**Señal de comprensión**: El alumno SIEMPRE verifica `smtpd_recipient_restrictions`.

### 5. Logs Son Tu Mejor Amigo (IMPORTANTE)

**Por qué es clave**: Sin saber leer `/var/log/mail.log`, el troubleshooting es imposible.

**Cómo enseñarlo**:
- Mostrar `tail -f /var/log/mail.log` en vivo
- Enseñar a rastrear un mensaje por su ID único
- Explicar los códigos de estado (250, 550, 421, etc.)

**Señal de comprensión**: El alumno usa `grep` para buscar errores específicos.

### 6. SPF/DKIM/DMARC No Son Opcionales (IMPORTANTE)

**Por qué es clave**: Gmail, Outlook y otros grandes proveedores rechazan correos sin autenticación.

**Cómo enseñarlo**:
- Mostrar un rechazo real de Gmail (error 550-5.7.26)
- Explicar que no es "seguridad extra", es requisito mínimo
- Demostrar verificación con MXToolbox

**Señal de comprensión**: El alumno implementa los tres antes de probar con Gmail.

### 7. TLS No Es Solo "Cifrado" (IMPORTANTE)

**Por qué es clave**: STARTTLS protege contraseñas en tránsito, sin él, las credenciales van en texto plano.

**Cómo enseñarlo**:
- Capturar con Wireshark una sesión sin TLS (mostrar contraseña visible)
- Capturar con TLS (mostrar datos cifrados)
- Explicar diferencia entre puerto 25 (STARTTLS) y 465 (SSL implícito)

**Señal de comprensión**: El alumno configura TLS antes de permitir autenticación.

### 8. Maildir > mbox (ÚTIL)

**Por qué es útil**: En sistemas modernos, Maildir evita corrupción y problemas de bloqueo.

**Cómo enseñarlo**:
- Mostrar la estructura de directorios de Maildir
- Explicar problemas de mbox en buzones grandes
- Configurar `mail_location = maildir:~/Maildir`

**Señal de comprensión**: El alumno elige Maildir por defecto.

---

## ⚠️ Errores Típicos del Alumnado

### Error 1: No Configurar el Hostname Correctamente

**Síntoma**: Postfix no arranca o da errores de "hostname lookup failure"

**Causa**: El alumno instala Postfix sin verificar que `hostname -f` devuelve un FQDN válido.

**Solución**:
```bash
# Verificar ANTES de instalar
hostname -f  # Debe devolver algo como mail.ejemplo.local

# Si no es correcto, configurar
sudo hostnamectl set-hostname mail.ejemplo.local
echo "192.168.1.10 mail.ejemplo.local mail" | sudo tee -a /etc/hosts
```

**Prevención**: Incluir verificación de hostname en el checklist inicial.

---

### Error 2: Olvidar Abrir Puertos en el Firewall

**Síntoma**: "Connection refused" al intentar conectar desde otro equipo

**Causa**: El alumno configura todo perfectamente pero olvida el firewall.

**Solución**:
```bash
# Verificar puertos abiertos
sudo nmap localhost

# Abrir puertos necesarios
sudo ufw allow 25/tcp
sudo ufw allow 587/tcp
sudo ufw allow 993/tcp
sudo ufw allow 995/tcp
```

**Prevención**: Hacer que usen `nmap` sistemáticamente después de cada cambio.

---

### Error 3: Confundir main.cf con master.cf

**Síntoma**: Añaden configuración de submission en main.cf y no funciona

**Causa**: No entienden que main.cf es comportamiento y master.cf es qué demonios ejecutar.

**Solución**:
- **main.cf**: Parámetros globales (myhostname, mydestination, etc.)
- **master.cf**: Servicios y puertos (submission, smtps, etc.)

**Prevención**: Usar la analogía "main.cf = reglas del juego, master.cf = jugadores en el campo".

---

### Error 4: No Ejecutar newaliases Después de Editar /etc/aliases

**Síntoma**: Los aliases no funcionan aunque estén bien escritos

**Causa**: Olvidan que /etc/aliases es texto plano y debe compilarse.

**Solución**:
```bash
sudo nano /etc/aliases
# Añadir: postmaster: root
sudo newaliases  # ¡CRÍTICO!
```

**Prevención**: Crear un checklist: "Editar → newaliases → Probar".

---

### Error 5: Permisos Incorrectos en Maildir

**Síntoma**: Dovecot no puede escribir en los buzones

**Causa**: Los directorios de correo pertenecen a root en lugar del usuario.

**Solución**:
```bash
# Para usuarios virtuales
sudo chown -R vmail:vmail /var/mail/vmail
sudo chmod -R 700 /var/mail/vmail

# Para usuarios del sistema
sudo chown -R usuario:usuario /home/usuario/Maildir
```

**Prevención**: Enseñar `ls -la` para verificar permisos antes de culpar a Dovecot.

---

### Error 6: Crear un Open Relay Accidentalmente

**Síntoma**: El servidor empieza a enviar spam masivo

**Causa**: Configuran `mynetworks = 0.0.0.0/0` o no incluyen `reject_unauth_destination`.

**Solución**:
```bash
# En main.cf, SIEMPRE:
mynetworks = 127.0.0.0/8, 192.168.1.0/24
smtpd_recipient_restrictions = 
    permit_mynetworks,
    permit_sasl_authenticated,
    reject_unauth_destination  # ¡CRÍTICO!
```

**Prevención**: Hacer prueba de Open Relay obligatoria con telnet antes de aprobar la práctica.

---

### Error 7: No Verificar Registros DNS Antes de Probar

**Síntoma**: El correo no llega a Gmail/Outlook

**Causa**: Asumen que porque Postfix arranca, todo está bien. No verifican MX, PTR, SPF.

**Solución**:
```bash
# Verificar ANTES de enviar
dig MX ejemplo.com
dig PTR 203.0.113.5
dig TXT ejemplo.com  # Ver SPF
dig TXT selector._domainkey.ejemplo.com  # Ver DKIM
```

**Prevención**: Checklist obligatorio de verificación DNS antes de pruebas externas.

---

### Error 8: Usar Certificados Autofirmados Sin Configurar el Cliente

**Síntoma**: Thunderbird rechaza la conexión por certificado no confiable

**Causa**: Generan certificado autofirmado pero no lo importan en el cliente.

**Solución**:
- Usar Let's Encrypt (recomendado)
- O importar el certificado autofirmado en el cliente
- O configurar el cliente para aceptar certificados no confiables (solo para pruebas)

**Prevención**: Explicar diferencia entre certificados de CA pública vs autofirmados.

---

### Error 9: No Reiniciar Servicios Después de Cambios

**Síntoma**: Los cambios en configuración no tienen efecto

**Causa**: Editan archivos pero no recargan/reinician Postfix o Dovecot.

**Solución**:
```bash
# Después de cambios en Postfix
sudo postfix check  # Verificar sintaxis
sudo systemctl reload postfix  # O restart si es necesario

# Después de cambios en Dovecot
sudo doveconf -n  # Verificar sintaxis
sudo systemctl restart dovecot
```

**Prevención**: Crear hábito: "Editar → Check → Reload → Probar".

---

### Error 10: Confundir IMAP con POP3

**Síntoma**: Configuran POP3 pero esperan sincronización entre dispositivos

**Causa**: No entienden la diferencia fundamental entre ambos protocolos.

**Solución**:
- **POP3**: Descarga y (típicamente) borra del servidor → Un solo dispositivo
- **IMAP**: Sincronización bidireccional → Múltiples dispositivos

**Prevención**: Tabla comparativa clara en los apuntes y pregunta en el quiz.

---

### Error 11: No Leer los Logs Cuando Algo Falla

**Síntoma**: Dicen "no funciona" sin más información

**Causa**: No saben o no quieren leer `/var/log/mail.log`.

**Solución**:
```bash
# Enseñar a leer logs
sudo tail -f /var/log/mail.log  # En tiempo real
sudo grep "error" /var/log/mail.log | tail -20  # Últimos errores
sudo grep "ID_MENSAJE" /var/log/mail.log  # Rastrear mensaje específico
```

**Prevención**: Hacer obligatorio incluir logs en cualquier consulta de error.

---

### Error 12: Copiar Configuraciones Sin Entender

**Síntoma**: Configuración funciona pero no saben explicar por qué

**Causa**: Copian y pegan de tutoriales sin leer la documentación.

**Solución**: Exigir que expliquen cada directiva que usan en la entrega final.

**Prevención**: Preguntas del quiz sobre parámetros específicos de configuración.

---

## 🎓 Estrategias de Impartición

### 1. Uso del Modelo Flipped Classroom

**Antes de Clase**:
- Publicar material con 1 semana de antelación
- Enviar recordatorio 3 días antes
- Estar disponible en foro para dudas

**Inicio de Clase**:
- Quiz Kahoot obligatorio (10-20 preguntas)
- Identificar conceptos que necesitan refuerzo
- Resolver dudas específicas (no repetir el video)

**Durante la Clase**:
- Práctica guiada (profesor hace, alumnos replican)
- Práctica supervisada (alumnos hacen, profesor supervisa)
- Troubleshooting colaborativo (grupos resuelven problemas)

**Después de Clase**:
- Completar configuración en casa
- Documentar todo el proceso
- Preparar entrega con capturas y logs

### 2. Gestión de Grupos

**Grupos Heterogéneos**:
- Mezclar alumnos con diferentes niveles
- El avanzado ayuda al que tiene dificultades
- Todos aprenden (enseñar refuerza el conocimiento)

**Rotación de Roles**:
- Sesión 1: Alumno A configura, B documenta
- Sesión 2: Alumno B configura, A documenta
- Todos practican todo

### 3. Uso de Máquinas Virtuales

**Ventajas**:
- Snapshots antes de cambios importantes
- Posibilidad de "romper" sin consecuencias
- Entorno idéntico para todos

**Configuración Recomendada**:
- Debian 11/12 o Ubuntu 22.04 LTS
- 2GB RAM mínimo
- 20GB disco
- Red en modo puente o NAT con port forwarding

### 4. Evaluación Continua

**Formativa** (no cuenta para nota):
- Quiz inicial diagnóstico
- Preguntas durante la práctica
- Revisión de configuraciones en vivo

**Sumativa** (cuenta para nota):
- Configuración funcional completa (40%)
- Documentación técnica (30%)
- Quiz final Kahoot (15%)
- Troubleshooting de caso práctico (15%)

---

## 📊 Criterios de Evaluación

### Configuración Funcional (40 puntos)

- **Postfix configurado** (10 puntos)
  - main.cf correcto
  - master.cf con submission habilitado
  - Sin Open Relay

- **Dovecot configurado** (10 puntos)
  - IMAP/POP3 funcionando
  - Autenticación SASL integrada
  - Maildir configurado

- **Seguridad implementada** (15 puntos)
  - TLS/STARTTLS activo (5 puntos)
  - SPF configurado (3 puntos)
  - DKIM funcionando (4 puntos)
  - DMARC publicado (3 puntos)

- **Pruebas exitosas** (5 puntos)
  - Envío local funciona
  - Envío a Gmail/Outlook funciona
  - Recepción funciona

### Documentación Técnica (30 puntos)

- **Completitud** (10 puntos)
  - Todos los pasos documentados
  - Capturas de pantalla relevantes
  - Logs incluidos

- **Claridad** (10 puntos)
  - Explicaciones comprensibles
  - Comandos correctamente formateados
  - Estructura lógica

- **Análisis** (10 puntos)
  - Explicación de decisiones tomadas
  - Problemas encontrados y soluciones
  - Verificaciones realizadas

### Quiz Kahoot (15 puntos)

- Basado en las 55 preguntas técnicas
- Puntuación proporcional a aciertos
- Mínimo 60% para aprobar esta parte

### Troubleshooting (15 puntos)

- Caso práctico con error introducido
- Debe diagnosticar usando logs
- Debe proponer y aplicar solución
- Debe verificar que funciona

---

## 💡 Consejos para el Profesor

### 1. Preparación Previa

- **Probar todo el material** en una VM antes de clase
- **Tener snapshots** de diferentes estados (básico, con TLS, completo)
- **Preparar errores comunes** para demostrar troubleshooting
- **Tener plan B** si Internet falla (usar DNS local)

### 2. Durante la Clase

- **Circular constantemente** entre los alumnos
- **No dar soluciones directas**, hacer preguntas guía
- **Usar la pizarra** para diagramas y flujos
- **Capturar errores interesantes** para discusión grupal

### 3. Gestión del Tiempo

- **No extenderse en teoría** (ya la vieron en el video)
- **Priorizar práctica** y resolución de problemas
- **Dejar tiempo para troubleshooting** (siempre surgen imprevistos)
- **No intentar cubrir todo** si el grupo va lento (mejor profundizar)

### 4. Atención a la Diversidad

- **Alumnos avanzados**: Retos adicionales (usuarios virtuales, clustering)
- **Alumnos con dificultades**: Tutorías individuales, checklist más detallado
- **Todos**: Aprendizaje colaborativo, nadie se queda atrás

### 5. Uso de Herramientas

- **Proyector**: Para demostraciones en vivo
- **Pizarra**: Para diagramas y conceptos
- **Foro/Chat**: Para dudas asíncronas
- **MXToolbox**: Para verificaciones en vivo

---

## 🔍 Indicadores de Éxito

### A Nivel Individual

- ✅ El alumno completa la configuración sin ayuda
- ✅ Puede explicar cada parámetro que usa
- ✅ Diagnostica errores leyendo logs
- ✅ Verifica DNS antes de culpar a Postfix
- ✅ Documenta su trabajo de forma profesional

### A Nivel de Grupo

- ✅ Más del 80% aprueba el quiz final
- ✅ Todos tienen servidor funcional al final
- ✅ Participación activa en troubleshooting colaborativo
- ✅ Preguntas de calidad (específicas, con contexto)

### A Nivel de Sesión

- ✅ El tiempo se usa eficientemente (poco tiempo muerto)
- ✅ Los alumnos llegan preparados (han visto el material)
- ✅ Las dudas son avanzadas (no básicas del video)
- ✅ Ambiente de colaboración (no competitivo)

---

## 📚 Recursos Adicionales para el Profesor

### Documentación de Referencia

- [Postfix Documentation](https://www.postfix.org/documentation.html)
- [Dovecot Wiki](https://doc.dovecot.org/)
- [RFC 5321 - SMTP](https://datatracker.ietf.org/doc/html/rfc5321)
- [RFC 7208 - SPF](https://datatracker.ietf.org/doc/html/rfc7208)

### Herramientas Útiles

- **MXToolbox**: Verificación completa de configuración
- **Mail-tester**: Puntuación de spam
- **Wireshark**: Captura de tráfico SMTP
- **Telnet**: Pruebas manuales de SMTP

### Comunidades

- r/sysadmin (Reddit)
- Postfix Users Mailing List
- Server Fault (Stack Exchange)

---

## 📝 Checklist del Profesor

### Antes de Empezar el Tema

- [ ] Material publicado con 1 semana de antelación
- [ ] VM de demostración preparada y probada
- [ ] Snapshots creados en diferentes estados
- [ ] Kahoot importado y probado
- [ ] Casos de troubleshooting preparados

### Antes de Cada Sesión

- [ ] Proyector y pizarra funcionando
- [ ] Conexión a Internet estable
- [ ] Material de la sesión accesible
- [ ] Checklist de la sesión impreso

### Durante la Sesión

- [ ] Quiz inicial completado
- [ ] Dudas principales resueltas
- [ ] Práctica guiada realizada
- [ ] Todos los alumnos avanzan
- [ ] Tiempo para troubleshooting

### Después de Cada Sesión

- [ ] Notas sobre dificultades encontradas
- [ ] Actualización de material si es necesario
- [ ] Respuesta a dudas en foro
- [ ] Preparación de siguiente sesión

### Al Finalizar el Tema

- [ ] Todas las entregas revisadas
- [ ] Feedback individual proporcionado
- [ ] Notas de mejora para próxima edición
- [ ] Material actualizado si es necesario

---

**Última actualización**: Febrero 2026  
**Autor**: Material didáctico SRI - ASIR  
**Versión**: 1.0

---

## 📧 Contacto y Soporte

Para dudas sobre este material o sugerencias de mejora, contactar con el departamento de informática.

**¡Éxito en la impartición del tema!** 🚀
