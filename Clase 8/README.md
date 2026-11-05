# 📚 Clase 8: Análisis Geográfico y Capas Vectoriales en QGIS

---

## 📌 Resumen de la Clase

Durante esta clase profundizamos en el uso de **QGIS** para el procesamiento de imágenes satelitales en formato **GeoTIFF** y la creación de capas vectoriales (tanto de polígonos como de puntos de interés). Como caso de estudio práctico, realizamos un análisis comparativo de la cobertura nival en la Cordillera de los Andes centrales (Glaciar de las Lágrimas, Malargüe, Mendoza), evaluando el sitio del histórico accidente aéreo de los rugbiers uruguayos de 1972.

---

## 🛰️ Introducción a QGIS y Imágenes GeoTIFF

- **QGIS:** Sistema de Información Geográfica (SIG) de código abierto y distribución libre.
- **Formato GeoTIFF (`.tif`, `.tiff`):** Estándar geoespacial que incorpora metadatos de georreferenciación directamente en las cabeceras del archivo, facilitando el análisis ráster sin requerir archivos auxiliares externos.
- **Fuente de Datos (Copernicus / Sentinel-2):** Descarga de imágenes multiespectrales de alta resolución desde el [Copernicus Browser](https://browser.dataspace.copernicus.eu/?zoom=13&lat=-34.75442&lng=-70.19148&themeId=DEFAULT-THEME&visualizationUrl=U2FsdGVkX1%2FHsrbyk%2FWvmQ9gPexLBvTGhRVNxdCY%2B9Im3cOwhl%2FNqGggu0kR5XOE0xYqiPnxHpaEwxLmMctFbiPxDd5guLHDift0GHgHfwa2K0DhyqlUmcNQgJiTQv5Y&datasetId=S2_L2A_CDAS&demSource3D=%22MAPZEN%22&cloudCoverage=30&dateMode=SINGLE&panel=layers) aplicando filtros de nubosidad menor al 10%.

---

## 📐 Creación de Capas Vectoriales y Medición de Áreas

Para obtener mediciones métricas exactas en metros cuadrados ($m^2$), se configuró el proyecto bajo un Sistema de Referencia de Coordenadas Proyectado:
- **SRC:** UTM Zona 19S / WGS 84 (EPSG:32719).

---

### 🔗 Enlaces:
- 📄 [**Informe Técnico de Investigación y Análisis SIG (PDF)**](https://raw.githubusercontent.com/allaymaria/TyHM2/main/Clase%208/AN%C3%81LISIS%20GEOGR%C3%81FICO%20CON%20QGIS.pdf)
- 📦 [**ANÁLISIS GEOGRÁFICO CON QGIS (ZIP)**](https://raw.githubusercontent.com/allaymaria/TyHM2/main/Clase%208/AN%C3%81LISIS%20GEOGR%C3%81FICO%20CON%20QGIS.zip)
- 🗜️ [**MEDICION NIEVE 2 (RAR)**](https://raw.githubusercontent.com/allaymaria/TyHM2/main/Clase%208/MEDICION%20NIEVE%202.rar)
- **Digitalización Manual:** Creación de una capa vectorial de tipo polígono en un archivo *GeoPackage*, trazando vértice por vértice el contorno de la superficie nival.

