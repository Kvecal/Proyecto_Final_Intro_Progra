// Hecho por Juan Mauel Charchalac
// carnet 15004342
// Introduccion a la Programacion

Aca se inicia los dialogos de presentacion

alert (" Seguros TK-U ")
alert (" Ciudad Jedha, Mid Rim")
alert (" Calculador Asegurador v.2")

Defino la variable principal

var preciobase=2000

Estas son las variables que multiplican dependiendo el rango de edad del primario

var edad1824=0.10
var edad2549=0.20
var edad50=0.30

Variables que multiplican segun rango edad del conyuge

var edcnyg1824=0.10
var edcnyg2549=0.20
var edcnyg50=0.30


Estos son los recargos

por edad del primario

var recargoedad=0

por edad del conyuge

var recargoconyuge=0

por cantidad de hijos

var recargohijos=0
var hijopercent=0.2

recargos EXTRAS (los puntos extras, no funcionó)

por propiedad

var casas=0
var propipercent=0.35

por salario (tampoco funcionó)

var sal=0
var salpercent=0.05

subtotales de los recargo

edad + conyuge + hijos

var recargototal=0

total a cobrar despues de ingresar los valores (cotizacion final)

el base + recargos

var preciofinal=0


primeros mensajes para ingresar informacion

var nombre=prompt("Ingrese su nombre completo");

var edad=prompt("Ingrese su edad (números únicamente)");

var conyuge=prompt("¿Es usted casado ó casada (SI ó NO)?")

Comprobando la edad del cónyuge, solamente si se está casado/a

var conyugeedad
if("SI"==conyuge.toUpperCase()){
  conyugeedad=prompt("¿Qué edad tiene su conyuge (números únicamente)?")
}

var edadnum=parseInt(edad)
var conyugeedadnum=0  // este valor lo voy a multiplicar con edad conyuges

Convirtiendo la edad del cónyuge si se esta casado/a

if("SI"==conyuge.toUpperCase()){
  conyugeedadnum=parseInt(conyugeedad)
}

var hijos=prompt("¿Tiene usted hijos (SI ó NO)?")

Verificando la cantidad de hijos, si la respuesta es Si

var cantidadhijos
if("SI"==hijos.toUpperCase()){
  cantidadhijos=prompt("¿Cuantos hijos tiene (números únicamente)?")
}

var hijosnum=0

Conviertiendo la cantidad de hijos

if("SI"==hijos.toUpperCase()){
  hijosnum=parseInt(cantidadhijos)
}

 calculando porcentaje hijos

recargohijos = preciobase * hijopercent * hijosnum


Propiedades (aca no funcionó)
cuando eligo la respuesta NO, tira error y no finaliza el programa

var propi=prompt("¿Desea incluir propiedades inmuebles (casas, terrenos) en ésta cotización (SI ó NO)?")

var cantidadpropi
if("SI"==propi.toUpperCase()){
  cantidadpropi=prompt("¿Cuantas propiedades desea incluir? (números únicamente)?")
}

var propinum=0

if("SI"==propi.toUpperCAse()){
  propinum=parseInt(cantidadpropi)
}

casas = preciobase * propipercent * propinum 


Sueldo (no funcionó)
Este prompt ya no lo veo, despues del prompt de Inmuebles

var sueldo=prompt("¿Desea incluir su salario en ésta cotización (SI ó NO)?")
if("SI"){
  sal = preciobase * salpercent
}


calculando con la edad del conyuge

if(conyugeedadnum<=17){
  alert("Error. Decreto 13-2017. Artículo 83 del Código Civil de Guatemala")
}
if(conyugeedadnum>=18 && conyugeedadnum<=24){
  recargoconyuge=preciobase*edcnyg1824
}
if(conyugeedadnum>=25 && conyugeedadnum<=49){
  recargoconyuge=preciobase*edcnyg2549
}
if(conyugeedadnum>=50){
  recargoconyuge=preciobase*edcnyg50
}


calculando con la edad del primario

if(edadnum<=17){
alert("Error. Proceso se aplica a personas de 18 años en adelante");  
}
if(edadnum>=18 && edadnum<=24){
  recargoedad=preciobase*edad1824

  recargototal = recargoedad + recargoconyuge + recargohijos + casas + sal  // las variables + casas + sal no se incluyen en el programa que si funciona

}
if(edadnum>=25 && edadnum<=49){
  recargoedad=preciobase*edad2549

  recargototal = recargoedad + recargoconyuge + recargohijos + casas + sal

}
if(edadnum>=50){
  recargoedad=preciobase*edad50
    
  recargototal = recargoedad + recargoconyuge + recargohijos + casas + sal
}


preciofinal = preciobase + recargototal


alert (" Para el solicitante: "+nombre)
alert (" El total de recargos en base a la información provista es de: "+recargototal)
alert (" El precio total para asegurar es de:  "+preciofinal)


QUE SE PODRIA MEJORAR?

varias cosas, mencionando por ejemplo que los extras no los logré funcionar
y que al preguntar si el cliente es casado, al responder NO, me tira el mensaje de edad menor a 17 años


// Hecho por Juan Mauel Charchalac
// carnet 15004342
// Introduccion a la Programacion

//fin