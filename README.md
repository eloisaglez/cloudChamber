# 🛰️ Simulador CanSat: Cloud Chamber

Simulador interactivo para el proyecto CanSat "Cloud Chamber" - Verificación Experimental de la Formación de Nubes mediante Condensación Atmosférica.

## 🎯 Características

- **Simulación en tiempo real** del ascenso del CanSat hasta 600m
- **Gráficas dinámicas** de temperatura y presión vs altitud
- **Visualización animada** del CanSat con tubo de condensación
- **Cálculo automático** del LCL (Lifting Condensation Level)
- **Predicción** de si habrá condensación o no
- **Animación de condensación** cuando se alcanza el punto de rocío
- **Responsive** - funciona en móviles, tablets y ordenadores

## 🚀 Cómo usar

1. Introduce las condiciones iniciales:
   - Temperatura inicial (T₀) en °C
   - Humedad Relativa (HR₀) en %
   - Presión inicial (P₀) en hPa

2. Haz clic en "🚀 Simular Ascenso"

3. Observa:
   - La animación del CanSat ascendiendo
   - Las gráficas de temperatura y presión
   - El marcador del LCL (línea roja)
   - La condensación en el tubo cuando se alcanza el punto de rocío

4. Usa "🔄 Reiniciar" para probar otras condiciones

## 📚 Fundamento Científico

El simulador reproduce las ecuaciones del CDR:

```
Punto de Rocío (Td):
  Td ≈ T₀ - ((100 - HR₀) / 5)

Lifting Condensation Level (LCL):
  LCL = 125 × (T₀ - Td)  [metros]

Temperatura a altitud h:
  T(h) = T₀ - 0.0065 × h

Presión a altitud h:
  P(h) = P₀ × (1 - 0.0065×h/288.15)^5.255
```

## 🌐 Cómo publicar en GitHub Pages

### Opción 1: Repositorio nuevo

1. Crea un nuevo repositorio en GitHub llamado `cansat-simulator`

2. Sube el archivo `cansat_simulator.html` y renómbralo a `index.html`:
   ```bash
   git clone https://github.com/tu-usuario/cansat-simulator.git
   cd cansat-simulator
   cp cansat_simulator.html index.html
   git add index.html
   git commit -m "Add CanSat simulator"
   git push
   ```

3. Ve a Settings → Pages → Source → selecciona `main` branch

4. Tu simulador estará en: `https://tu-usuario.github.io/cansat-simulator/`

### Opción 2: Repositorio existente

1. Crea una carpeta `docs` en tu repositorio

2. Copia `cansat_simulator.html` como `docs/index.html`

3. En Settings → Pages → Source → selecciona `main` branch y `/docs` folder

4. Estará en: `https://tu-usuario.github.io/nombre-repositorio/`

### Opción 3: Más rápido (interfaz web)

1. Ve a tu repositorio en GitHub

2. Haz clic en "Add file" → "Upload files"

3. Sube `cansat_simulator.html` y renómbralo a `index.html`

4. Activa GitHub Pages en Settings → Pages

## 🎓 Uso Educativo

### Actividades sugeridas:

1. **Predicción pre-vuelo**: Los estudiantes introducen las condiciones meteorológicas del día del lanzamiento y predicen si habrá condensación

2. **Exploración de variables**: ¿Qué pasa si cambiamos la humedad? ¿Y la temperatura?

3. **Validación post-vuelo**: Comparar la predicción del simulador con los datos reales del CanSat

4. **Diseño de experimento**: Los estudiantes ajustan condiciones para garantizar condensación

5. **Análisis de nubes**: Relacionar el LCL calculado con la altura observada de nubes reales

## 🔧 Personalización

El simulador es un archivo HTML autocontenido. Puedes modificar:

- **Colores**: Busca los valores hexadecimales en el CSS
- **Velocidad de simulación**: Cambia `SIMULATION_SPEED` (línea ~500)
- **Altitud máxima**: Cambia `MAX_ALTITUDE` (línea ~499)
- **Gradiente térmico**: Cambia `LAPSE_RATE` (línea ~501)

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

## 🎨 Capturas

El simulador muestra:
- Panel de control con inputs
- Visualización animada del CanSat
- Dos gráficas interactivas
- Telemetría en tiempo real
- Explicación científica

## 📝 Licencia

Este simulador es de uso educativo libre. Puedes modificarlo y compartirlo.

## 🤝 Contribuciones

Si mejoras el simulador:
1. Haz un fork del repositorio
2. Crea una rama con tu mejora
3. Envía un pull request

## 📧 Contacto

Proyecto educativo - CanSat 3º ESO
Departamento de Tecnología

---

**¡Disfruta explorando la ciencia atmosférica!** 🌤️☁️🌧️
