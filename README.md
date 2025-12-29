# 🎮 Project Zomboid Translation Tool

Herramienta web para traducir archivos de Project Zomboid del inglés al español (España y Argentina).

[![Live Demo](https://img.shields.io/badge/demo-online-brightgreen)](https://pangolp.github.io/pz-translation-tool/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

## 🌐 Demo en Vivo

Accede a la herramienta aquí: **[https://pangolp.github.io/pz-translation-tool/](https://pangolp.github.io/pz-translation-tool/)**

## ✨ Características

- ✅ **Traducción Automática**: Sugerencias automáticas usando MyMemory Translation API
- ✅ **Title Case Automático**: Las traducciones siempre tienen la primera letra en mayúscula
- ✅ **Dos Dialectos**: Soporte para español de España (ES) y Argentina (AR)
- ✅ **Comparación de Traducciones**: Si subes un archivo parcialmente traducido, podrás comparar tu traducción con la sugerencia automática
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

### 4. Resultado Final

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
- **API de Traducción**: MyMemory Translation API (gratuita, sin límites)
- **Formato de Salida**: 
  - Sangría de 4 espacios
  - Comas al final de cada línea
  - Title Case automático (Primera Letra En Mayúscula)
- **Compatibilidad**: Todos los navegadores modernos
- **Sin Backend**: Todo funciona en el navegador

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

1. **Guarda tu progreso frecuentemente**: Usa el botón "💾 Descargar Progreso" cada 10-20 traducciones
2. **Revisa las sugerencias**: La traducción automática es buena, pero siempre revisa el contexto del juego
3. **Usa archivos de progreso**: Si no puedes terminar en una sesión, descarga el progreso y continúa después
4. **Mantén consistencia**: Si traduces varios archivos, usa el mismo dialecto (ES o AR)
5. **Edita cuando sea necesario**: Las sugerencias son un punto de partida, ajústalas al contexto del juego

## 🐛 Solución de Problemas

### La traducción no aparece en el campo de texto
- Verifica que el archivo EN esté correctamente formateado
- Asegúrate de tener conexión a internet (necesaria para las sugerencias)

### El archivo descargado no tiene el formato correcto
- Verifica que el archivo EN original tenga el formato correcto de Lua
- Asegúrate de completar todas las traducciones antes de descargar

### No puedo continuar una traducción
- Verifica que el archivo ES/AR tenga el mismo formato que el EN
- Asegúrate de que las claves coincidan entre ambos archivos

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
