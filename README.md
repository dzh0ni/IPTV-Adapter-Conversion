IPTV Adapter Conversion

:information_source: Descripción

IPTV Adapter Conversion es una herramienta web para limpiar, procesar y convertir lotes de enlaces IPTV directamente desde el navegador.

El procesamiento se realiza localmente mediante JavaScript, sin necesidad de una API externa.

:gear: Características

Procesamiento de lotes de URLs.

Limpieza automática de enlaces.

Detección de URLs duplicadas.

Detección de entradas inválidas.

Conversión a formato TS.

Conversión a formato HLS.

Conservación de enlaces que ya contienen output=ts o output=hls.

Búsqueda de resultados.

Filtros por formato y estado.

Selección individual o múltiple.

Copiar resultados.

Descargar resultados en formato TXT.

Visualización del resultado TXT.

Estadísticas del procesamiento.

Interfaz responsive.

:arrows_counterclockwise: Conversión

La herramienta permite generar:

TS
output=ts

HLS
output=hls


También permite seleccionar:

TS + HLS
Solo TS
Solo HLS

:page_facing_up: Entrada

La aplicación acepta enlaces como:

http://servidor:puerto/player_api.php?username=usuario&password=clave

http://servidor:puerto/get.php?username=usuario&password=clave


También reconoce enlaces HTTP y HTTPS.

:computer: Uso

Descarga o clona el proyecto:

git clone https://github.com/dzh0ni/IPTV-Adapter-Conversion.git


Abre:

index.html


Pega el lote de enlaces en el área ENTRADA / LOTE, selecciona el protocolo y el tipo de generación y pulsa:

Procesar lote

Los resultados aparecerán en la tabla.

Desde ahí puedes:

Copiar una URL.

Seleccionar varias URLs.

Copiar la selección.

Copiar todos los resultados.

Ver los resultados TXT.

Descargar el TXT.

Eliminar resultados.

:lock: Procesamiento local

El procesamiento se realiza dentro del navegador.

La aplicación no realiza:

Validación de cuentas.

Autenticación.

Comprobación de servidores.

Comprobación de disponibilidad.

Solicitudes automáticas a servidores IPTV.

:art: Interfaz

La interfaz utiliza:

HTML5

CSS3

JavaScript

Inter

Fira Code

Font Awesome

Diseño oscuro basado en superficies tipo GitHub Dark, con acentos azules, estados de color y componentes adaptados para escritorio y dispositivos móviles.

:balance_scale: Licencia

Este proyecto se distribuye bajo la licencia MIT.

Consulta el archivo LICENSE para conocer los términos completos.

:star2: Créditos

IPTV Adapter Conversion

Desarrollado por dZh0ni.

:email: Contacto

:busts_in_silhouette: dZh0ni: Telegram

<p align="center">

☆ dZh0ni ☆

</p>