# IPTV Adapter Conversion

 Herramienta web para **limpiar, normalizar y convertir lotes de URLs IPTV** directamente en el navegador.

 La aplicación está diseñada para trabajar con el texto introducido por el usuario y generar URLs de salida en formatos **TS**, **HLS** o ambos, sin realizar validaciones remotas ni autenticaciones contra servidores IPTV.

---

 ## ✨ Características

 - Procesamiento completamente local en el navegador.
- No requiere backend.
- No requiere API externa.
- No realiza autenticación contra servidores IPTV.
- No comprueba disponibilidad de servidores.
- Compatible con `HTTP` y `HTTPS`.
- Detección automática de URLs.
- Limpieza de texto adicional alrededor de las URLs.
- Eliminación de duplicados.
- Detección de URLs inválidas.
- Soporte para:
  - `player_api.php`
  - `get.php`
  - dominios con puerto
  - URLs `http://`
  - URLs `https://`
- Generación de:
  - `TS`
  - `HLS`
  - `TS + HLS`
- Detección de enlaces que ya contienen `output=ts` o `output=hls`.
- Búsqueda por:
  - servidor
  - usuario
  - contraseña
  - formato
  - estado
  - URL
- Filtros por formato.
- Filtros por estado.
- Selección individual de resultados.
- Selección masiva.
- Copiado individual.
- Copiado de selección.
- Copiado de todos los resultados.
- Visualización del resultado como TXT.
- Descarga de resultados en `.txt`.
- Eliminación individual mediante selección.
- Vaciar todos los resultados.
- Estadísticas en tiempo real.
- Diseño responsive.
- Interfaz oscura basada en GitHub Dark.
- Notificaciones Toast.
- Modal para visualizar el TXT.
- Atajo `Ctrl + Enter` / `Cmd + Enter` para procesar.
- Atajo `Escape` para cerrar el visor TXT.

---

 ## 🖥️ Interfaz

 La interfaz utiliza un sistema visual oscuro inspirado en superficies tipo GitHub Dark:

 - Fondo `#05070a`
- Sidebar `#0d1117`
- Cards `#161b22`
- Bordes `#30363d`
- Azul principal `#3b82f6`
- Verde `#10b981`
- Rojo `#ef4444`
- Amarillo `#f59e0b`
- Tipografía `Inter`
- Tipografía monoespaciada `Fira Code`

 El CSS está organizado alrededor de variables reutilizables para mantener una identidad visual consistente.

---

 ## 🚀 Uso

 No es necesario instalar Node.js, Python ni ningún servidor.

 Simplemente abre:

```
index.html
```

 en un navegador moderno.

 También puedes alojarlo directamente en GitHub Pages.

---

 ## 📥 Entrada

 La herramienta acepta lotes de texto con URLs IPTV.

 Ejemplos:

```
http://example.com/player_api.php?username=user&password=pass
```

```
https://example.com/get.php?username=user&password=pass
```

 También puede detectar URLs dentro de líneas que contengan texto adicional.

 Por ejemplo:

```
Canal 1: http://example.com/get.php?username=user&password=pass
```

 La herramienta intenta extraer únicamente la URL.

---

 ## 🧹 Limpieza automática

 Antes de generar los resultados, el sistema:

 1. Divide el texto por líneas.
2. Busca URLs explícitas `http://` o `https://`.
3. Busca dominios y direcciones con puerto.
4. Normaliza las URLs.
5. Elimina caracteres residuales.
6. Ignora determinadas líneas de texto que no contienen URLs útiles.
7. Detecta duplicados.
8. Identifica entradas inválidas.

 Las URLs válidas se almacenan internamente como líneas limpias.

---

 ## 🔄 Conversión

 La aplicación analiza los parámetros:

```
username
password
```

 de la URL.

 Cuando encuentra una URL compatible, genera una salida basada en:

```
/get.php
```

 con los parámetros:

```
username
password
type=m3u_plus
output=ts
```

 o:

```
username
password
type=m3u_plus
output=hls
```

 ### Ejemplo

 Entrada:

```
http://example.com/player_api.php?username=user&password=pass
```

 Salida TS:

```
http://example.com/get.php?username=user&password=pass&type=m3u_plus&output=ts
```

 Salida HLS:

```
http://example.com/get.php?username=user&password=pass&type=m3u_plus&output=hls
```

