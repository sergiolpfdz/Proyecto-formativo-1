# Proyecto-formativo-1
Variables
Es un nombre que se refiere a un objeto que reside en la memoria. El objeto puede ser de alguno de los tipos vistos
(número o cadena de texto), o alguno de los otros tipos existentes en Python.
Cada variable debe tener un nombre único llamado identificador. Eso es muy de ayuda pensar las variables como
contenedores que contienen data el cual puede ser cambiado después a través de técnicas de programación.
Ejemplo de asignar valor a variable
A continuación, se creará un par de variables a modo de ejemplo. Una de tipo cadenas de caracteres (Página 45)
y una de tipo entero:
>>> c = "Hola Mundo" # cadenas de caracteres
>>> type(c) # comprobar tipo de dato
<type 'str'>
>>> e = 23 # número entero
>>> type(e) # comprobar tipo de dato
<type 'int'>
Constantes
Una constante es un tipo de variable la cual no puede ser cambiada. Eso es muy de ayuda pensar las constantes
como contenedores que contienen información el cual no puede ser cambiado después.
En Python, las constantes son usualmente declaradas y asignadas en un módulo. Aquí, el módulo significa un
nuevo archivo que contiene variables, funciones, etc; el cual es importada en el archivo principal. Dentro del
módulo, las constantes son escritas en letras MAYÚSCULAS y separadas las palabras con el carácter underscore
_.
Ejemplo de constantes desde un módulo externo
Crear un archivo llamado constantes.py con el siguiente contenido:
IP_DB_SERVER = "127.0.0.1"
PORT_DB_SERVER = 3307
USER_DB_SERVER = "root"
PASSWORD_DB_SERVER = "123456"
DB_NAME = "nomina"
Crear un archivo llamado main.py con el siguiente contenido:
import constantes
print "scp -v -P {0} {1}@{2}:/{3}/{4}/{4}.sql /srv/backup".format(
str(constantes.PORT_DB_SERVER), constantes.USER_DB_SERVER,
constantes.IP_DB_SERVER, constantes.USER_DB_SERVER,
constantes.DB_NAME)
Luego ejecuta el programa de la siguiente forma:
python main.py
Cuando usted ejecuta el programa, la salida será:
scp -v -P 3307 root@127.0.0.1:/root/webapp/db.sql /srv/backup
Operadores de asignaciones
Los operadores de asignación se utilizan para
Existe en Python todo un grupo de operadores los cuales le permiten básicamente asignar un valor a una variable, usando el operador “=”. Con estos operadores pueden aplicar la técnica denominada asignación aumentada
Operador =
El operador igual a, (=), es el más simple de todos y asigna a la variable del lado izquierdo cualquier variable o
resultado del lado derecho.
Operador +=
El operador += suma a la variable del lado izquierdo el valor del lado derecho.
>>> r = 5; r += 10; r
15
En el ejemplo anterior si la variable “r” es igual a 5 y r += 10, entonces la variable “r” sera igual a 15. Su
equivalente seria el siguiente:
>>> r = 5; r = r + 10; r
15
Operador -=
El operador -= resta a la variable del lado izquierdo el valor del lado derecho.
>>> r = 5; r -= 10; r
-5
Clases
A continuación, una lista de clases integradas Python para los tipos de cadenas de caracteres:
basestring
Es la clase base de las clases str y unicode.
str
Son secuencias inmutables de cadenas de caracteres con soporte a caracteres ASCII.
>>> 'Hola Mundo'
'Hola Mundo'
>>> "Hola Mundo"
'Hola Mundo'
unicode
Son secuencias inmutables de cadenas de caracteres con soporte a caracteres Unicode.
>>> u'Jekechitü'
u'Jekechit\xfc'
Funciones
Python implementa un sistema muy sencillo para establecer el valor de las docstrings en las funciones, únicamente tiene que crear un comentario en la primera línea después de la declaración.
>>> def hola(arg):
... """El docstring de la función"""
... print "Hola", arg, "!"
...
>>> hola("Plone")
Hola Plone !
Puede puede consultar la documentación de la función hola() debe utilizar la función integrada help() (Página 115) y pasarle el argumento del objeto de función hola():
>>> help(hola)
Help on function hola in module __main__:
hola(arg)
El docstring de la función
>>>
>>> print hola.__doc__
El docstring de la función
Clases y métodos
De la misma forma puede establecer la documentación de la clase después de la definición, y de los métodos,
como si fueran funciones:
>>> class Clase:
...
... """El docstring de la clase"""
... def __init__(self):
... """El docstring del método constructor de clase"""
...
... def metodo(self):
... """El docstring del método de clase"""
...
>>> o = Clase()
>>> help(o)
Help on instance of Clase in module __main__:
class Clase
| El docstring de la clase
|
| Methods defined here:
|
| __init__(self)
| El docstring del método constructor de clase
|
| metodo(self)
| El docstring del método de clase
>>> o.__doc__
'El docstring de la clase'
>>> o.__init__.__doc__
'El docstring del método constructor de clase'
>>> o.metodo.__doc__
'El docstring del método de clase'
Métodos
El el objeto de tipo lista integra una serie de métodos integrados a continuación:
append()
Este método agrega un elemento al final de una lista.
>>> versiones_plone = [2.5, 3.6, 4, 5]
>>> print versiones_plone
[2.5, 3.6, 4, 5]
>>> versiones_plone.append(6)
>>> print versiones_plone
[2.5, 3.6, 4, 5, 6]
count()
Este método recibe un elemento como argumento, y cuenta la cantidad de veces que aparece en la lista.
>>> versiones_plone = [2.1, 2.5, 3.6, 4, 5, 6]
>>> print "6 ->", versiones_plone.count(6)
6 -> 1
>>> print "5 ->", versiones_plone.count(5)
5 -> 1
>>> print "2.5 ->", versiones_plone.count(2.5)
2.5 -> 1
extend()
Este método extiende una lista agregando un iterable al final.
>>> versiones_plone = [2.1, 2.5, 3.6]
>>> print versiones_plone
[2.1, 2.5, 3.6]
>>> versiones_plone.extend([4])
>>> print versiones_plone
[2.1, 2.5, 3.6, 4]
>>> versiones_plone.extend(range(5,7))
>>> print versiones_plone
[2.1, 2.5, 3.6, 4, 5, 6]
index()
Este método recibe un elemento como argumento, y devuelve el índice de su primera aparición en la lista.
>>> versiones_plone = [2.1, 2.5, 3.6, 4, 5, 6, 4]
>>> print versiones_plone.index(4)
3
El método admite como argumento adicional un índice inicial a partir de donde comenzar la búsqueda, opcionalmente también el índice final.
>>> versiones_plone = [2.1, 2.5, 3.6, 4, 5, 6, 4]
>>> versiones_plone[2]
3.6
Funciones
Una función es un bloque de código con un nombre asociado, que recibe cero o más argumentos como entrada,
sigue una secuencia de sentencias, la cuales ejecuta una operación deseada y devuelve un valor y/o realiza una
tarea, este bloque puede ser llamados cuando se necesite.
El uso de funciones es un componente muy importante del paradigma de la programación llamada estructurada
(Página 97), y tiene varias ventajas:
modularización: permite segmentar un programa complejo en una serie de partes o módulos más simples,
facilitando así la programación y el depurado.
reutilización: permite reutilizar una misma función en distintos programas.
Python dispone de una serie de funciones integradas (Página 111) al lenguaje, y también permite crear funcion
definidas por el usuario para ser usadas en su propios programas.
Sentencia def La sentencia def es una definición de función usada para crear objetos funciones definidas por el usuario. Una definición de función es una sentencia ejecutable. Su ejecución enlaza el nombre de la función en el namespace local actual a un objecto función (un envoltorio alrededor del código ejecutable para la función). Este objeto función contiene una referencia al namespace local global como el namespace global para ser usado cuando la función es llamada. La definición de función no ejecuta el cuerpo de la función; esto es ejecutado solamente cuando la función es llamada. La sintaxis para una definición de función en Python es: def NOMBRE(LISTA_DE_PARAMETROS): """DOCSTRING_DE_FUNCION""" SENTENCIAS RETURN [EXPRESION] A continuación se detallan el significado de pudo código fuente anterior: NOMBRE, es el nombre de la función. LISTA_DE_PARAMETROS, es la lista de parámetros que puede recibir una función. DOCSTRING_DE_FUNCION, es la cadena de caracteres usada para documentar (Página 49) la función. SENTENCIAS, es el bloque de sentencias en código fuente Python que realizar cierta operación dada. RETURN, es la sentencia return  en código Python. EXPRESION, es la expresión.
Un ejemplo simple de función esta seguidamente:
>>> def hola(arg):
... """El docstring de la función"""
... print "Hola", arg, "!"
...
>>> hola("Plone")
Hola Plone !
Argumentos y parámetros
Al definir una función los valores los cuales se reciben se denominan parámetros, pero durante la llamada los
valores que se envían se denominan argumentos.
Por posición
Cuando enviá argumentos a una función, estos se reciben por orden en los parámetros definidos. Se dice por tanto
que son argumentos por posición:
>>> def resta(a, b):
... return a - b
...
>>> resta(30, 10)
20
Sentencia pass
Es una operación nula — cuando es ejecutada, nada sucede. Eso es útil como un contenedor cuando una sentencia
es requerida sintácticamente, pero no necesita código que ser ejecutado, por ejemplo:
>>> # una función que no hace nada (aun)
... def consultar_nombre_genero(letra_genero): pass
...
>>> type(consultar_nombre_genero)
<type 'function'>
>>> consultar_nombre_genero("M")
>>>
>>> # una clase sin ningún método (aun)
... class Persona: pass
...
>>> macagua = Persona
>>> type(macagua)
<type 'classobj'>

