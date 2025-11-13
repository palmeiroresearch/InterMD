# Monitor de Sala - Medicina Interna 🏥

Aplicación web progresiva (PWA) completa para gestión y seguimiento de pacientes hospitalizados en sala de Medicina Interna.

## 🎯 Características Principales

### ✅ Gestión Completa de Pacientes
- Registro ilimitado de pacientes con datos completos
- **Ordenamiento inteligente por cama** (1, 2, 3... 7, 8... no 1, 10, 11, 2)
- Búsqueda rápida por nombre, cama o diagnóstico
- Múltiples opciones de ordenamiento (cama, nombre, fecha ingreso, días estadía)

### 📋 Ficha Completa del Paciente
- **Datos personales**: Nombre, edad, sexo, historia clínica
- **Antropometría**: Peso, talla, IMC y superficie corporal (calculados automáticamente)
- **Información de ingreso**: Fecha, motivo, diagnósticos principales
- **Antecedentes**: Patológicos personales
- **Alergias**: Destacadas visualmente con alerta
- **Tratamiento actual**: Medicamentos y dosis

### 📝 Evaluaciones Diarias (Formato SOAP)
- **Signos vitales completos**: Temperatura, FC, FR, TA, PAM, SatO₂, Glicemia
- **Subjetivo**: Síntomas del paciente
- **Objetivo**: Hallazgos del examen físico
- **Assessment**: Impresión diagnóstica
- **Plan**: Conducta y manejo
- Edición de evaluaciones previas
- Historial cronológico completo

### ⚠️ Sistema de Pendientes
- Gestión de tareas por paciente
- Clasificación: Normal / Urgente
- Marcar como completado
- Vista consolidada de todos los pendientes
- Contador de pendientes activos por paciente

### 📊 Indicadores Visuales
- **Altas próximas**: Resaltado cuando quedan ≤3 días para alta
- **Pendientes urgentes**: Tarjetas rojas para pacientes con pendientes urgentes
- **Alergias**: Badge pulsante de alerta
- **Días de estadía**: Cálculo automático desde ingreso
- **Última evaluación**: Tiempo transcurrido desde última evaluación

### 💾 Persistencia y Respaldo
- Datos permanentes en dispositivo local
- Exportación completa en JSON
- Importación de respaldos
- Funciona 100% offline después de primera carga

### 📄 Generación de Informes
- Informes individuales completos
- Incluye toda la historia clínica
- Formato texto descargable
- Ideal para epicrisis o referencias

## 🚀 Instalación

### Opción 1: Uso Directo (Recomendado)
1. Abre `monitor-sala.html` en un navegador web moderno
2. Desde el navegador móvil: "Agregar a pantalla de inicio"
3. La app se instalará como PWA

### Opción 2: Servidor Local
```bash
# Usar Python
python -m http.server 8000

# O Node.js
npx http-server
```

Acceder a `http://localhost:8000/monitor-sala.html`

## 📖 Guía de Uso Detallada

### 1. Agregar un Nuevo Paciente

**Paso a paso:**
1. Click en **"➕ Nuevo Paciente"**
2. Completar información requerida:
   
   **Datos Personales:**
   - Nombre completo *
   - Número de cama * (se ordenará numéricamente)
   - Edad *
   - Sexo *
   - Historia clínica (opcional)
   - Peso y talla (opcionales - calcula automáticamente IMC y SC si ambos están disponibles)

   **Información de Ingreso:**
   - Fecha de ingreso *
   - Fecha probable de alta (opcional, activa alertas)
   - Motivo de ingreso *
   - Diagnósticos principales *

   **Antecedentes:**
   - Patológicos personales
   - 🚨 Alergias (se destacará en la ficha)

   **Tratamiento:**
   - Medicamentos actuales con dosis

3. Click en **"Guardar Paciente"**
4. Se abrirá automáticamente la ficha completa del paciente

### 2. Realizar una Evaluación Diaria

