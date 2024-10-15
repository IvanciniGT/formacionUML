
Equipo de sonido
-----------------

PRREGUNTAS POCO DETALLADAS: ¿Qué puedes hacer?
Reproduce música: CASO DE USO
Reproducir música desde un vinilo: CASO DE USO (algo que alguien puede hacer con mi equipo de sonido) ¿Cómo se hace eso?

Puede estar encendido o apagado o reproduciendo música, averiado: ESTADOS EN LOS QUE SE PUEDE ENCONTRAR EL EQUIPO

Salidas de reproducción: Altavoz, autoriculares                 \
Controles de sonido (bajos, medios, graves... ecualizador)       > COMPONENTES DEL EQUIPO
Fuente de electricidad (Batería, red)                           /
Le puedo enchufar música por USB, Bluetooth, CD, Cassete, Vinilo, Ondas radiofónicas, etc.


PREGUNTAS MAS DETALLADAS: ¿Cómo lo haces?
Qué debo hacer para poner música desde un vinilo: DETALLE DE UNA ACTIVIDAD . Cómo reproduces música desde un vinilo

PREGUNTAS MAS DETALLADAS: Internamente qué hace el equipo de sonido para reproducir música desde un vinilo



Cómo lo control (interfaz)
Si es portátil o fijo
Si tiene entrada de micro

Cuánta pasta cuesta
De que material está hecho
Qué procedimiento debo seguir para instalarlo
Mantenerlo
Poner música desde la radio


---
Llevamos una secuencia a la hora de construir los diagramas: Son una herramienta para ayudarme a entender un sistema
Y el día 0 no soy capaz de tener una foto completa.
Cuando me meto a desarrollar un sistema, tardaré un AÑO: 365 días...
Y alñ final del camino será cuando tenga una visión HIPERDETALLADA DEL SISTEMA, que desde luego el día 1 no tengo.

El día 1 a lo mejor sé o NO lo que quiero/ espero de mi sistema:
Poder reproducir música de un vinilo! = IDEA / CONCEPTO = CASOS DE USO!

Y ahora tengo que ir desarrollandolo! Y serán muchas horas de muchos ingenieros!

DE LOS CASOS DE USO -> REQUISITOS ! Que empiezan a entrar en el detalle... un poquito!

# REQUISITOS para poder poner música desde un vínilo:

- Tener algo que lea vinilos
- Tener algo para reproducir sonido
- Tener algo para transmitir energía al aparato que lee vinilos
- Poder pedirle al aparato que quiero que reproduzca música desde un vinilo (PLAY)
- ...
- ...
- ...
- ...
---

Sistema para leer pasaportes en un aeropuerto:
CASOS DE USO:
- Emitir avisos cuando entre alguien fichado por la interpol.
- Registrar entradas y salidas del país.
- Garantizar la identificabilidad de la gente.


- REQUISITO DE ALTO NIVEL: NECESITO LEER PASAPORTES
  - Tener un aparto que lea pasaportes.. SI SII Evidente.. pero hay que presupuestarlo.
---

Quiero montar un microservicio de gestión de pedidos para Amazón

---

CASO DE USO DEL PROGRAMA: Qué? Qué hace el programa?
Quiero montar un programa que por las noches pase datos de la BBDD a a la BBDD b

REQUISITOS:
- Funcionales
  - Debo ser capaz de leer los datos de la BBDD a
  - Debo ser capaz de escribir los datos en la BBDD b
- No funcionales
  - Hardware
  - Seguridad
  - Rendimiento

COMPONENTES:
    - Componente: FUNCION: Lee datos de la BBDD a
    - Componente: FUNCION: Escribe datos en la BBDD b
    - Componente: FUNCION: Procesa datos que se hayan leído antes de escribirlos

Secuencia de trabajo:
    Componente que lee -> Componente que procesa -> componente que escribe