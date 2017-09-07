# Como hacemos datos abiertos
> Datos Abiertos como propósito y a propósito


## ¿Porqué hacer Open Data?

Los datos tienen consigo información, la cual sabemos, es dificil de aprovecharse completamente desde un solo frente. Dejar la puerta abierta para que la comunidad explore los datos, tanto de nuestros aliados con los que formamos equipo como de los proyectos que desarrollamos, tiene muchísimo valor para generar valor a las comunidades que impactamos.

## ¿Cómo hacemos Open Data en cívica digital?

Así como generamos código abierto, hacemos *open data por propósito*, lo que significa que abrimos datos cuando tenemos claro:
- El valor en la comunidad de los datos que estamos generando.
- La velocidad y calidad de los datos a publicar.
- La estrategia de publicación de datos en el tiempo.

## ¿Qué compone la calidad de los datos abiertos?

Los datos abiertos tienen dos dimensiones en los indicadores de su calidad:

- **Eje Técnico**: Los datos están en sus mejores condiciones técnicas para ser reutilizado. Esto incluyen las dimensiones consideradas en el [Five star open data](http://5stardata.info/en/), y las preguntas hechas para el eje de calidad de los datos hechas por el [barómetro de datos abiertos](http://opendatabarometer.org/).
- **Eje temático**: Los datos tienen la mayor cantidad de densidad de información por dato. Esto es, los datos registrados contienen la mayor cantidad de respuestas a las preguntas que se podrían realizar al conjunto temático en su tópico. Las unidades de medida no son tan claras como en el eje técnico, pero es importante considerar la granularidad de la información, la adhesión del conjunto de datos a los estandares que existen para tal tema, y la frecuencia con la que los datos se actualizan.


## Lo que hemos hecho antes:

**Herramientas para la Apertura de datos:**
- Refinadora - Test compliance of Open Data Standards using scripts in any language from a single web interface - [Repo](https://github.com/civica-digital/la-refinadora)
- IRIS - Information Readiness Assessment - [Repo](https://github.com/civica-digital/iris)

**Repositorios de datos abiertos**
- Datamx.io - [link](datamx.io) - [Repo](https://github.com/CodeandoMexico/ckanext-datamx_theme)
- Laboratorio para la Ciudad de México - [link](http://datos.labcd.mx/dataset) -  [Repo](https://github.com/LabPLC/Laboratorio-de-datos/graphs/contributors)

**Plataformas que generan datos abiertos**
- URBEM - [link](http://urbem-puebla.herokuapp.com/)
- MiNegocio México - [link]() - [Repo](https://github.com/civica-digital/mi-negocio-mx)

**Procesos de Seguimiento a la apertura de datos**
- Laboratorio para la Ciudad en Ciudad de México - [Datos](http://datos.labcd.mx/dataset)
- Ciudatos - [Datos](http://datos.ciudatos.com/dataset)
- MiNegocio México - [Datos](https://minegociomexico.mx/)
- Respira - [Datos](respiraciudad.org)

**Visualización de datos**
- Inversión en el gasto - [link](cambioclimatico.tm.org.mx) - [Repo](https://github.com/civica-digital/financiamiento-climatico)
- UNHabitat - [link](unhabitat-ciudades-equitativas.herokuapp.com)
- Ciudatos - [link](http://ciudatos.com/datos/indicadores/) - [Repo](https://github.com/civica-digital/como-vamos-colombia-webapp)
- Respira - [link](respiraciudad.org) - [Repo](https://github.com/civica-digital/calidad-del-aire-webapp)

**Análisis y Evaluación de Estrategias de Datos Abiertos**
- Open Data Barometer - [link](opendatabarometer.org)
- Articulo: Open Data Squads - [link](http://datos.gob.mx/)


#### ¿Cómo instalamos open data en nuestras plataformas y proyectos?

1. Identificar el valor en los datos que están alimentando o generando las aplicaciones que desarrollamos.
2. Conversar con nuestro aliado sobre el potencial de su información y el valor de compartir los datos con la comunidad.
3. Generar una estrategia para la publicación periódica y preferentemente automática de la información recabada o generada por la plataforma, tomando en cuenta las restricciones de datos personales. Dar preferencia a la publicación en un repositorio público de datos abiertos.
4. Hacer visible la generación de los datos abiertos en la plataforma y salida del producto generado.


#### ¿Cómo apoyamos los procesos de apertura de datos a los que nos invitan?

1. **Identificar** los aliados generadores de datos. Realizar una primer acercamiento y convencimiento sobre el valor de los procesos de apertura y el objetivo del proceso.
2. **Contactar** a los aliados, siempre es importante tener un lider técnico que sirva de contacto para las fuentes de datos; Y un administrador, que permita la toma rápida de desiciones.
3. **Iniciar** el rebote de la información entre el ente generador y nosotros. Este proceso puede ser en el rebote del contenido de los archivos cuando los datos están en lote, y la estructura de la API provista de existir alguna. *formar capacidades va primero que realizar la tarea*
4. **Asignar** el espacio para la publicación de la información. Aquí podemos entrar como aliados en la instalación, aprovechando nuestro know-how de las plataformas de datos.
5. **Revisar** nuestra estrategia de publicación con las necesidades de la comunidad que rodea a los datos, es importante este paso para confirmar las hipótesis sobre la publicación de datos contra la realidad de su consumo.

De manera paralela, es importante reconocer los puntos de mayor potencial para el aprovechamiento de los datos; Ya que es un paso natural para la realización de un proyecto de seguimiento.


#### Aprendizajes sobre las plataformas de visualización de datos.

1. Identificar las necesidades del usuario y centrarse en las más importantes.
2. La mejor visualización no está siempre en la que visualiza más datos, sino la que da más información.
3. Diseño y Datos deben de estar juntos en el proceso de desarrollo de visualizaciones.
4. Dar preferencia al uso de plantillas de manejo de Frontend, para centrarse en la visualización de datos.
5. Hasta ahorita, la preferencia está en APIs de datos y webapps independientes consumiendo la información sobre la construcción de aplicaciones completas. Eso está a discusión.
