# Auditor a ASG y Refactorización Sostenible por López Alonso Marco
## Fase 1: Inventario y Dimensión Ambiental (A):
### 1. Medición inicial: 
Para esta actividad he elegido la página web de una cafetería/bar que hay al lado de donde estudio, llamada Cafetería Bar Marbella.
Para comenzar voy a utilizar las herramientas gratuitas como Website Carbon Calculator o Lighthouse (pestaña de rendimiento en Chrome/Edge) para obtener la huella de carbono estimada por visita.
El cual me da estos altísimos resultados:
<img width="1232" height="691" alt="image" src="https://github.com/user-attachments/assets/bd020265-c1e0-4952-b4ba-f0f025c47c81" />

### 2. Identificación de Bloatware:
Imágenes principales sin optimizar: El recurso individual más pesado es la imagen de fondo de la cabecera principal, el banner hero que muestra el local/terraza y las imágenes destacadas de los posts del blog como la imagen de la oferta de cubatas o de la terraza. Estas imágenes están subidas en formatos tradicionales de alta resolución como .jpg o .png en lugar de formatos modernos comprimidos como .webp o .avif. En total, el conjunto de imágenes de la página principal supera con creces los 2.5 MB - 3 MB, lo que supone la inmensa mayoría del peso de la web.

Archivos JavaScript de Elementor y WordPress Core:
La web está construida utilizando el CMS WordPress junto con el constructor visual Elementor. Al abrir la pestaña de red, se puede observar una gran cantidad de scripts .js fragmentados. Aunque individualmente están parcialmente minificados, la acumulación de todos estos scripts de plugins y del constructor visual suma más de 800 KB - 1 MB de código que el navegador debe descargar, parsear y ejecutar.

Hojas de estilo CSS duplicadas y sin usar (Elementor / Themes):
El tercer grupo de recursos más pesado corresponde a los archivos .css. Al utilizar un constructor visual comercial, el sitio descarga hojas de estilo genéricas para bloques de diseño que ni siquiera se están utilizando en la página de inicio. Los archivos CSS de Elementor, combinados con las fuentes tipográficas de Google Fonts descargadas en archivos pesados .woff2 de forma externa, bloquean el renderizado inicial de la página sumando varios cientos de kilobytes.

### 3. Análisis:
Sí, esta web sufre una 'inflación de software' de manual. A ver, al final es una página súper sencilla —básicamente texto informativo, un blog con tres publicaciones y un contacto—, pero para mostrar eso te hace descargar entre 4 y 5 megas de datos y hace casi 100 peticiones a la red. El problema es que está construida con WordPress y un maquetador visual llamado Elementor, lo que inyecta un montón de código, animaciones y hojas de estilo repetitivas que el usuario ni llega a ver. En resumen: pesa muchísimo para lo poco que ofrece, penalizando la carga en móviles solo por culpa de una estructura interna sobrecargada e innecesaria.



## Fase 2: Dimensión Social y Equidad:
### Contraste de color insuficiente e identificación de barreras:
Esta web suspende en accesibilidad porque tiene barreras graves que dejan fuera a muchos usuarios. El primer gran problema es el contraste de los colores. En varias partes de la página, como en los menús o en algunos botones, se usa texto claro sobre fondos que también son claros o sobre fotografías. Esto hace que sea un dolor de cabeza leer la información para personas con baja visión, daltonismo o cualquiera que intente mirar la pantalla en la calle con el reflejo del sol.

El otro fallo crítico está en las imágenes y en cómo está organizada la página por dentro. La mayoría de las fotos de los platos y de la terraza no tienen texto alternativo, lo que significa que los lectores de pantalla que usan las personas invidentes no pueden describirles lo que hay ahí. Además, los títulos y encabezados internos están desordenados y se usan solo por estética, rompiendo la estructura lógica. Al final, alguien que dependa del teclado o de un asistente de voz para navegar se va a perder por completo en la web.



## Fase 3: Dimensión de Gobernanza y Ética:
Ahora voy a revisar las cookies y la parte de contacto de la web.
Al entrar en la web nos va a saltar en la esquina derecha de la pantalla el siguiente mensaje:

<img width="535" height="293" alt="image" src="https://github.com/user-attachments/assets/eb22930b-f3ea-4244-9ad0-b2a2821a2077" />

Aquí podemos ver que las cookies no van con trampa, no te obligan al 100% a aceptarlas para poder ver o entrar en la web, permitiendonos así llegar a rechazarlas.
Y ahora vamos a ver si la web nos pide algún tipo de información o registro para poder contactar con esta:
<img width="582" height="591" alt="image" src="https://github.com/user-attachments/assets/b22a232a-2fc0-44d4-8c52-30ae3ba60635" />

Por lo que podemos ver en estas dos imágenes, la web nos permite entrar y contactar sin la necesidad de que demos ni un dato personal, cosa que muchos usuarios agradecen, ya que prefieren no dar sus datos personales solo para ver una web o contactar con ellos.


## Fase 4: Propuesta de Refactorización:
