# 🎮 Project Zomboid Translation Tool

Herramienta web para traducir archivos de Project Zomboid del inglés al español (España y Argentina).

[![Live Demo](https://img.shields.io/badge/demo-online-brightgreen)](https://pangolp.github.io/pz-translation-tool/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

## 🌐 Demo en Vivo

Accede a la herramienta aquí: **[https://pangolp.github.io/pz-translation-tool/](https://pangolp.github.io/pz-translation-tool/)**

## ✨ Características

- ✅ **Traducción Automática**: Sugerencias automáticas usando MyMemory Translation API
- ✅ **Detección de Límite de API**: Notifica cuando se alcanza el límite de uso y sugiere traducción manual
- ✅ **Capitalización Correcta**: Las traducciones siempre tienen solo la primera letra en mayúscula
- ✅ **Dos Dialectos**: Soporte para español de España (ES) y Argentina (AR)
- ✅ **Comparación de Traducciones**: Si subes un archivo parcialmente traducido, podrás comparar tu traducción con la sugerencia automática
- ✅ **Guardado Automático**: Tu progreso se guarda automáticamente en el navegador (localStorage)
- ✅ **Recuperación de Progreso**: Si cierras la pestaña, puedes continuar donde lo dejaste
- ✅ **Navegación Intuitiva**: Ve una traducción a la vez con contador de progreso
- ✅ **Sin Instalación**: Funciona 100% en el navegador
- ✅ **Descarga de Progreso**: Guarda tu trabajo en cualquier momento
- ✅ **Formato Preservado**: Mantiene el formato exacto de los archivos de Project Zomboid

## 🚀 Cómo Usar

### 1. Preparar tus Archivos

Los archivos de traducción de Project Zomboid tienen este formato:

```lua
NombreArchivo_EN = {
    Clave_1 = "Texto en inglés",
    Clave_2 = "Otro texto",
    -- Comentarios
}
```

**⚠️ Importante:** El archivo debe comenzar con el nombre en el formato `NombreArchivo_EN = {` para que la herramienta pueda detectar correctamente el nombre del archivo. Por ejemplo:
- ✅ `Attributes_EN = {` → Generará `Attributes_ES.txt`
- ✅ `RecipeGroups_EN = {` → Generará `RecipeGroups_ES.txt`
- ❌ `Items = {` → No se detectará correctamente

### 2. Proceso de Traducción

#### Opción A: Traducción desde Cero

1. **Abre la herramienta**: Visita [https://pangolp.github.io/pz-translation-tool/](https://pangolp.github.io/pz-translation-tool/)
2. **Sube el archivo EN**: Click en "Archivo EN (Obligatorio)" y selecciona tu archivo (ej: `Attributes_EN.txt`)
3. **Selecciona el idioma**: Elige entre:
   - **ES** - Español (España)
   - **AR** - Español (Argentina)
4. **Comienza**: Click en "Comenzar Traducción"
5. **Revisa cada traducción**:
   - La sugerencia aparecerá automáticamente en el campo de texto
   - Edita la traducción si es necesario
   - Click en "Siguiente →" para continuar
6. **Descarga el resultado**: Al terminar, descarga tu archivo `NombreArchivo_ES.txt` o `NombreArchivo_AR.txt`

#### Opción B: Continuar una Traducción Existente

1. **Sube el archivo EN**: Tu archivo original en inglés
2. **Sube el archivo ES/AR**: Tu traducción parcial (ej: `Attributes_ES.txt`)
3. **Selecciona el idioma**: ES o AR (se detecta automáticamente del archivo)
4. **Comienza**: La herramienta continuará desde donde lo dejaste
5. **Compara traducciones**: Si subes un archivo ES/AR, verás dos opciones:
   - **📄 Usar del Archivo**: Tu traducción anterior
   - **💡 Usar Sugerencia**: Nueva sugerencia automática
6. **Selecciona tu preferencia**: Click en el botón de la traducción que prefieras

### 3. Navegación y Guardado

- **Anterior/Siguiente**: Navega entre traducciones
- **Contador de Progreso**: Ve cuántas traducciones llevas completadas (ej: "5 de 12")
- **💾 Descargar Progreso**: Guarda tu trabajo en cualquier momento (genera un archivo `_progreso.txt`)
- **Barra de Progreso**: Visual en la parte superior
- **🔄 Guardado Automático**: Tu progreso se guarda automáticamente en el navegador cada vez que avanzas a la siguiente traducción

### 4. Recuperación de Progreso (LocalStorage)

La herramienta guarda automáticamente tu progreso en el navegador. Si cierras la pestaña accidentalmente o necesitas tomar un descanso:

1. **Vuelve a abrir la herramienta**
2. **Sube el mismo archivo EN**
3. **Selecciona el mismo idioma** (ES o AR)
4. **Aparecerá un mensaje**: "¡Progreso Guardado Encontrado!"
5. **Elige una opción**:
   - **🔄 Continuar Traducción**: Recupera tu progreso exactamente donde lo dejaste
   - **🆕 Empezar de Nuevo**: Borra el progreso guardado y empieza desde cero

**Nota importante**: El progreso se guarda por archivo y por idioma. Es decir, puedes tener guardados múltiples archivos simultáneamente:
- `Attributes_ES` (guardado por separado)
- `BodyParts_AR` (guardado por separado)
- `Items_ES` (guardado por separado)

### 5. Resultado Final

El archivo generado tendrá este formato:

```lua
NombreArchivo_ES = {
    Clave_1 = "Texto En Español",
    Clave_2 = "Otro Texto",
}
```

O para Argentina:

```lua
NombreArchivo_AR = {
    Clave_1 = "Texto En Español",
    Clave_2 = "Otro Texto",
}
```

## 📋 Formato de Archivos

### Archivo de Entrada (EN)

```lua
Attributes_EN = {
    Attributes_Type_None = "None",
    Attributes_Type_Quality = "Quality",
    Attributes_Type_Durability = "Durability",
}
```

### Archivo de Salida (ES)

```lua
Attributes_ES = {
    Attributes_Type_None = "Ninguno",
    Attributes_Type_Quality = "Calidad",
    Attributes_Type_Durability = "Durabilidad",
}
```

### Archivo de Salida (AR)

```lua
Attributes_AR = {
    Attributes_Type_None = "Ninguno",
    Attributes_Type_Quality = "Calidad",
    Attributes_Type_Durability = "Durabilidad",
}
```

## 🔧 Características Técnicas

- **Framework**: Vue.js 3
- **API de Traducción**: MyMemory Translation API (gratuita con límites de uso)
  - Límite aproximado: 5000 caracteres por día
  - Rate limit: requests por hora (variable)
  - Manejo automático de errores 429 (Too Many Requests)
- **Persistencia**: LocalStorage del navegador para guardado automático
- **Formato de Salida**: 
  - Sangría de 4 espacios
  - Comas al final de cada línea
  - Solo primera letra en mayúscula (ej: "Hola como andas", no "Hola Como Andas")
  - Nombres de archivo preservados correctamente (ej: `RecipeGroups_ES.txt`)
- **Compatibilidad**: Todos los navegadores modernos (Chrome, Firefox, Safari, Edge)
- **Sin Backend**: Todo funciona en el navegador
- **Sin Dependencias Externas**: No requiere instalación ni configuración

## 📝 Ejemplos de Uso

### Ejemplo 1: Traducir desde Cero

```
1. Archivo: Attributes_EN.txt
2. Idioma: ES
3. Resultado: Attributes_ES.txt
```

### Ejemplo 2: Continuar Traducción

```
1. Archivo EN: BodyParts_EN.txt
2. Archivo AR: BodyParts_AR.txt (50% traducido)
3. Idioma: AR (detectado automáticamente)
4. Resultado: BodyParts_AR.txt (100% traducido)
```

### Ejemplo 3: Comparar Traducciones

```
1. Archivo EN: Items_EN.txt
2. Archivo ES: Items_ES.txt (traducción existente)
3. La herramienta muestra:
   - Tu traducción anterior
   - Nueva sugerencia automática
4. Eliges cuál usar
```

## 🎯 Casos de Uso

- ✅ Traducir mods de Project Zomboid
- ✅ Actualizar traducciones existentes
- ✅ Revisar y mejorar traducciones automáticas
- ✅ Mantener consistencia en traducciones
- ✅ Trabajo colaborativo (compartir archivos de progreso)

## 💡 Tips y Mejores Prácticas

1. **El guardado es automático**: No necesitas hacer nada especial, tu progreso se guarda automáticamente cada vez que avanzas
2. **Usa el mismo navegador**: El progreso se guarda en el navegador que estás usando, así que usa siempre el mismo
3. **No limpies el caché**: Si limpias los datos del navegador, perderás el progreso guardado
4. **Descarga periódicamente**: Aunque hay guardado automático, es buena idea descargar el progreso cada cierto tiempo por seguridad
5. **Trabaja en sesiones cortas**: Para evitar alcanzar el límite de la API, considera traducir en bloques de 50-100 entradas
6. **Ten paciencia con los límites**: Si alcanzas el límite de la API, puedes continuar manualmente o esperar unos minutos
7. **Revisa las sugerencias**: La traducción automática es buena, pero siempre revisa el contexto del juego
8. **Mantén consistencia**: Si traduces varios archivos, usa el mismo dialecto (ES o AR)
9. **Edita cuando sea necesario**: Las sugerencias son un punto de partida, ajústalas al contexto del juego

## ❓ Preguntas Frecuentes (FAQ)

### ¿Necesito instalar algo?
No, la herramienta funciona 100% en el navegador. Solo necesitas acceder a la URL.

### ¿Es gratis?
Sí, completamente gratuita y sin límites de uso.

### ¿Funciona sin internet?
Necesitas internet para cargar la herramienta y para las sugerencias automáticas de traducción. El guardado en localStorage funciona offline.

### ¿Puedo traducir varios archivos a la vez?
No simultáneamente, pero puedes traducir un archivo, descargarlo, y luego empezar con otro. El progreso de cada archivo se guarda por separado.

### ¿Qué pasa si el archivo tiene muchas entradas?
No hay límite. Puedes traducir archivos con cientos o miles de entradas. El progreso se guarda automáticamente.

### ¿Puedo usar esto para otros juegos?
Sí, si usan el mismo formato de archivos Lua con estructura `NombreArchivo_EN = { clave = "valor" }`

### ¿Las traducciones son perfectas?
No, son sugerencias automáticas. Siempre debes revisarlas y editarlas según el contexto específico del juego.

### ¿Puedo compartir mi progreso con otros?
Sí, usa el botón "💾 Descargar Progreso" y comparte el archivo generado. Otros pueden subirlo como archivo ES/AR para continuar.

### ¿Cómo borro mi progreso guardado?
Cuando completas una traducción o eliges "Empezar de Nuevo", el progreso se borra automáticamente. También puedes limpiar los datos del navegador manualmente.

### ¿Funciona en móvil?
Sí, funciona en navegadores móviles, aunque la experiencia es mejor en desktop debido al tamaño de pantalla.

### ¿Qué hago si aparece "Límite de API Alcanzado"?
Esto significa que se alcanzó el límite de uso gratuito de MyMemory. Puedes:
1. Continuar traduciendo manualmente (el texto está disponible en inglés)
2. Esperar 5-10 minutos y recargar la página
3. Descargar tu progreso y continuar más tarde
El guardado automático preservará tu trabajo.

### ¿Hay límite de traducciones por día?
La API gratuita de MyMemory tiene límites de uso (aproximadamente 5000 caracteres por día). Si alcanzas el límite, puedes continuar manualmente o esperar hasta el día siguiente. Tu progreso se guarda automáticamente.

## 🐛 Solución de Problemas

### La traducción no aparece en el campo de texto
- **Límite de API alcanzado**: MyMemory tiene un límite de uso gratuito. Si ves el mensaje "⏱️ Límite de API Alcanzado", espera unos minutos (usualmente 5-10 minutos) antes de continuar
- **Solución temporal**: Puedes continuar traduciendo manualmente mientras esperas. Tu progreso se guarda automáticamente
- Verifica que el archivo EN esté correctamente formateado
- Asegúrate de tener conexión a internet (necesaria para las sugerencias)
- Abre la consola del navegador (F12) para ver si hay errores adicionales

### El archivo descargado tiene un nombre incorrecto (ejemplo: "_ES.txt")
- Asegúrate de que el archivo EN comience con `NombreArchivo_EN = {`
- Verifica que no haya espacios o caracteres especiales al inicio del archivo
- El formato debe ser exactamente: `Attributes_EN = {` (sin espacios antes)

### El archivo descargado no tiene el formato correcto
- Verifica que el archivo EN original tenga el formato correcto de Lua
- Asegúrate de completar todas las traducciones antes de descargar
- Revisa que las comillas estén correctamente cerradas en el archivo original

### No puedo continuar una traducción
- Verifica que el archivo ES/AR tenga el mismo formato que el EN
- Asegúrate de que las claves coincidan entre ambos archivos
- El archivo ES/AR debe comenzar con `NombreArchivo_ES = {` o `NombreArchivo_AR = {`

### No aparece el mensaje de "Progreso Guardado"
- Asegúrate de usar el mismo navegador
- Verifica que el nombre del archivo y el idioma sean exactamente los mismos
- Comprueba que las cookies/localStorage estén habilitadas en tu navegador
- Revisa la consola del navegador (F12) para ver si hay errores

### Perdí mi progreso
- Si limpiaste el caché del navegador, el progreso guardado se habrá eliminado
- Usa el botón "💾 Descargar Progreso" regularmente como respaldo
- Considera usar el modo incógnito solo si NO quieres guardar el progreso
- El progreso se guarda por archivo + idioma, no globalmente

### La capitalización no es correcta
- La herramienta capitaliza solo la primera letra de cada traducción
- Ejemplo correcto: "Hola como andas" (no "Hola Como Andas")
- Si necesitas mayúsculas en medio de la frase, edita manualmente la traducción

### Las traducciones automáticas no son precisas
- MyMemory es una API de traducción general, no específica de videojuegos
- Siempre revisa y edita las traducciones según el contexto del juego
- Puedes escribir tu propia traducción desde cero si la sugerencia no es adecuada

### Límite de uso de la API alcanzado
- **Qué significa**: MyMemory API tiene límites de uso gratuito (generalmente 5000 caracteres por día o límite por hora)
- **Cuánto esperar**: Usualmente 5-10 minutos para límites por hora, o hasta el día siguiente para límites diarios
- **Qué hacer**:
  1. Continúa traduciendo manualmente (tu progreso se guarda)
  2. Descarga tu progreso actual con "💾 Descargar Progreso"
  3. Espera el tiempo indicado en el mensaje
  4. Vuelve más tarde y carga tu progreso guardado
- **Prevención**: Si tienes muchas entradas, considera trabajar en sesiones más cortas

## 📄 Licencia

MIT License - Libre de usar, modificar y distribuir.

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Por favor:

1. Fork el repositorio
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 👨‍💻 Autor

**pangolp**

- GitHub: [@pangolp](https://github.com/pangolp)

## 🙏 Agradecimientos

- MyMemory Translation API por proveer traducciones gratuitas
- Comunidad de Project Zomboid
- Vue.js por el framework

## 📮 Contacto y Soporte

Si encuentras algún bug o tienes sugerencias, por favor abre un [Issue](https://github.com/pangolp/pz-translation-tool/issues) en GitHub.

---

⭐ Si esta herramienta te resulta útil, considera darle una estrella en GitHub!

## 📋 Changelog

### Versión 1.0.1 (Enero 2025)
- ✨ Agregada detección de límite de uso de API (Error 429)
- ✨ Mensajes informativos cuando se alcanza el límite de MyMemory API
- 🐛 Mejorado manejo de errores con información sobre tiempo de espera
- 📝 Documentación actualizada con soluciones para límites de API

### Versión 1.0.0 (Diciembre 2024)
- ✅ Traducción automática con MyMemory API
- ✅ Guardado automático en localStorage
- ✅ Recuperación de progreso
- ✅ Soporte para español de España (ES) y Argentina (AR)
- ✅ Comparación entre traducción existente y sugerencia
- ✅ Capitalización correcta (solo primera letra)
- ✅ Navegación intuitiva con contador de progreso
- ✅ Descarga manual de progreso
- ✅ Validaciones y manejo de errores mejorado

### Correcciones
- 🐛 Corregido bug donde el nombre del archivo no se guardaba en localStorage
- 🐛 Corregido formato de capitalización (ahora solo primera letra en mayúscula)
- 🐛 Agregado fallback para detectar nombre de archivo desde el nombre del archivo subido
- 🐛 Validaciones adicionales para evitar archivos sin nombre