---

 ## ⚙️ Modos de generación

 Desde **Configuración → Generación** se puede seleccionar:

 ### TS + HLS

 Genera ambas variantes.

```
output=ts
output=hls
```

 ### Solo TS

 Genera únicamente:

```
output=ts
```

 ### Solo HLS

 Genera únicamente:

```
output=hls
```

---

 ## 🔐 Procesamiento local

 El proyecto está diseñado para realizar el procesamiento dentro del navegador.

 La aplicación **no realiza**:

 - autenticación contra servidores IPTV;
- comprobación de credenciales;
- comprobación de cuentas;
- comprobación de servidores;
- validación de disponibilidad;
- solicitudes de reproducción;
- consultas remotas de estado;
- conexión con una API IPTV.

 El procesamiento principal se realiza mediante JavaScript del lado del cliente.

 > **Importante:** aunque el procesamiento de esta aplicación es local, el navegador puede cargar recursos externos utilizados por la interfaz, como Font Awesome o Google Fonts.

---

 ## 📊 Estadísticas

 La interfaz muestra:

 | Estadística | Descripción |
| --- | --- |
| Detectadas | URLs válidas detectadas durante la limpieza |
| Resultados | Resultados generados |
| Ignoradas | Líneas ignoradas durante el procesamiento |
| Inválidas | Entradas que no pudieron convertirse en URLs válidas |
| Duplicadas | URLs o resultados duplicados |
| Visibles | Resultados que cumplen los filtros actuales |

---

 ## 🔎 Búsqueda y filtros

 La tabla incluye un buscador capaz de localizar resultados por:

 - servidor;
- usuario;
- contraseña;
- formato;
- estado;
- URL.

 También existen filtros independientes:

```
Todos los formatos
TS
HLS
```

 y:

```
Todos los estados
Convertidos
Ya convertidos
```

---

 ## 📋 Gestión de resultados

 Cada resultado puede seleccionarse mediante su checkbox.

 Las acciones disponibles incluyen:

 - Copiar selección
- Seleccionar todo
- Eliminar selección
- Ver TXT
- Copiar todo
- Descargar TXT
- Vaciar resultados

 Cada fila también incluye un botón para copiar individualmente su URL.

---

 ## 📄 Exportación TXT

 Los resultados pueden visualizarse mediante el visor integrado:

```
Ver TXT
```

 También pueden copiarse o descargarse directamente.

 El archivo generado utiliza el nombre:

```
iptv-results.txt
```

---

 ## ⌨️ Atajos de teclado

 ### Procesar lote

```
Ctrl + Enter
```

 En macOS:

```
Cmd + Enter
```

 ### Cerrar modal

```
Escape
```

---

 ## 📁 Estructura recomendada

 Para una versión sencilla del proyecto:

```
iptv-adapter-conversion/
│
├── index.html
├── README.md
├── LICENSE
└── .gitignore
```

 Actualmente la aplicación puede mantenerse completamente dentro de:

```
index.html
```

 El HTML contiene:

 - estructura de interfaz;
- CSS;
- JavaScript;
- lógica de procesamiento;
- filtros;
- tabla;
- modal;
- Toasts;
- exportación TXT.

---

 ## 🎨 Sistema visual

 El proyecto utiliza variables CSS centralizadas:

```
:root {
  --bg: #05070a;
  --sidebar: #0d1117;
  --card: #161b22;
  --card-soft: #0d1117;

  --accent: #3b82f6;
  --accent-hover: #60a5fa;
  --accent-glow: rgba(59, 130, 246, .42);

  --border: #30363d;
  --border-soft: rgba(48, 54, 61, .65);

  --text: #f0f6fc;
  --text-soft: #c9d1d9;
  --text-dim: #8b949e;

  --success: #10b981;
  --danger: #ef4444;
  --warning: #f59e0b;
  --info: #0ea5e9;
}
```

 Esto permite reutilizar el lenguaje visual del proyecto en futuras interfaces de Nexaia sin tener que copiar todo el CSS.

---

 ## 🧩 Componentes principales

 El sistema visual contiene componentes reutilizables:

```
.btn
.btn-primary
.btn-success
.btn-danger
.btn-warning

.card

.stat-card

.format-card

.badge

.toolbar

.notice

.modal

.toast

.table-container
```

 También se utilizan estados visuales:

```
:hover
:focus
:focus-visible
:active
.show
.visible
```

