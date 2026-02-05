# Administración Avanzada de Servicios de Correo Electrónico

## 📧 Tema Tratado

**Administración Avanzada de Servicios de Correo Electrónico**

Este repositorio contiene material didáctico completo para el aprendizaje de la administración de servidores de correo electrónico en entornos Linux, utilizando la metodología de **Aula Invertida (Flipped Classroom)**. El contenido cubre desde los fundamentos de los protocolos de correo hasta la implementación de medidas avanzadas de seguridad y autenticación.

**Módulo**: Servicios de Red e Internet (SRI)  
**Ciclo Formativo**: ASIR - Administración de Sistemas Informáticos en Red  
**Curso**: 2º ASIR  
**Año Académico**: 2025-2026

---

## 👨‍🎓 Autor

**Alejandro García Ripalda**  
Estudiante de 2º ASIR  
Ilerna Albor FP

---

## 📚 Índice del Material

### 1. Material de Aula Invertida (`aula_invertida/`)

Material diseñado para que el alumnado se prepare antes de las sesiones presenciales:

- **`README.md`** - Guía principal del material de aula invertida
- **`apuntes_correo_electronico.md`** - Apuntes completos en Markdown (~600 líneas)
  - Arquitectura del correo electrónico
  - Protocolos SMTP, POP3, IMAP
  - Configuración de Postfix y Dovecot
  - Seguridad: SPF, DKIM, DMARC
  - Cifrado TLS/SSL
  - Protección contra spam y virus
  - Troubleshooting y diagnóstico
  
- **`video_seleccionado.md`** - Video tutorial seleccionado con justificación pedagógica
  - Video principal: "How to Set Up Mail Server with Postfix and Dovecot"
  - Justificación pedagógica detallada (8 puntos)
  - Videos alternativos opcionales
  - Instrucciones de uso
  
- **`documentacion_oficial.md`** - Enlaces a documentación oficial (50+ recursos)
  - Documentación de Postfix y Dovecot
  - RFCs (SMTP, SPF, DKIM, DMARC)
  - Tutoriales completos
  - Herramientas de diagnóstico

### 2. Evaluación Interactiva (`kahoot/`)

Material para evaluación mediante Kahoot:

- **`README.md`** - Instrucciones completas de uso
- **`kahoot_correo_electronico.md`** - 55 preguntas técnicas con explicaciones
- **`kahoot_import.csv`** - Archivo CSV listo para importar a Kahoot
- **`kahoot_correo_electronico.html`** - Versión HTML para visualización
- **`GENERAR_PDF.md`** - Instrucciones para generar PDF

**Características del Kahoot**:
- 55 preguntas técnicas (no triviales)
- Explicaciones detalladas para cada respuesta
- Formato importable directamente a la plataforma
- Cobertura completa de todos los temas

### 3. Guía del Profesor (`guia_profesor/`)

Material de apoyo para el profesorado:

- **`guia_imparticion.md`** - Guía completa de impartición (~30 KB)
  - Planificación temporal (15 horas lectivas)
  - Desglose hora por hora de sesiones
  - 8 conceptos clave explicados
  - 12 errores típicos del alumnado con soluciones
  - Estrategias de impartición
  - Criterios de evaluación detallados
  - Checklists y recursos

- **`Flipped Classroom - Administración Avanzada de Servicios de Correo Electrónico.docx`** - Documento original del profesor

---

## 🗂️ Estructura del Repositorio

```
SRI/
├── README.md                          # Este archivo
│
├── aula_invertida/                    # Material para estudiantes
│   ├── README.md                      # Guía del material
│   ├── apuntes_correo_electronico.md  # Apuntes completos
│   ├── video_seleccionado.md          # Video y justificación
│   └── documentacion_oficial.md       # Enlaces a recursos
│
├── kahoot/                            # Material de evaluación
│   ├── README.md                      # Instrucciones de uso
│   ├── kahoot_correo_electronico.md   # 55 preguntas con explicaciones
│   ├── kahoot_import.csv              # Archivo para importar
│   ├── kahoot_correo_electronico.html # Versión HTML
│   └── GENERAR_PDF.md                 # Instrucciones PDF
│
└── guia_profesor/                     # Material para profesores
    ├── guia_imparticion.md            # Guía de impartición
    └── Flipped Classroom - (...).docx # Documento original
```