**En la tarjeta del paciente:**
1. Click en **"📝 Evaluar"**
2. Completar la evaluación:

   **Signos Vitales:**
   - Temperatura, FC, FR
   - TA (calcula PAM automáticamente)
   - SatO₂, Glicemia

   **Evolución (SOAP):**
   - **Subjetivo**: Cómo se siente el paciente
   - **Objetivo**: Hallazgos del examen físico
   - **Assessment**: Impresión diagnóstica actual
   - **Plan**: Conducta, cambios en tratamiento, estudios

3. Click en **"Guardar Evaluación"**

### 3. Ver Ficha Completa

Click en **"📋 Ficha"** para ver:
- Todos los datos del paciente organizados
- Indicadores de días de estadía
- Días para alta (si está configurada)
- Alergias destacadas
- Botón para editar la ficha

### 4. Ver Historia de Evaluaciones

1. Click en **"📊 Historia"**
2. Visualiza todas las evaluaciones en orden cronológico
3. Cada evaluación muestra:
   - Fecha y hora
   - Signos vitales
   - Evolución completa (SOAP)
   - Botón para editar
4. Click en **"📄 Generar Informe Completo"** para descargar

### 5. Gestionar Pendientes

**Por Paciente:**
1. Click en **"⚠️ Pendientes"**
2. Ver lista actual de pendientes
3. Para agregar nuevo:
   - Escribir descripción
   - Seleccionar urgencia (Normal/Urgente)
   - Click "Agregar"
4. Marcar checkbox cuando se complete
5. Click 🗑️ para eliminar

**Vista Global:**
- Ir a tab **"⚠️ Pendientes"**
- Ver todos los pendientes activos agrupados por paciente

### 6. Búsqueda y Filtrado

**Búsqueda:**
- Escribir en el campo de búsqueda
- Filtra por: nombre, número de cama, diagnóstico

**Ordenamiento:**
- **Por Cama**: Orden numérico correcto (1, 2, 3... 7, 8...)
- **Por Nombre**: Alfabético
- **Por Fecha de Ingreso**: Más recientes primero
- **Por Días de Estadía**: Mayor estadía primero

### 7. Editar Información

**Editar Ficha del Paciente:**
1. Abrir ficha completa
2. Click en **"✏️ Editar Ficha"**
3. Modificar los datos necesarios
4. Guardar

**Editar Evaluación:**
1. Abrir historia del paciente
2. En la evaluación deseada, click **"✏️ Editar"**
3. Modificar
4. Guardar

### 8. Exportar/Importar Datos

**Exportar (Backup):**
1. Click en **"📥 Exportar"** (header)
2. Se descarga archivo JSON con todos los datos
3. Guardar en lugar seguro

**Importar (Restaurar):**
1. Click en **"📤 Importar"**
2. ⚠️ Lee la advertencia (reemplaza datos actuales)
3. Seleccionar archivo JSON
4. Click "Importar Datos"

### 9. Eliminar Paciente

1. En la tarjeta del paciente, click **"🗑️"**
2. Confirmar eliminación
3. **⚠️ Esta acción no se puede deshacer**

## 📊 Interpretación de Indicadores Visuales

### Tarjetas de Pacientes

**Colores de fondo:**
- **Blanco**: Sin alertas
- **Amarillo claro**: Alta próxima (≤3 días)
- **Rojo claro**: Pendientes urgentes activos

**Badges:**
- 🔵 Número azul: Días de estadía
- 🟡 "Alta en Xd": Días hasta alta probable
- 🔴 "X pendiente(s)": Pendientes activos
- 🚨 "ALERGIA": Paciente con alergias (badge pulsante)

**Número de cama:**
- Círculo azul en esquina superior derecha
- Ordenado numéricamente en la vista

**Última evaluación:**
- 🟢 Verde: Última evaluación hace <24h
- 🔴 Rojo: Sin evaluación o hace >24h

