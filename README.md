# Auditor a ASG y Refactorización Sostenible por López Alonso Marco
## Inventario y Dimensión Ambiental (A):
### 1 Medición inicial: 
Para esta actividad he elegido la página web de una cafetería/bar que hay al lado de donde estudio, llamada Cafetería Bar Marbella.
Para comenzar voy a utilizar las herramientas gratuitas como Website Carbon Calculator o Lighthouse (pestaña de rendimiento en Chrome/Edge) para obtener la huella de carbono estimada por visita.
El cual me da estos altísimos resultados:
<img width="1232" height="691" alt="image" src="https://github.com/user-attachments/assets/bd020265-c1e0-4952-b4ba-f0f025c47c81" />

### 2 Identificación de Bloatware:
Imágenes principales sin optimizar: El recurso individual más pesado es la imagen de fondo de la cabecera principal (el banner hero que muestra el local/terraza) y las imágenes destacadas de los posts del blog (como la imagen de la oferta de cubatas o de la terraza). Estas imágenes están subidas en formatos tradicionales de alta resolución (como .jpg o .png) en lugar de formatos modernos comprimidos como .webp o .avif. En total, el conjunto de imágenes de la página principal supera con creces los 2.5 MB - 3 MB, lo que supone la inmensa mayoría del peso de la web.

Archivos JavaScript de Elementor y WordPress Core (wp-includes):
La web está construida utilizando el CMS WordPress junto con el constructor visual Elementor. Al abrir la pestaña de red, se puede observar una gran cantidad de scripts .js fragmentados (como jquery.min.js, frontend.min.js de Elementor, scripts de animaciones y librerías de sliders). Aunque individualmente están parcialmente minificados, la acumulación de todos estos scripts de plugins y del constructor visual suma más de 800 KB - 1 MB de código que el navegador debe descargar, parsear y ejecutar.

Hojas de estilo CSS duplicadas y sin usar (Elementor / Themes):
El tercer grupo de recursos más pesado corresponde a los archivos .css. Al utilizar un constructor visual comercial, el sitio descarga hojas de estilo genéricas para bloques de diseño que ni siquiera se están utilizando en la página de inicio. Los archivos CSS de Elementor, combinados con las fuentes tipográficas de Google Fonts (descargadas en archivos pesados .woff2 de forma externa), bloquean el renderizado inicial de la página sumando varios cientos de kilobytes.

### 3 Análisis:
Sí, esta web sufre una 'inflación de software' de manual. A ver, al final es una página súper sencilla —básicamente texto informativo, un blog con tres publicaciones y un contacto—, pero para mostrar eso te hace descargar entre 4 y 5 megas de datos y hace casi 100 peticiones a la red. El problema es que está construida con WordPress y un maquetador visual llamado Elementor, lo que inyecta un montón de código, animaciones y hojas de estilo repetitivas que el usuario ni llega a ver. En resumen: pesa muchísimo para lo poco que ofrece, penalizando la carga en móviles solo por culpa de una estructura interna sobrecargada e innecesaria.
