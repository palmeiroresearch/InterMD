# 🏥 Monitor de Sala - Medicina Interna

## 📦 Archivos del Proyecto

Este paquete contiene una PWA completa para gestión de sala de Medicina Interna.

### Archivos Principales:

1. **index-sala.html** - Página de inicio y bienvenida ⭐ EMPIEZA AQUÍ
2. **monitor-sala.html** - Aplicación principal (PWA)
3. **guia-rapida-sala.html** - Guía rápida de uso
4. **README-monitor-sala.md** - Documentación completa

### Archivos de Configuración:

5. **manifest-sala.json** - Manifest de la PWA
6. **service-worker-sala.js** - Service Worker para funcionalidad offline

## 🚀 Despliegue Rápido

### Opción 1: GitHub Pages (Recomendado)

```bash
# 1. Crear un nuevo repositorio en GitHub
# 2. Subir todos los archivos a la raíz del repositorio
# 3. Ir a Settings > Pages
# 4. Seleccionar branch 'main' y carpeta '/ (root)'
# 5. Guardar y esperar unos minutos
# 6. Tu app estará en: https://tu-usuario.github.io/nombre-repo/index-sala.html
```

### Opción 2: Servidor Local

```bash
# Con Python 3
python -m http.server 8000

# Con Python 2
python -m SimpleHTTPServer 8000

# Con Node.js
npx http-server

# Luego abrir: http://localhost:8000/index-sala.html
```

### Opción 3: Abrir Directamente

1. Descomprimir todos los archivos en una carpeta
2. Abrir **index-sala.html** directamente en tu navegador
3. ⚠️ Algunas funcionalidades pueden estar limitadas sin servidor

## 📱 Instalación como PWA

### En Android (Chrome/Edge):
1. Abrir la aplicación en el navegador
2. Menú (⋮) > "Agregar a pantalla de inicio"
3. Confirmar instalación

### En iOS (Safari):
1. Abrir la aplicación en Safari
2. Botón "Compartir" (⬆️)
3. "Agregar a pantalla de inicio"
4. Confirmar

## 🎯 Primeros Pasos

1. **Abrir index-sala.html** - Página de inicio
2. Click en "Abrir Aplicación"
3. Agregar tu primer paciente
4. ¡Listo para usar!

## 📖 Documentación

- **Guía Rápida**: guia-rapida-sala.html
- **Documentación Completa**: README-monitor-sala.md

## ✨ Características Destacadas

✅ Ordenamiento inteligente por cama (1, 2, 3... 7, 8...)
✅ Fichas completas editables
✅ Evaluaciones diarias formato SOAP
✅ Gestión de pendientes con prioridades
✅ Alertas de alergias destacadas
✅ Generación de informes descargables
✅ Funciona 100% offline
✅ Datos permanentes en dispositivo
✅ Exportación/importación de respaldos

## ⚠️ Importante

- Los datos se guardan SOLO en el dispositivo local
- NO hay sincronización entre dispositivos
- Exporta datos regularmente como respaldo
- Herramienta de APOYO, no sustituye expediente oficial

## 🐛 Problemas Comunes

**No funciona offline:**
- Recarga la página una vez con internet

**Datos se borraron:**
- Importa tu último backup
- Configura navegador para no borrar datos

**Ordenamiento de camas incorrecto:**
- Actualiza tu navegador a la última versión

## 📞 Soporte

Para más información:
1. Leer README-monitor-sala.md (documentación completa)
2. Ver guia-rapida-sala.html (guía visual)
3. Revisar código fuente (está comentado)

## 📜 Licencia

Herramienta educativa para práctica preprofesional en medicina.
Uso bajo responsabilidad del profesional de salud.

---

**Monitor de Sala v1.0** - Medicina Interna
Desarrollado para práctica preprofesional
Compatible con entornos hospitalarios cubanos
Noviembre 2025

🩺 *"Tecnología al servicio de la Medicina Interna"*
