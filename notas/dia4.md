
# Programación orientada a objetos

En todo lenguaje de programación, tengo tipos de datos.
            Se caracteriza por          Operativas
    Fecha:  día, mes, año               caes en Jueves?   Cuantos días hay entre 2 fechas?
    String: secuencia de caracteres     concatenar, buscar, reemplazar, ponte en mayúsculas
    Numero: valor numérico              sumar, restar, multiplicar, dividir, valor absoluto
    Entero

Hay lenguajes que me permiten definir mis propios tipos de datos.
Algunos de ellos solo me permiten definir tipos de datos que tengan asociadas características: 
    - C: Struct
    - ADA: record

Hay lenguajes que me permiten definir tipos de datos que tengan asociadas características y operaciones propias de ellos (funciones): POO

    Una clase es un nuevo TIPO DE DATO que tendrá sus características y operaciones propias.
    Una vez le explicamos al lenguaje de programación lo que es un nuevo tipo de dato (CLASE), podemos crear datos concretos de ese tipo (OBJETO o INSTANCIA).

    Depende del lenguaje hay características más o menos avanzadas: Herencia(simple/multiple), polimorfismo, encapsulamiento, etc.

---

## Programa de hace 38 años: GW-BASIC

CLASE:

aaaaa<<<
AAAAA<<<

aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa<<<
aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa<<<


PROGRAMA.codigo
aaaaa<<<
AAAAA<<<
XXXX
XXXX
XXXX

xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx


xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa<<<
aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa<<<
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxx


xxxxxxxx
xxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa<<<
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa<<<
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxx


xxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa<<<

xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa<<<
xxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxx
xxxxxxxx


---

Cocina:
RECETA:
Ingredientes (variables)
Pasos        (algoritmo)

PURO LENGUAJE IMPERATIVO
----> EVOLUCION PROCEDIMIENTOS

- Croquetas de jamón                                    -> Bechamel
- Berenjenas rellenas                                   -> Bechamel
- Salmón con una bechamel de espinacas en hojaldre      -> Bechamel

Cuento el algoritmo de preparación de la bechamel una vez o mejor creo un procedimiento de preparación de la bechamel y lo reutilizo en las recetas que lo necesiten.

Eso me ayuda mucho: 
- De cara al mnto de la receta: Mejoro el proceso de preparación de la bechamel me aplica a todas las recetas que la usen y todas mejoran.
- Poder escribir nuevas recetas que usen bechamel más rápido
- De cara a entender las recetas

----> EVOLUCION ORIENTACION A OBJETOS

Voy a crear a un PreparadorDeBechamel que me permita preparar bechamel de forma más sencilla y reutilizable.

Y cuando lo necesite, le pido a mi PreparadorDeBechamel que me prepare la bechamel.

Y tengo al PreparadorDeBechamel que me prepara la bechamel.
Y tengo a preparador de carne que me prepara la carne.
Y tengo a preparador de pescado que me prepara el pescado.


C -> C++ (Incremento sobre C, es C con POO)

     C# -> C++
            ++

++ (INCREMENTO)

La POO: Me ofrece un nivel de:
- Reutilización del código muy superior a la programación imperativa / procedural
- Facilidad para el mnto   muy superior a la programación imperativa / procedural
- Facilidad para las pruebas muy superior a la programación imperativa / procedural

PYTHON
JAVASCRIPT
JAVA
C++
C#

PHP, Go, Rust, Swift, Kotlin, Typescript

Al diseñar un sistema con POO acabamos con muchos (muchísimos) tipos de objetos (CLASES), que se relacionan entre si. Para entender bien un sistema, me ayuda mucho poder representar visualmente esos TIPOS DE OBJETOS y sus relaciones: DIAGRAMAS DE CLASES

BBDD Relacionales: Diagramas ENTIDAD-RELACION

En UML un diagrama entidad relación es un subconjunto de un diagrama de clases.

---
Modelos: Tipo de clase que desarrollamos para representar un objeto en la vida real.

