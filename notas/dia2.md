
En esta fomación usaremos Mermaid y PlantUML para generar diagramas.
Lo que generan esas herramientas es PAPEL!
Eso implica que el mnto. de eso corre de nuestra cuenta.

Enterprise Architect es otra cosa... es una herramienta de modelización.
Lo que vamos construyendo es una BBDD de MODELOS, que posteriormente podemos representar en 1 o 17 diagramas.

Cualquier cambio que hacemos en un modelo, en automático se aplica a los 17 diagramas!

Crear gráficos en EA es horrible ... MAS QUE HORRIBLE (muchas horas de cajitas y ratón)
Crear gráficos con PlantUML y Mermaid es escribir texto (super cómodo)

Mantener diagramas con mermaid y plantuml es horrible ... MAS QUE HORRIBLE (muchas horas de reescribir 880 diagramas)
En cambio mantener diagramas en EA es super cómodo (cambias un modelo y en automático se actualizan los 880 diagramas)

---

Los diagramas que hacemos en UML deben representar la REALIDAD DE MI SISTEMA? NO!
Y cuidado con esto... Como quiera representar la realidad de un sistema, puedo necesitar MILES de hojas y miles de miles de horas pintando esas hojas... NO SE TRATA DE ESO! 

Se trata de ser capaces de TRANSMITIR INFORMACION UTIL A OTROS.
Qué quiero transmitir? Y entonces monto un diagrama que me ayude a transmitir ese concepto!

No confundamos LOS MODELOS con los diagramas que representan esos modelos.

El modelo va evolucionando según evoluciona el sistema (y se implementa) y acaba siendo MUY COMPLEJO!
El modelo representa la realidad del sistema.

Un diagrama es una visión que hago de un modelo!

Una persona (ser humano) es un ente muy complejo!
Pero no puedo confundir una persona con una FOTO de una persona.
Y de una persona puedo sacar 100 fotos diferentes... y en cada una contaré una cosa diferente, que me interesa en ese momento.

La persona es el modelo.
La foto es el diagrama.

Puedo poner a una persona haciendo el pino... si quiero transmitir que es una persona atlética.
Pero no estoy transmitiendo que es una persona también que estudia.
Puedo sacar otra foto de esa persona estudiando... y transmitir que es una persona que estudia.


---

Cuando tenemos 2 participantes en un sistema comunicándose, esas comunicaciones pueden ser:
- Síncronas:  No hago nada (dejo de hacer todo) hasta que no reciba respuesta al mensaje que mando.
- Asíncronas: Mando el mensaje y sigo con mi vida. No espero a la respuesta para seguir haciendo cosas.

2 participantes:
- Yo
- Mi madre

- Sistema: Mundo real

- Comunicándose:
- Mamá, que tienes hoy de comer?... que si me gusta me paso a verte!

    - Si llamo a mi madre por teléfono: Síncrona
    - Si le mando un whatsapp: Asíncrona

De qué depende el que quiera establecer una comunicación síncrona o asíncrona?
- En general es algo que me marcan los requisitos.
  - Voy a mercadona... hago la compra.... y tengo que pagar.
    Programa en el TPV de Mercadona        --->      Programa del banco (pasarela de pago) 
    Esa comunicación la quiero síncrona o asíncrona? SINCRONA !

        Puedo salir del mercadona con mi compra sin confirmación del banco? NO
        El programa del TPV del mercadona sigue con su vida mientras el banco no contesta? NO
        Queda a la espera de la respuesta del banco? SÍ
        - Si el banco dice que no: Me voy sin compra
        - Si el banco dice que sí: Me voy con compra
        - Si el banco no contesta: Me voy sin compra (Se cae la pasarela de pago del banco)

En lugar de estar en el Mercadona, estoy en un PEAJE!!!!
    Quiero salir, meto el ticket... meto la tarjeta...
    Como es esa comunicación? ASINCRONO!
    La TPV almacena la información del pago y me deja pasar.. sin que el pago se haya realizado.
    Por eso en un peaje me obligan a pagar con tarjeta de débito o crédito.. pero no se admiten tarjetas prepago.

    - Si el banco no contesta: Me voy con mi coche / No me dejan salir?
        - Y si soy una ambulancia que lleva a un tio con un infarto? Me dejan salir?

En una comunicación asíncrona, me quedo a la espera o no? Lo cierto es que un poquito si!
                              Servidor de Whatsapp
    Emisor  -- [whatsapp] --> Sistema de mensajería --> Destinatario
      YO √                                                MI MADRE
         ^
         Que el servidor de whatsapp lo tiene. Y entonces es cuando yo me puedo quedar tranquilo

En el mundo de la informática hay muchos servidores de mensajería: Kafka, RabbitMQ, ActiveMQ.

Os dije ayer también.... que en ocasiones, para comunicaciones SINCRONAS también uso sistemas de mensajería ASINCRONCRONOS!

Imaginad que no voy a hacer nada... no me muevo de la silla hasta que mi madre me conteste a mi pregunta: SINCRONA!
Si a mi madre la contacto por llamada de teléfono, qué pasa si no me contesta? Llamar de nuevo!
Y si no lo coge? Llamar de nuevo! Y así 40 veces.. que hartura!!!

También puedo optar por el uso de un sistema de mensajería asíncrono: Whatsapp!
Mando el mensaje... el servidor de whatsapp me dice que ok... Y yo no me muevo de la pantalla del móvil hasta que mi madre me conteste... pero de que me he liberado? De estar llamando 40 veces!

Llevaros esto al mundo de la informática:

        Programa ------>
        Programa ------> [ COLA ] Servidor
        Programa ------>
              le pide algo

Y el servidor tiene una determinada capacidad X de trabajo (es capaz de asumir cierta carga de trabajo por unidad de tiempo)
Y en un momento dado dado, el servidor no contesta porque está petao!
Y qué hago yo? Volver a llamar!
Y no contesta .. y vuelvo a llamar!

Qué es lo que estoy consiguiendo? Saturar más aún al servidor!

El procedimiento asíncrono ME GARANTIZA LA ENTREGA DEL MENSAJE!
Ya se procesará cuando sea.. y yo a lo mejor ESTOY A LA ESPERA !

Eso de "GARANTIZA" es un poco relativo... porque si el sistema de mensajería se cae... jodidos estamos! Lo que pasa es que este tipo de herramientas suelen ser muy muy robustas.