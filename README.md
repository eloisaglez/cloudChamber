# 🛰️ Simulador CanSat: Cloud Chamber

Simulador interactivo para el proyecto CanSat "Cloud Chamber" - Verificación Experimental de la Formación de Nubes mediante Condensación Atmosférica en la Capa Límite Planetaria.

## 🎯 Características

- **Simulación realista** del vuelo completo:
  - **Ascenso rápido** (el CanSat es transportado por globo/cohete/avioneta - no visible)
  - **Descenso lento** con paracaídas desplegado visualmente
- **Gráficas dinámicas** de temperatura y presión vs altitud
- **Visualización animada** del CanSat con tubo de condensación
- **Cálculo automático** del LCL (Lifting Condensation Level)
- **Gradiente térmico ajustable** (para simular condiciones reales de la capa límite: 4-10°C/km)
- **Predicción** de si habrá condensación o no
- **Animación de condensación** cuando se alcanza el punto de rocío
- **Responsive** - funciona en móviles, tablets y ordenadores

## 🚀 Cómo usar

1. **Introduce las condiciones atmosféricas:**
   - Temperatura inicial (T₀) en °C
   - Humedad Relativa (HR₀) en %
   - Presión inicial (P₀) en hPa
   - Gradiente térmico (típicamente 6.5°C/km, ajustable entre 4-10°C/km para capa límite)

2. **Haz clic en "🚀 Iniciar Simulación"**

3. **Observa las fases del vuelo:**
   - **Fase 1 - Ascenso rápido ⬆️**: El CanSat sube rápidamente (transportado por globo/cohete/avioneta - no visible)
   - **Fase 2 - Descenso lento 🪂**: El paracaídas se despliega y el CanSat baja lentamente registrando datos

4. **Analiza los resultados:**
   - Las gráficas de temperatura y presión
   - El marcador del LCL (línea roja horizontal)
   - La condensación en el tubo (cuando T ≤ Td)
   - El panel de telemetría en tiempo real

5. **Usa "🔄 Reiniciar"** para probar otras condiciones

## 📚 Fundamento Científico

### ⚠️ Importante: Capa Límite Planetaria

A 600m de altitud estamos en la **capa límite planetaria** (planetary boundary layer, 0-2km), Esta capa tiene características especiales:
- El gradiente térmico puede variar entre **4-10°C/km** (no siempre 6.5°C/km)
- Está influenciada por la superficie terrestre
- Puede tener inversiones térmicas
- El comportamiento atmosférico es más variable

### Ecuaciones del simulador:

```
Punto de Rocío (Td):
  Td ≈ T₀ - ((100 - HR₀) / 5)

Lifting Condensation Level (LCL):
  LCL = (T₀ - Td) / (Γ / 1000)
  LCL ≈ 125 × (T₀ - Td)  [si Γ = 6.5°C/km]

Temperatura a altitud h:
  T(h) = T₀ - (Γ / 1000) × h
  donde Γ es el gradiente térmico en °C/km

Presión a altitud h:
  P(h) = P₀ × (1 - 0.0065×h/288.15)^5.255
```

### Fases del vuelo:

1. **Ascenso pasivo (rápido)**: El CanSat es transportado como carga en un globo/cohete/avioneta hasta ~600m
2. **Descenso controlado (lento)**: El paracaídas se despliega automáticamente y el CanSat desciende registrando datos continuamente
3. **Durante todo el vuelo**: El tubo sellado registra pasivamente la condensación cuando T ≤ Td


## 🎓 Uso Educativo

### Actividades sugeridas:

1. **Predicción pre-vuelo**: 
   - Los estudiantes miden las condiciones meteorológicas del día del lanzamiento
   - Introducen los datos en el simulador
   - Predicen si habrá condensación y a qué altura

2. **Exploración del gradiente térmico**: 
   - ¿Qué pasa si el gradiente es 4°C/km vs 10°C/km?
   - ¿Por qué puede variar el gradiente en la capa límite planetaria?
   - Investigar inversiones térmicas y su efecto en el LCL

3. **Validación post-vuelo**: 
   - Comparar la predicción del simulador con los datos reales del CanSat
   - ¿Coincidió el LCL calculado con la altura de condensación real?
   - Análisis de errores y factores no considerados

4. **Exploración de variables**: 
   - ¿Qué pasa si cambiamos la humedad de 50% a 90%?
   - ¿Cómo afecta la temperatura inicial al LCL?
   - ¿Cuál es la mínima humedad para garantizar condensación a 600m?

5. **Análisis de nubes reales**: 
   - Relacionar el LCL calculado con la altura observada de nubes cumuliformes
   - ¿Por qué las nubes estratiformes NO siguen el modelo LCL?

6. **Diseño experimental óptimo**: 
   - Los estudiantes ajustan condiciones para maximizar probabilidad de condensación
   - Planificar el mejor día/hora para el lanzamiento

## 🔧 Personalización

El simulador es un archivo HTML autocontenido. Puedes modificar:

- **Colores**: Busca los valores hexadecimales en el CSS
- **Velocidad de ascenso**: Cambia `ASCENT_SPEED` (línea ~494, por defecto 25ms)
- **Velocidad de descenso**: Cambia `DESCENT_SPEED` (línea ~495, por defecto 60ms)
- **Altitud máxima**: Cambia `MAX_ALTITUDE` (línea ~493)
- **Gradiente térmico por defecto**: Cambia el valor inicial del input

## 📱 Compatibilidad

- ✅ Chrome, Firefox, Safari, Edge (últimas versiones)
- ✅ Móviles iOS y Android
- ✅ No requiere instalación ni servidor
- ✅ Funciona offline (una vez cargado)

## 📊 Datos técnicos

- **Biblioteca de gráficas**: Chart.js 4.4.0 (CDN)
- **Tamaño**: ~25 KB
- **Dependencias**: Solo Chart.js (cargado desde CDN)
- **Navegadores soportados**: ES6+ (2015 en adelante)

## 🎨 Características Visuales

El simulador muestra:
- **Panel de control** con condiciones atmosféricas ajustables
- **Animación realista** del vuelo completo:
  - Ascenso rápido (CanSat sube velozmente - transportado por vehículo no visible)
  - Despliegue automático del paracaídas
  - Descenso lento con paracaídas visible
- **Fases claramente indicadas**: "⬆️ Ascenso Rápido" → "🪂 Descenso Lento" → "✅ Aterrizaje"
- **Dos gráficas interactivas** con datos en tiempo real
- **Telemetría en vivo** con indicador de fase actual
- **Marcador LCL** (línea roja) mostrando la altura teórica de base de nubes
- **Tubo de condensación** que cambia visualmente cuando condensa
- **Explicación científica** detallada con advertencia sobre capa límite planetaria

## 📝 Licencia

Este simulador es de uso educativo libre. Puedes modificarlo y compartirlo.

## 🤝 Contribuciones

Si mejoras el simulador:
1. Haz un fork del repositorio
2. Crea una rama con tu mejora
3. Envía un pull request

## 📧 Contacto

Proyecto educativo - CanSat 3º ESO
Departamento de Tecnología - IES Diego Velázquez

---

**¡Disfruta explorando la ciencia atmosférica!** 🌤️☁️🌧️