### Tab de Estadísticas

Visualiza:
- Total de pacientes en sala
- Altas próximas (≤3 días)
- Total de pendientes activos
- Pendientes urgentes
- Promedio de días de estadía
- Distribución por días (≤3d, 4-7d, 8-14d, >14d)

## 🎨 Interfaz y Navegación

### Tabs Principales

1. **👥 Pacientes**: Vista principal con todas las tarjetas
2. **⚠️ Pendientes**: Consolidado de todos los pendientes
3. **📊 Estadísticas**: Resumen y métricas de la sala

### Estadísticas del Header

- Contador de pacientes totales (esquina superior derecha)
- Tres cards en vista de pacientes:
  - Pacientes en Sala
  - Altas Próximas (≤3d)
  - Pendientes Totales

## ⚙️ Funcionamiento Técnico

### Almacenamiento
- **Ubicación**: `localStorage` del navegador
- **Clave**: `sala_patients`
- **Formato**: JSON serializado
- **Persistencia**: Indefinida (hasta borrado manual)

### Cálculos Automáticos

**Antropometría:**
```
IMC = peso(kg) / [talla(m)]²
SC (Mosteller) = √[talla(cm) × peso(kg) / 3600]
```

**Signos Vitales:**
```
PAM = (TAS + 2×TAD) / 3
```

**Indicadores Temporales:**
```
Días de estadía = Hoy - Fecha de ingreso
Días hasta alta = Fecha probable alta - Hoy
Horas desde última evaluación = Hoy - Timestamp última evaluación
```

### Service Worker
- Cachea la aplicación para uso offline
- Estrategia: Cache-first, luego network
- Versión: `sala-monitor-v1.0.0`
- Se actualiza automáticamente en nuevas versiones

### Ordenamiento de Camas
El sistema usa ordenamiento numérico real:
```javascript
patients.sort((a, b) => a.bed - b.bed)
// Resultado: [1, 2, 3, 7, 8, 10, 15, 20]
// NO: [1, 10, 15, 2, 20, 3, 7, 8]
```

## 🔒 Privacidad y Seguridad

⚠️ **IMPORTANTE:**
- Los datos se almacenan **ÚNICAMENTE** en el dispositivo local
- No hay sincronización con servidores externos
- No se envía ninguna información por internet
- El dispositivo debe tener medidas de seguridad apropiadas
- Realizar backups regulares usando "Exportar"
- Los datos persisten hasta que se borren manualmente

## 📋 Requisitos del Sistema

### Navegadores Soportados
- Chrome/Edge 90+
- Safari 14+
- Firefox 88+
- Navegadores móviles modernos (Android/iOS)

### Dispositivos Recomendados
- Smartphones (iOS/Android)
- Tablets
- Computadoras portátiles
- Computadoras de escritorio

### Conectividad
- **Primera carga**: Requiere internet
- **Uso posterior**: 100% offline

## 🛠️ Personalización

### Modificar Campos de la Ficha

Editar en `monitor-sala.html`, sección del formulario:
```html
<div class="form-group">
    <label class="required">Tu Nuevo Campo</label>
    <input type="text" id="tuCampo" required>
</div>
```

### Agregar Nuevos Ordenamientos

En el select de ordenamiento:
```html
<option value="tucampo">Tu Criterio</option>
```

Y en la función de ordenamiento:
```javascript
case 'tucampo':
    return a.tucampo - b.tucampo;
```

### Cambiar Umbrales de Alertas

**Altas próximas (actualmente ≤3 días):**
```javascript
const daysToDischarge <= 3  // Cambiar el 3
```

**Evaluación antigua (actualmente >24h):**
```javascript
hourssinceEval > 24  // Cambiar el 24
```

## 📄 Estructura del Informe Generado

