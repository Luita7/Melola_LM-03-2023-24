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
