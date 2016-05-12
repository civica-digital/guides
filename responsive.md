Responsive básico en 4 pasos
===

### 1- Definir qué va a ser responsive y qué elástico

**Responsive** es cuando la visualización se ajusta a un rango de medidas más o menos fijas (px o em), por ejemplo: de 960px a 1200px, de 780 a 959, etc.  

**Elástico**, es cuando se va ajustando pixel a pixel, porque el contenedor mide un porcentaje con respecto a la pantalla.

Siempre va a haber excepciones y todo dependerá de las necesidades del diseño, pero podemos tomar de base esta estructura:
1200 o + (responsive)  
960 a 1199 (responsive)  
780 a 959 (responsive)  
640 a 779 (responsive)  
320 a 639 (elástico)  

### 2- Agregar el meta viewport

Esta meta etiqueta va en el header del layout, y define cómo se va a mostrar el sitio en distintos dispositivos.

``` <meta name=viewport content="width=device-width, initialscale=
1"> ```  

Con ese tag, le decimos al dispositivo que si mide 380px de ancho, se muestren 380px reales y no los 1200 de nuestro container achicados proporcionalmente.

### 3- Configurar el layout

Definimos el tamaño del contenedor que va a responder a los distintos rangos de media:

	.container{
		width: 1200px;
		@include media(min-width 960px max-width 1199px){
			width: 960px; padding-left:15px; padding-right:15px;
		}
		@include media(min-width 780px max-width 959px) {
			width: 780px; padding-left:15px; padding-right:15px;
		}
		@include media(min-width 640px max-width 779px) {
			width: 640px; padding-left:10px; padding-right:10px;
		}
		@include media(min-width 320px max-width 639px) {
			width: 100%; padding-left:10px; padding-right:10px;
		}
	}

### 4- Ajustar cada componente

Una vez que tenemos definidos los saltos de container, podemos ir revisando cada componente a sus distintas visualizaciones. Hay dos formas de hacerlo:

1- **Incluir los media queries dentro del componente, o en los archivos de configuración (Opción recomendada)**: A medida que vamos escribiendo el código del componente, lo vamos revisando en las distintas versiones y hacemos los ajustes necesarios para que las visualizaciones sean correctas. Solo incluimos los media de los saltos en los que necesitamos hacer ajustes:
	
	.evento{
		float: left;
		width:30%;
		
		@include media(min-width 640px max-width 959px) {
			width: 48%;
		}
		@include media(min-width 320px max-width 639px) {
			width: 100%;
		}
	}
Es importante escribir la menor cantidad de media queries posible, para que sea más legible el código y más fácil hacer retoques. Por eso, no necesariamente hay que escribirlas en cada componente, sino a veces en los archivos de configuración, por ejemplo, en _tipography.scss, podemos definir:
	
	h1 {
		font-size: 40px;
		
		@include media(min-width 640px max-width 959px) {
			font-size: 30px;
		}

		@include media(min-width 320px max-width 639px) {
			font-size: 20px;
		}
	}

Las razones por las que recomiendo esta opción son:  


a- Es más fácil encontrar las variaciones cuando estamos dentro
del scss del componente, que buscarlas en un archivo
distinto.   

b- A medida que vamos creando el grid del componente, podemos
ir pensando en cómo se va a comportar en responsive, y esto
nos permite ajustar en haml y scss en el momento, sin
necesidad de tener que volver a cambiar elementos del haml
luego.  

===   
    
2- **Incluir los media queries en archivos SCSS separados.** Esta opción es válida cuando tenemos un sitio que ya está resuelto, pero no es del todo aconsejable cuando estamos empezando un proyecto nuevo.   

