# Instrucciones para Generar PDF del Kahoot

## 📄 Generación de PDF

Dado que las herramientas automáticas de conversión a PDF no están disponibles en este sistema, aquí tienes **3 métodos sencillos** para generar el PDF:

---

## Método 1: Desde el Navegador (MÁS FÁCIL) ⭐

1. **Abre el archivo HTML**:
   - Navega a: `d:\ASIR\2º\SRI\SRI\kahoot\kahoot_correo_electronico.html`
   - Haz doble clic para abrirlo en tu navegador predeterminado

2. **Imprime a PDF**:
   - Presiona `Ctrl + P` (o ve a Menú → Imprimir)
   - En "Destino" o "Impresora", selecciona **"Guardar como PDF"** o **"Microsoft Print to PDF"**
   - Configura:
     - Orientación: Vertical
     - Márgenes: Predeterminados
     - Escala: 100%
   - Haz clic en **"Guardar"**
   - Guarda como: `kahoot_correo_electronico.pdf` en la misma carpeta

3. **Listo**: Tendrás el PDF completo con todas las 55 preguntas

---

## Método 2: Desde Microsoft Word

1. **Abre Word**

2. **Abre el archivo Markdown**:
   - Ve a Archivo → Abrir
   - Navega a: `d:\ASIR\2º\SRI\SRI\kahoot\kahoot_correo_electronico.md`
   - Selecciona "Todos los archivos (*.*)" en el filtro
   - Abre el archivo

3. **Guarda como PDF**:
   - Ve a Archivo → Guardar como
   - Selecciona ubicación: `d:\ASIR\2º\SRI\SRI\kahoot\`
   - Tipo de archivo: **PDF (*.pdf)**
   - Nombre: `kahoot_correo_electronico.pdf`
   - Haz clic en **"Guardar"**

---

## Método 3: Usando Google Chrome

1. **Abre Chrome**

2. **Arrastra el archivo HTML**:
   - Arrastra `kahoot_correo_electronico.html` a una ventana de Chrome

3. **Imprime a PDF**:
   - Presiona `Ctrl + P`
   - Destino: **"Guardar como PDF"**
   - Diseño: Vertical
   - Páginas: Todas
   - Márgenes: Predeterminados
   - Opciones: Marca "Gráficos de fondo"
   - Haz clic en **"Guardar"**

---

## Método 4: Usando PowerShell (Avanzado)

Si tienes instalado `wkhtmltopdf`:

```powershell
cd "d:\ASIR\2º\SRI\SRI\kahoot"
wkhtmltopdf kahoot_correo_electronico.html kahoot_correo_electronico.pdf
```

Si tienes instalado `pandoc` con LaTeX:

```powershell
cd "d:\ASIR\2º\SRI\SRI\kahoot"
pandoc kahoot_correo_electronico.md -o kahoot_correo_electronico.pdf
```

---

## ✅ Verificación

Después de generar el PDF, verifica que:

- ✅ Contiene todas las 55 preguntas
- ✅ Las respuestas correctas están marcadas con ✓
- ✅ Las explicaciones están incluidas
- ✅ El formato es legible
- ✅ No hay texto cortado

---

## 💡 Recomendación

**El Método 1 (navegador) es el más sencillo y rápido.** Solo toma 30 segundos y no requiere software adicional.

---

## 📝 Nota

El archivo HTML (`kahoot_correo_electronico.html`) ya está creado y listo para usar. Simplemente ábrelo en cualquier navegador y usa Ctrl+P para generar el PDF.

**¡Es muy fácil!** 🚀
