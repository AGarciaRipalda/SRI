# Material de Aula Invertida - Administración Avanzada de Servicios de Correo Electrónico

## 📋 Descripción

Este directorio contiene todo el material necesario para el modelo de **Aula Invertida (Flipped Classroom)** del tema de Administración Avanzada de Servicios de Correo Electrónico, correspondiente al módulo de Servicios de Red e Internet (SRI) del ciclo ASIR.

## 📁 Contenido del Material

### 1. 📚 Apuntes Teóricos
**Archivo**: [`apuntes_correo_electronico.md`](apuntes_correo_electronico.md)

Apuntes completos en formato Markdown que cubren:
- Arquitectura del correo electrónico (MUA, MTA, MDA, MSA)
- Protocolos SMTP, POP3, IMAP
- Configuración de Postfix y Dovecot
- Seguridad: SPF, DKIM, DMARC
- Cifrado TLS/SSL
- Protección contra spam y virus
- Troubleshooting y diagnóstico
- Comandos de referencia rápida

**Uso**: Leer antes de ver el video y antes de la clase presencial.

### 2. 🎥 Video Seleccionado
**Archivo**: [`video_seleccionado.md`](video_seleccionado.md)

Contiene:
- Enlace al video principal seleccionado
- Justificación pedagógica detallada
- Videos alternativos opcionales
- Instrucciones para aprovechar el video
- Tiempo estimado de estudio