---

## 🎯 Objetivos de Aprendizaje

Al completar este material, el alumnado será capaz de:

1. ✅ **Identificar** los componentes de la arquitectura de correo (MUA, MTA, MDA, MSA)
2. ✅ **Configurar** servidores Postfix y Dovecot en entornos Linux
3. ✅ **Implementar** mecanismos de autenticación SASL y cifrado TLS
4. ✅ **Desplegar** registros de seguridad DNS (SPF, DKIM, DMARC)
5. ✅ **Diagnosticar** problemas comunes en servicios de correo
6. ✅ **Aplicar** medidas de protección contra spam y malware

---

## 🚀 Cómo Usar Este Material

### Para Estudiantes

1. **Preparación previa** (3-4 horas antes de clase):
   - Lee `aula_invertida/apuntes_correo_electronico.md`
   - Ve el video indicado en `aula_invertida/video_seleccionado.md`
   - Instala Postfix y Dovecot en tu VM siguiendo los apuntes
   - Documenta tus dudas

2. **Durante la clase presencial**:
   - Participa en el quiz Kahoot inicial
   - Resuelve dudas específicas con el profesor
   - Practica configuraciones avanzadas
   - Trabaja en troubleshooting colaborativo

3. **Después de clase**:
   - Completa la configuración en tu VM
   - Documenta todo el proceso
   - Prepara la entrega final

### Para Profesores

1. **Preparación**:
   - Lee `guia_profesor/guia_imparticion.md`
   - Importa el Kahoot desde `kahoot/kahoot_import.csv`
   - Prepara VM de demostración
   - Publica material con 1 semana de antelación

2. **Impartición**:
   - Sigue la planificación temporal de la guía
   - Usa el Kahoot para evaluación diagnóstica
   - Enfoca la clase en práctica y troubleshooting
   - Aplica los criterios de evaluación documentados

---

## 📊 Estadísticas del Material

- **Apuntes**: ~14.7 KB, 600+ líneas
- **Documentación**: 50+ enlaces verificados
- **Kahoot**: 55 preguntas técnicas
- **Guía del profesor**: ~30 KB, 12 errores típicos documentados
- **Total de archivos**: 11 archivos principales
- **Tiempo de preparación estudiante**: 3-4 horas
- **Tiempo de clase presencial**: 15 horas

---

## 🛠️ Tecnologías Cubiertas

### Software
- **Postfix** - Mail Transport Agent (MTA)
- **Dovecot** - Mail Delivery Agent (MDA)
- **OpenDKIM** - Implementación de DKIM
- **SpamAssassin** - Filtro antispam
- **ClamAV** - Antivirus
- **Amavis** - Coordinador de escaneo

### Protocolos
- **SMTP** (Simple Mail Transfer Protocol)
- **ESMTP** (Extended SMTP)
- **IMAP** (Internet Message Access Protocol)
- **POP3** (Post Office Protocol v3)
- **SASL** (Simple Authentication and Security Layer)
- **TLS/SSL** (Transport Layer Security)

### Estándares de Seguridad
- **SPF** (Sender Policy Framework)
- **DKIM** (DomainKeys Identified Mail)
- **DMARC** (Domain-based Message Authentication)

### Sistemas Operativos
- Debian 11/12
- Ubuntu 22.04 LTS

---

## 📖 Referencias y Documentación

### RFCs Principales
- **RFC 5321** - SMTP Protocol
- **RFC 5322** - Internet Message Format
- **RFC 3207** - SMTP STARTTLS
- **RFC 7208** - SPF
- **RFC 6376** - DKIM
- **RFC 7489** - DMARC

