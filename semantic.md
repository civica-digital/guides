HAML/SCSS Marcado Semántico
===
Cuándo usar ids, clases, y selectores de etiqueta
---

### ID

1- Como selector único de una vista, también se puede usar
clase.

    #contact
        %h1
        %p

2- Si necesitamos manipular el elemento con js

    #url-box-js
        %p
        %button

### Clase

1- Cuando necesitamos nombrar un div de forma particular, por ejemplo un componente

    .event
        %p
        %button

2- O el contenedor de una lista de componentes

    .events
        .event 
            ...
        .event 
            ...

3- Cuando no existe la posibilidad de usar un selector de etiqueta para agrupar elementos  

    .event
        .activities
            %h4  
            %p
        .routes
            %img
        %button


### Selectores de etiqueta

1- Siempre que sea posible, sin recurrir a estructuras extrañas para justificarlo.   
**Estaría bien:** 

    .evento
        %h3
        %p
        %img
        %ul
            %li
            %li
        %button

2- O, si necesitamos agrupar algunos elementos dentro de otros:  
  
    .evento
        %header
            %h3
            %p
        %main
            %img
            %ul
                %li
                %li
        %footer
            %button

**No estaría bien**, o no sería del todo práctico…  
    
    .evento
        %div
            %h3
            %p
        %div
            %ul
                %li
                %li
        %div
            %button

…porque necesitaríamos escribir un scss muy rebuscado, tipo:  
  
    .evento{
        div:first-child{…}
        div + div{…}
        div:last-child{…}
    }

Cómo marcar semánticamente el código html
---
**1- Usando etiquetas html5 para definir el layout, por ejemplo:**
    
    %header
        %nav
            %ul
                %li…
    %section
        %aside
            %nav
                %ul
                    %li…
        %article
            %header
                %h1
            %main
                %p
                %figure
                    %img
                    %figcaption
        %footer
            %nav
                %ul
                    %li…

Pueden ver una guía de html tags acá: 
http://www.w3schools.com/html/html5_semantic_elements.asp

**2- Tratando de usar, siempre que se pueda, sólo selectores de etiqueta** combinados con una clase para identificar al componente, por ejemplo:  

    .evento
        %h3
        %p
        %img
        %ul
            %li
            %li
        %button

3- Usar correctamente los selectores de etiqueta, **evitar usar etiquetas para contener elementos que NO corresponden semánticamente con su nombre**, como por ejemplo:  

    %p
        %input


4- Evitar, en la medida de lo posible, meter elementos de bloque dentro de
elementos de línea, por ejemplo:  
  
    %a
        %h1
        %p

5- **Evitar ensuciar el haml con clases** que se pueden definir en el scss, por ejemplo  
  
    %h3.text-center

> Siempre hay excepciones, diseños en los que no se pueden usar solo selectores de etiqueta
y necesitamos muchas clases, o situaciones donde meter un %h3.text-center nos
ahorra escribir 20 líneas de scss. En esos casos, siempre priorizar lo que sea
más práctico, requiera escribir menos código, y sea más fácil de leer y
entender.  
  
  
Cómo estructurar SCSS
===
### Directorio de archivos

Podemos trabajar con la estructura que sugiere bourbon, donde tenemos un archivo _base en cada directorio en el que incluimos todos los shared; y un archivo application, donde incluimos todos los _base. Los directorios necesarios dependerán de cada proyecto, pero como guía podemos tomar:

1- *Base*, donde estarán todos los archivos de configuración, variables, helpers.  
2- *Componentes*, donde pondremos todos los componentes que necesitemos en nuestra app.

Ejemplo:

* base  
    * _base.scss  
    * _buttons.scss  
    * _grid-settings.scss  
    * _variables.scss  
* componentes
    * _base.scss   
    * _header.scss  
    * _footer.scss  
    * _content-texts.scss  
    * _modal.scss  
    * _video.scss  
* application.scss

### Estructura básica scss para un componente

>Idealmente, cada componente debería tener una clase para el wrapper y luego elementos html para marcar su contenido. Si se trata de un componente de lista, podemos tener también un wrapper para la lista, que utilizaremos en el scss para definir el grid. 

Por ejemplo, para una estructura donde queremos que un bloque de evento se repita en un grid de 3 columnas, podemos definir: 

    .events
        .event
            %h3
            %p
            %button
    .event …
    .event …

podríamos usar un scss:  
  
    .events{
        margin-top:50px;
        overflow:hidden;
        
        .event{
            width:30%;
            float:left;
            background-color:$blue;
            
            h3{
                color:#fff;
            }
            
            p{
                color:$light-gray;
            } 
        }
    }


Ahora, imaginando que queremos usar el mismo componente de evento, pero lo necesitamos con otro grid que ya no sea de 3 columnas sino uno debajo del otro al 100%, podemos utilizar una clase especial para el wrapper y generar las excepciones con @extend:  
  
    .events-100
        .event …
        .event …
        .event …

y en nuestro scss, solo agregamos:  
  
    .events{
         …
    }
    .events-100{
        @extend .events;
        .event {
            width:100%;  
            float:none;
        }
    }

Algo similar podemos hacer cuando tenemos componentes de listas, pero hay variaciones en los elementos. Para eso se suelen usar dos clases, una para definir lo general y otra para las
excepciones: 

    .events
        .event.event-blue …
        .event.event-red …
        .event.event-green …
        .event.event-blue …

Sin embargo, sería mejor usar @extend, y no repetir la clase 'event' en cada elemento, lo haríamos así:

    .events
        .event-blue …
        .event-red …
        .event-green …
        .event-blue …
Y en SCSS
  
    .events{
        .event{
            width:30%;
            float:left;
            color:#fff;
        }
        
        .event-blue{
            @extend .event;
            background-color:$blue;
        }
        .event-red{ ...}
    }