El informe incluye:
1. **Datos del paciente**: Completos
2. **⚠️ Alergias**: Destacadas al inicio si existen
3. **Hospitalización**: Fechas y días
4. **Motivo de ingreso**
5. **Diagnósticos principales**
6. **Antecedentes**
7. **Tratamiento actual**
8. **Evaluaciones completas**: Cronológicas con:
   - Fecha y hora
   - Signos vitales
   - SOAP completo

Formato: Texto plano (.txt) descargable

## 🤝 Casos de Uso Típicos

### Inicio de Guardia
1. Abrir app
2. Revisar tab "Pendientes" para prioridades
3. Identificar altas próximas (tarjetas amarillas)
4. Ver pacientes sin evaluación reciente

### Durante el Pase de Visita
1. Evaluar cada paciente
2. Actualizar pendientes
3. Modificar fecha de alta si corresponde
4. Generar informes si hay altas

### Fin de Guardia
1. Revisar que todos estén evaluados
2. Verificar pendientes urgentes
3. Exportar datos como backup
4. Entregar pendientes importantes al relevo

### Preparación de Alta
1. Abrir ficha del paciente
2. Click "Generar Informe Completo"
3. Usar para epicrisis o resumen

## ⚕️ Buenas Prácticas

### Evaluaciones
- ✅ Evaluar todos los pacientes al menos 1 vez/día
- ✅ Documentar cambios importantes inmediatamente
- ✅ Usar formato SOAP consistentemente
- ✅ Incluir siempre signos vitales

### Gestión de Pendientes
- ✅ Marcar urgentes solo lo realmente urgente
- ✅ Completar pendientes en el momento
- ✅ Eliminar pendientes obsoletos
- ✅ Ser específico en descripciones

### Datos del Paciente
- ✅ Verificar alergias al ingreso
- ✅ Mantener tratamiento actualizado
- ✅ Actualizar diagnósticos si cambian
- ✅ Establecer fecha probable de alta

### Seguridad de Datos
- ✅ Exportar datos semanalmente
- ✅ No compartir dispositivo sin protección
- ✅ Verificar respaldos periódicamente
- ✅ Eliminar pacientes dados de alta regularmente

## 🚫 Limitaciones

- ⚠️ No sustituye el expediente clínico oficial
- ⚠️ No tiene sincronización multi-dispositivo
- ⚠️ Los datos están limitados al dispositivo
- ⚠️ Requiere backup manual para respaldo
- ⚠️ No genera indicaciones médicas automáticas

## 🐛 Solución de Problemas

### No puedo agregar más pacientes
- **Causa**: No hay límite, verifica el navegador
- **Solución**: Prueba con otro navegador o limpia caché

### Los datos se borraron
- **Causa**: Limpieza de datos del navegador
- **Solución**: Importar último backup, configurar navegador para no borrar datos

### No funciona offline
- **Causa**: Service Worker no registrado
- **Solución**: Recargar página con internet una vez

### El ordenamiento de camas no funciona
- **Causa**: Navegador muy antiguo
- **Solución**: Actualizar navegador

### No se guarda información nueva
- **Causa**: localStorage lleno (muy raro)
- **Solución**: Exportar, eliminar pacientes antiguos, importar

## 📞 Soporte

Para dudas o problemas:
1. Revisar esta documentación
2. Verificar código fuente (está comentado)
3. Verificar Console del navegador para errores
4. Verificar permisos de almacenamiento local

## 📜 Licencia

Herramienta educativa y de apoyo clínico.
Uso bajo responsabilidad del profesional de salud.

---

**Desarrollado para práctica preprofesional en medicina**
**Compatible con Cuba healthcare settings**
**Última actualización: Noviembre 2025**

🩺 *"Tecnología al servicio de la Medicina Interna"*

## 🎓 Créditos

Desarrollado siguiendo las mejores prácticas de:
- PWA (Progressive Web Apps)
- Diseño mobile-first
- Offline-first architecture
- Clinical workflow optimization

Inspirado en las necesidades reales de guardias hospitalarias en Medicina Interna.