### Documentación Oficial
- [Postfix.org](https://www.postfix.org/)
- [Dovecot Wiki](https://doc.dovecot.org/)
- [DMARC.org](https://dmarc.org/)

### Herramientas de Verificación
- [MXToolbox](https://mxtoolbox.com/)
- [Mail-tester](https://www.mail-tester.com/)

---

## 💭 Reflexión Final del Grupo

### Sobre el Proceso de Creación

La elaboración de este material didáctico ha sido un ejercicio exhaustivo de síntesis y organización del conocimiento sobre administración de servicios de correo electrónico. El enfoque de **Aula Invertida** ha requerido un cambio de paradigma en la forma de presentar el contenido, priorizando la autonomía del estudiante y la optimización del tiempo presencial.

### Aprendizajes Clave

1. **Importancia de la Preparación Previa**: El modelo de aula invertida solo funciona si el material previo es de calidad y está bien estructurado. Los apuntes deben ser completos pero concisos, y el video debe ser cuidadosamente seleccionado.

2. **Valor de las Explicaciones**: En el Kahoot, no basta con tener preguntas técnicas; las explicaciones detalladas son fundamentales para el aprendizaje. Cada respuesta correcta debe incluir el "por qué", no solo el "qué".

3. **Anticipación de Errores**: Documentar los 12 errores típicos del alumnado ha requerido ponerse en el lugar del estudiante y anticipar dónde surgirán las dificultades. Esta anticipación es clave para una enseñanza efectiva.

4. **Integración de Recursos**: La combinación de apuntes propios, videos externos y documentación oficial crea un ecosistema de aprendizaje completo que atiende a diferentes estilos de aprendizaje.

### Desafíos Encontrados

- **Equilibrio entre profundidad y accesibilidad**: Encontrar el punto medio entre contenido técnico riguroso y material comprensible para estudiantes de 2º ASIR.

- **Selección de video**: Evaluar múltiples videos para encontrar uno que cumpliera todos los criterios pedagógicos (claridad, completitud, ritmo adecuado).

- **Creación de preguntas no triviales**: Diseñar 55 preguntas que requieran comprensión profunda, no solo memorización, fue un reto significativo.

### Valor Añadido del Material

Este material no es solo una recopilación de información, sino un **sistema pedagógico completo** que:

- Facilita el aprendizaje autónomo
- Optimiza el tiempo de clase presencial
- Proporciona evaluación continua
- Anticipa y previene errores comunes
- Ofrece recursos de profundización

### Aplicabilidad

El material es directamente aplicable en el aula y está diseñado para ser:

- **Reutilizable**: Válido para múltiples ediciones del curso
- **Adaptable**: Puede ajustarse a diferentes ritmos y niveles
- **Escalable**: Permite añadir contenido adicional sin romper la estructura
- **Profesional**: Sigue estándares de documentación técnica

### Conclusión

La creación de este material ha demostrado que la **calidad de la enseñanza** depende en gran medida de la **calidad de la preparación**. Un material bien estructurado, con objetivos claros, recursos abundantes y anticipación de dificultades, es la base para un aprendizaje efectivo.

El modelo de aula invertida, cuando se implementa correctamente con material de calidad, tiene el potencial de transformar la experiencia educativa, convirtiendo al estudiante en protagonista de su propio aprendizaje y al profesor en facilitador y guía.

---

## 📝 Licencia y Uso

Este material ha sido creado con fines educativos para el módulo de Servicios de Red e Internet del ciclo ASIR.

**Uso permitido**:
- ✅ Uso en el aula por profesores del módulo SRI
- ✅ Estudio personal por estudiantes de ASIR
- ✅ Adaptación para otros centros educativos (con atribución)

**Uso no permitido**:
- ❌ Uso comercial
- ❌ Redistribución sin atribución

---

## 📧 Contacto

Para dudas, sugerencias o mejoras del material:

**Estudiante**: Alejandro García Ripalda  
**Módulo**: SRI - Servicios de Red e Internet  
**Centro**: IES [Nombre del Centro]  
**Curso**: 2º ASIR (2025-2026)

---

## 🙏 Agradecimientos

- Al profesorado del módulo SRI por proporcionar el documento base
- A la comunidad de Postfix y Dovecot por la excelente documentación
- A los creadores de contenido educativo en YouTube por los tutoriales de referencia
- A la metodología Flipped Classroom por inspirar este enfoque pedagógico

---

**Última actualización**: Febrero 2026  
**Versión**: 1.0  
**Estado**: Material completo y listo para usar

---

<div align="center">

**🚀 ¡Material listo para transformar el aprendizaje de administración de correo electrónico! 🚀**

</div>
