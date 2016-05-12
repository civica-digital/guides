Formas básicas de crear grids en css sin frameworks
===

### Float, overflow:hidden y clear:

Float es la forma más básica de crear un grid de elementos que se acomoden en columnas, este es un ejemplo:  

  .wrapper{
      overflow:hidden;
      .box{
        width:30%;
        float:left;
      }
  }

 

**Cuando usamos floats, tenemos que tener en cuenta:**

1- Cuando un elemento tiene float, es como si se despegara del código y flotara tanto como pueda hacia la derecha o la izquierda, y se acomoda donde topa con otro elemento. Cuando un elemento tiene float, es ignorado por los demás elementos que no flotan.
 

2- Cuando un contenedor, por ejemplo ‘paginación’, tiene adentro todos elementos que flotan: ‘prev’ y ‘next’, el contenedor los ignora. 

 

Para que un contenedor reconozca a sus hijos flotantes, tiene que tener *overflow:hidden*.  
  
  .pagination{
      overflow:hidden;
  
      .prev{
          float:left;
        width:30%;
      }
      .next{
          float:right;
          width:30%;
      }
  }

3- Cuando queremos que a partir de cierto punto los elementos que siguen a un elemento flotante comiencen a reconocerlo y dejen de ignorarlo, usamos clear:


 
### Display: inline-block y text-align: center

Esta es otra forma de crear elementos que se ubican en columnas:

  .wrapper{
      text-align:center;
      .box{
        width:200px;
        display:inline-block;
      }
  }

La diferencia básica con el float, es que si tenemos un grid de 3 columnas y 4 elementos, con float el cuarto elemento va a alinearse a la izquierda, y con inline-block va a centrarse.  
 
### Table y table-cell

Las tablas tienen dos ventajas que no podemos lograr con divs: centrar verticalmente un contenido y hacer que todos los elementos tengas el mismo alto.


Para que el *display:table-cell* de una caja funcione, su contenedor padre tiene que tener *display:table*. 

  .wrapper{
      display:table;
      .box{
        display:table-cell;
        width:30%;
      }
  }