**Video principal**: [How to Set Up Mail Server with Postfix and Dovecot on Ubuntu/Debian](https://www.youtube.com/watch?v=03GFRdFkQJA)

**Uso**: Ver el video siguiendo la técnica "pausar y replicar" en tu VM.

### 3. 🔗 Enlaces a Documentación Oficial
**Archivo**: [`documentacion_oficial.md`](documentacion_oficial.md)

Recopilación organizada de:
- Documentación oficial de Postfix
- Documentación oficial de Dovecot
- RFCs de protocolos (SMTP, SPF, DKIM, DMARC)
- Tutoriales completos de configuración
- Guías de troubleshooting
- Herramientas online de verificación

**Uso**: Consulta durante la configuración y para profundizar en temas específicos.

## 🎯 Metodología de Aula Invertida

### Fase 1: Preparación Individual (Antes de Clase)
**Tiempo estimado**: 3-4 horas

1. **Leer los apuntes** [`apuntes_correo_electronico.md`](apuntes_correo_electronico.md)
   - Familiarízate con los conceptos básicos
   - Identifica términos que no entiendas

2. **Ver el video** indicado en [`video_seleccionado.md`](video_seleccionado.md)
   - Usa la técnica "pausar y replicar"
   - Toma notas de tus dudas

3. **Practicar en VM**
   - Instala Postfix y Dovecot
   - Intenta configurar lo básico
   - Documenta los errores que encuentres

4. **Consultar documentación** de [`documentacion_oficial.md`](documentacion_oficial.md)
   - Busca soluciones a tus problemas
   - Profundiza en conceptos que te interesen

### Fase 2: Clase Presencial
**Tiempo**: 6 horas (distribuidas en 2-3 sesiones)

1. **Quiz inicial** (15 min)
   - Verificación de preparación previa
   - Identificación de conceptos a reforzar

2. **Resolución de dudas** (30 min)
   - Preguntas específicas de los alumnos
   - Aclaración de conceptos complejos

3. **Práctica avanzada** (4 horas)
   - Configuración de SPF, DKIM, DMARC
   - Implementación de antispam/antivirus
   - Usuarios virtuales con MySQL
   - Webmail con Roundcube

4. **Troubleshooting colaborativo** (1 hora)
   - Resolución de problemas reales
   - Análisis de logs
   - Diagnóstico de fallos

5. **Evaluación práctica** (30 min)
   - Configuración completa funcional
   - Verificación de seguridad

### Fase 3: Consolidación (Después de Clase)

1. **Completar configuración**
   - Terminar aspectos pendientes
   - Documentar tu configuración

2. **Pruebas adicionales**
   - Enviar correos a Gmail, Outlook, etc.
   - Verificar con herramientas online

3. **Preparar entrega**
   - Documentación técnica
   - Capturas de pantalla
   - Análisis de logs

## ✅ Checklist de Preparación

Antes de la clase presencial, asegúrate de haber:

- [ ] Leído completamente los apuntes
- [ ] Visto el video completo
- [ ] Creado una VM con Debian/Ubuntu
- [ ] Instalado Postfix y Dovecot
- [ ] Intentado enviar un correo local
- [ ] Documentado tus errores y dudas
- [ ] Consultado la documentación oficial
- [ ] Preparado preguntas específicas

## 🎓 Objetivos de Aprendizaje

Al completar este material y la clase presencial, serás capaz de:

- ✅ Explicar la arquitectura completa de un sistema de correo
- ✅ Configurar Postfix como MTA
- ✅ Configurar Dovecot como MDA
- ✅ Implementar autenticación SASL
- ✅ Configurar cifrado TLS/SSL
- ✅ Crear y publicar registros SPF, DKIM y DMARC
- ✅ Diagnosticar problemas de entrega de correo
- ✅ Analizar logs de mail.log
- ✅ Proteger el servidor contra spam y virus
- ✅ Gestionar usuarios y aliases

## 📊 Evaluación

### Evaluación Continua (40%)
- Quiz inicial de preparación (10%)
- Participación en clase (15%)
- Prácticas en laboratorio (15%)

### Evaluación Final (60%)
- Configuración completa funcional (30%)
- Documentación técnica (15%)
- Prueba teórico-práctica (15%)

## 🛠️ Requisitos Técnicos

### Hardware
- **RAM**: Mínimo 2GB para la VM
- **Disco**: 20GB libres
- **Procesador**: Soporte para virtualización

### Software
- **Hipervisor**: VirtualBox, VMware, o similar
- **SO de la VM**: Debian 11/12 o Ubuntu 22.04 LTS
- **Conexión**: Internet estable

### Conocimientos Previos
- Administración básica de Linux
- Comandos de terminal
- Edición de archivos de configuración
- Conceptos de redes (TCP/IP, DNS)

## 📞 Soporte

### Durante la Preparación
- **Foro del curso**: Para dudas generales
- **Documentación oficial**: Para consultas técnicas
- **Compañeros**: Grupos de estudio

### Durante la Clase
- **Profesor**: Resolución de dudas complejas
- **Asistentes**: Ayuda en configuración
- **Pares**: Trabajo colaborativo

## 📅 Cronograma Recomendado

### Semana 1
- **Lunes-Martes**: Leer apuntes y ver video
- **Miércoles-Jueves**: Practicar instalación básica
- **Viernes**: Preparar dudas para clase

### Semana 2
- **Lunes**: Clase presencial (Parte 1)
- **Miércoles**: Clase presencial (Parte 2)
- **Viernes**: Clase presencial (Parte 3)

### Semana 3
- **Lunes-Miércoles**: Completar configuración
- **Jueves**: Preparar documentación
- **Viernes**: Entrega final

## 🌟 Consejos para el Éxito

1. **No dejes la preparación para el último día**
   - El material es extenso y requiere práctica

2. **Documenta todo lo que hagas**
   - Comandos ejecutados
   - Errores encontrados
   - Soluciones aplicadas

3. **No tengas miedo de fallar**
   - Los errores son parte del aprendizaje
   - Cada fallo te enseña algo nuevo

4. **Consulta la documentación oficial**
   - Es la fuente más confiable
   - Te prepara para el mundo profesional

5. **Trabaja en grupo**
   - Comparte tus dudas
   - Ayuda a tus compañeros
   - Aprende de los demás

6. **Haz preguntas específicas**
   - "No funciona" no es una pregunta útil
   - "Obtengo error 550 al enviar a Gmail" es específica

## 📖 Recursos Adicionales

### Libros Recomendados
- "The Book of Postfix" - Ralf Hildebrandt
- "Postfix: The Definitive Guide" - Kyle D. Dent

### Comunidades
- r/sysadmin (Reddit)
- Server Fault (Stack Exchange)
- Postfix Users Mailing List

### Certificaciones Relacionadas
- Linux Professional Institute (LPIC-2)
- Red Hat Certified Engineer (RHCE)
- CompTIA Linux+

## 📝 Notas Importantes

> **⚠️ IMPORTANTE**: La preparación previa es **OBLIGATORIA**. La clase presencial asume que has visto el video y leído los apuntes. Sin esta preparación, no podrás seguir el ritmo de la clase.

> **💡 TIP**: Crea snapshots de tu VM antes de hacer cambios importantes. Te permitirá volver atrás si algo sale mal.

> **🔒 SEGURIDAD**: Nunca expongas tu servidor de correo a Internet sin haber configurado correctamente SPF, DKIM, DMARC y antispam. Podrías convertirte en un relay abierto.

## 🏆 Criterios de Excelencia

Para obtener la máxima calificación:

- ✅ Servidor completamente funcional
- ✅ Autenticación SPF, DKIM y DMARC configurada
- ✅ Cifrado TLS activo
- ✅ Antispam y antivirus funcionando
- ✅ Logs limpios sin errores
- ✅ Documentación técnica completa
- ✅ Pruebas de entregabilidad exitosas
- ✅ Demostración de troubleshooting

---

**Última actualización**: Febrero 2026  
**Módulo**: Servicios de Red e Internet (SRI)  
**Ciclo**: ASIR - Administración de Sistemas Informáticos en Red  
**Profesor**: [Nombre del Profesor]

---

## 📧 Contacto

Para dudas sobre el material:
- **Email**: [email del profesor]
- **Horario de tutoría**: [horario]
- **Aula**: [número de aula]

¡Mucho éxito en tu aprendizaje! 🚀
