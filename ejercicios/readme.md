# Ejercicios para practicar DTD

## Ejercicio 1: mensajes

**1.** Se quiere almacenar los mensajes de móviles que se envían a un servidor. Los datos que se guardarán son los siguientes:

- Número de teléfono del usuario
- Fecha de envío
- Hora de envío
- Texto del mensaje

Crear primero el XML que permita almacenar dicha información y posteriormente una DTD que permita establecer el formato de intercambio de estos mensajes.

**2.** Suponer para el ejercicio anterior, que por cada mensaje recibido se puede almacenar más de un texto. Modificar la dtd para contemplar este cambio.

**3.** Añadir al ejercicio anterior un atributo en el nodo hora que me permita almacenar la franja horaria (de manera obligatoria).

## Ejercicio 2: vuelos

Sea el siguiente documento XML de ejemplo, construye el fichero validador vuelos.dtd, teniendo en cuenta:

- Por cada vuelo es obligatorio un origen y un destino.
- El orden en el que aparecen origen y destino puede ser cualquiera

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE vuelos SYSTEM "vuelos.dtd">
<vuelos>
  <vuelo>
    <origen>Valencia (VLC)</origen>
    <destino>Londres Heathrow (LHR)</destino>
  </vuelo>
  <vuelo>
    <destino>Berlín Schönefeld (SFX)</destino>
    <origen>Paris Charles de Gaulle (CDG)</origen>
  </vuelo>
</vuelos>
```

## Ejercicio 3: catálogo de CDs

Sea el siguiente documento XML de ejemplo, construye el fichero validador catalogo.dtd, teniendo el cuenta:

- El catálogo puede tener muchos o ningún CD.
- Se podrá especificar o no la discográfica y año.
- Título del disco y canciones es obligatorio.
- Al menos habrá una canción.
- El título de la canción es obligatorio, pero no así la duración.
- En caso de especificar la duración, es obligatorio especificar minutos y segundos

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE catalogo SYSTEM "catalogo.dtd">
<catalogo>
  <cd>
    <autor>Los Pisotones</autor>
    <discografica>Producciones del garaje</discografica>
    <anyo>2015</anyo>
    <titulo_disco>En directo</titulo_disco>
    <canciones>
      <cancion>
        <titulo_cancion>Curiosa casualidad</titulo_cancion>
        <duracion>
          <minutos>3</minutos>
          <segundos>54</segundos>
        </duracion>
      </cancion>
      <cancion>
        <titulo_cancion>Lapiceros de colores</titulo_cancion>
      </cancion>
    </canciones>
  </cd>
</catalogo>
```


## Ejercicio 4: biblioteca

Se quiere crear una biblioteca de libros en un documento XML. Para ello se necesita crear una DTD que almacene los siguientes campos de un libro:

1)	Atributos libro
   
    Código del libro único
  	
    Tipo portada	 (tapaDura | tapaBlanda | bolsillo) por defecto bolsillo
3)	Título
4)	Edición
5)	Editorial
6)	ISBN
7)	Número de páginas
8)	Autores

Además debéis tener en cuenta que hay dos tipos de autores:

- autor
- autora
  
Y puede haber más de una autor y autora. Como mínimo 1.

## Ejercicio 5: factura

Escribir un documento XML con una DTD asociada que represente la información contenida en la siguiente factura ficticia:

![image](https://github.com/profeMelola/LM-03-2023-24/assets/91023374/58455efd-ce3c-4854-8504-976e5d2d9dee)

Consideraciones respecto a la DTD:

- Hay que guardar los datos del emisor de la factura agrupados. A continuación, los datos del cliente, también agrupados. Y finalmente, los datos de detalle donde se escriben (en líneas) los datos de cada artículo, así como, el importe total.
- Obsérvese que en cada línea se indica el código de un artículo, el tipo al que pertenece, su descripción, la cantidad facturada, si está de oferta o no, y el PVP (Precio de Venta al Público). Ahora bien, de los datos que aparecen en cada línea, sólo el código del artículo y el tipo deben representarse mediante atributos en la DTD.
- Se tiene que indicar que el código del artículo ha de ser único y obligatorio para cada artículo.
- Los posibles tipos de un artículo son Libro, DVD o Varios, no permitiéndose otro valor. Ahora bien, este atributo debe indicarse que es opcional.
- El importe también debe representarse por medio de un atributo, que debe ser obligatorio.
- En la DTD debe indicarse que al menos tiene que aparecer una línea de detalle y, para cada una de ellas, se tiene que guardar la información en el mismo orden en el que aparece en la factura.
- Para indicar si un artículo está de oferta, se debe utilizar un elemento vacío que, respecto a cada artículo, podrá aparecer (en el caso de sí estar de oferta) o no aparecer (en el caso contrario).
- Respecto al número de la factura y su fecha de emisión, deben representarse mediante atributos obligatorios donde se estime más apropiado.

## Ejercicio 6: panel de vuelos

Escribir un documento XML con una DTD asociada que represente la información contenida en la siguiente factura ficticia:

Consideraciones respecto a la DTD:

![image](https://github.com/profeMelola/LM-03-2023-24/assets/91023374/a8d5a8bd-382b-4c7b-a243-b63adeb30cd3)


- Hay que guardar el nombre del aeropuerto, los datos de cada vuelo agrupados y la fecha del panel, en ese orden.
- En la DTD, sólo el código de un vuelo y su estado deben representarse mediante atributos.
- Se tiene que indicar que el código ha de ser único y obligatorio para cada vuelo.
- Los posibles estados de un vuelo son C (Cancelado), E (En hora), R (Retrasado). El valor por defecto debe ser E.
- En la DTD debe indicarse que al menos tiene que aparecer un vuelo y, para cada uno de ellos, se tiene que guardar la información en el mismo orden en el que aparece en el panel.
- Para indicar si un vuelo es diario, se debe utilizar un elemento vacío que, respecto a cada vuelo, podrá aparecer (en el caso de sí ser diario) o no aparecer (en el caso contrario).

## Ejercicio 7: boletín de notas

Crea un documento XML que permita el envío de la información de los boletines de notas de los alumnos de un curso.

Dicho XML debe guardar toda la información que se puede completar en un boletín:

![image](https://github.com/profeMelola/LM-03-2023-24/assets/91023374/bc8d4b48-f0f3-433b-bc87-5a3b58b1b293)

Se necesita el mayor nivel de estructuración en el XML.

Después crea un documento DTD validador que tenga en cuenta:
- El orden del nombre, apellido y dirección del alumno no puede variar.
- El nombre y apellido es obligatorio, la dirección es opcional.
- El orden de los módulos no tiene por qué ir de forma secuencial.
- Cada módulo tendrá un atributo llamado evaluacion que sólo tendrá los valores: 1ev, 2ev, 3ev, ordinaria