---

 ## 📱 Responsive

 La interfaz se adapta a diferentes tamaños de pantalla.

 ### Desktop

 Incluye:

 - sidebar;
- header;
- estadísticas;
- paneles;
- tabla completa.

 ### Tablet

 La distribución reduce el ancho del sidebar y reorganiza las estadísticas.

 ### Mobile

 La interfaz:

 - oculta el sidebar;
- convierte el header en sticky;
- reorganiza los controles;
- convierte la toolbar en una columna;
- adapta los botones;
- adapta las tarjetas;
- mantiene la tabla con scroll horizontal.

---

 ## 🛡️ Privacidad

 El proyecto no incorpora un backend propio.

 Los datos introducidos en el campo de entrada son procesados mediante JavaScript en el navegador.

 No se almacenan automáticamente en una base de datos.

 No se envían deliberadamente a un servidor propio de la aplicación.

 Sin embargo, los usuarios deben revisar siempre el código y los recursos externos utilizados antes de introducir información sensible.

---

 ## 🌐 Dependencias externas

 La interfaz utiliza recursos externos para iconos y fuentes:

 ### Font Awesome

```
https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.7.0/css/all.min.css
```

 ### Google Fonts

```
Inter
Fira Code
```

 ### Favicon

 El HTML actual utiliza un icono alojado externamente.

 Para una versión completamente autocontenida se recomienda descargar estos recursos y servirlos localmente desde el propio repositorio.

---

 ## 🔧 Desarrollo

 El proyecto está construido con tecnologías web estándar:

```
HTML5
CSS3
JavaScript
```

 No requiere framework.

 No requiere bundler.

 No requiere compilación.

 No requiere backend.

 Esto permite modificar el proyecto directamente desde:

```
index.html
```

---

 ## 🧪 Compatibilidad

 Se recomienda utilizar una versión actualizada de:

 - Google Chrome
- Microsoft Edge
- Mozilla Firefox
- Safari

 El proyecto utiliza APIs modernas del navegador como:

```
URL
URLSearchParams
navigator.clipboard
Blob
URL.createObjectURL
```

---

 ## ⚠️ Consideraciones

 Esta herramienta es un procesador de texto y URLs ejecutado localmente.

 No determina si una cuenta IPTV es válida.

 No determina si un servidor está activo.

 No realiza comprobaciones de acceso.

 No intenta conectarse al servidor para verificar resultados.

 La generación de una URL no implica que dicha URL sea accesible o funcional.

---

 ## 🗂️ Estado del proyecto

 Proyecto orientado a procesamiento local de lotes.

 ### Implementado

 - [x] Interfaz oscura
- [x] Responsive
- [x] Procesamiento local
- [x] Limpieza de URLs
- [x] Detección de duplicados
- [x] Detección de inválidos
- [x] Conversión TS
- [x] Conversión HLS
- [x] Filtros
- [x] Búsqueda
- [x] Selección múltiple
- [x] Copiado
- [x] Exportación TXT
- [x] Modal TXT
- [x] Estadísticas
- [x] Toasts
- [x] Atajos de teclado

---

 ## 📝 Licencia

 Este proyecto se distribuye bajo la licencia MIT.

 Consulta el archivo:

```
LICENSE
```

 para conocer los términos completos de uso, modificación y distribución.

---

 ## Contacto

Lead Developer: dZh0ni — Telegram: [@dzh0ni_Dev](https://t.me/dzh0ni_Dev/)

 Proyecto:

```
IPTV Adapter Conversion
```

 Motor:

```
Local Processing Engine
```

---

 ## ⭐ Contribuciones

 Las mejoras y correcciones son bienvenidas.

 Antes de realizar cambios importantes se recomienda:

 1. Crear una rama independiente.
2. Mantener la lógica de procesamiento local.
3. Evitar introducir validaciones remotas innecesarias.
4. Mantener el sistema visual existente.
5. Comprobar el comportamiento responsive.
6. Verificar que las funciones de copia y descarga continúen funcionando.
7. Actualizar este `README.md` cuando se agreguen funcionalidades relevantes.

---

 ## 📌 Principio del proyecto

 > **Local Processing · Simple · Portable · No Backend**

 El objetivo es mantener una herramienta pequeña, portable y fácil de revisar, donde la transformación de los datos ocurra directamente en el navegador.
 