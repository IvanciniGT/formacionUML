# Diagrama de estados: CAJERO (Operativa de sacar dinero)

ESTADOS: 
    - Apagado
    - Encendido
        - Iniciando
        - Operativo
           - Reposo
           - Lectura de la tarjeta
           - Obtención del PIN
           - Solicitando Cantidad
           - Entregando cantidad
           - Operación fallida
        - Apagando

Sustantivos / Gerundios / Participios (algo que implique un ESTADO: Duración en el tiempo)
Las acciones son de corta duración: ALGO QUE EJECUTO Y TERMINO
Un estado es algo que dura en el tiempo: ALGO QUE ESTOY HACIENDO


TRANSICIONES POSIBLES:
Esa transiciones serían verbos

Apagado -> Encendido: Encender

Encendido -> Apagado: Apagar

---


```mermaid
stateDiagram-v2
direction LR

Encendido --> Apagado: Apagar
Apagado --> Encendido: Encender

```
---

```mermaid
stateDiagram-v2
direction LR

state Encendido {
    [*] --> Iniciando
    Iniciando --> Operativo
    Operativo --> Apagando
    Apagando --> [*]
}

Encendido --> Apagado: Apagar
Apagado --> Encendido: Encender

```
---

```mermaid
stateDiagram-v2
direction LR


state Operativo{
    [*] --> Reposo
    Reposo --> Ocupado
    Ocupado --> Reposo
    Reposo --> [*]

}

state Encendido {
    [*] --> Iniciando
    Iniciando --> Operativo
    Operativo --> Apagando
    Apagando --> [*]
}

Encendido --> Apagado: Apagar
Apagado --> Encendido: Encender

```


---

```mermaid
stateDiagram-v2
direction LR

Lectura: Lectura de la tarjeta
Pin: Obtención del PIN
Cantidad: Solicitando Cantidad
Entrega: Entregando cantidad
Fallo: Operación fallida

state validar_tarjeta <<choice>>
state leer_tarjeta <<choice>>
state validar_cantidad <<choice>>
state entregar_dinero <<choice>>

state Ocupado {
    [*] --> Lectura
    Lectura --> leer_tarjeta
    leer_tarjeta --> Pin
    Pin --> validar_tarjeta
    validar_tarjeta --> Cantidad
    Cantidad --> validar_cantidad
    validar_cantidad --> Entrega
    Entrega --> entregar_dinero
    leer_tarjeta --> Fallo
    validar_tarjeta --> Fallo
    validar_cantidad --> Fallo
    entregar_dinero --> [*]
    entregar_dinero --> Fallo
    Fallo --> [*]

}

state Operativo{
    [*] --> Reposo
    Reposo --> Ocupado
    Ocupado --> Reposo
    Reposo --> [*]

}

state Encendido {
    [*] --> Iniciando
    Iniciando --> Operativo
    Operativo --> Apagando
    Apagando --> [*]
}

Encendido --> Apagado: Apagar
Apagado --> Encendido: Encender

```
---

```mermaid
stateDiagram-v2
direction LR


Lectura: Lectura de la tarjeta
Pin: Obtención del PIN
Cantidad: Solicitando Cantidad
Entrega: Entregando cantidad
Fallo: Operación fallida

state validar_tarjeta <<choice>>
state leer_tarjeta <<choice>>
state validar_cantidad <<choice>>
state entregar_dinero <<choice>>
state Ocupado {
    [*] --> Lectura
    Lectura --> leer_tarjeta
    leer_tarjeta --> Pin
    Pin --> validar_tarjeta
    validar_tarjeta --> Cantidad
    Cantidad --> validar_cantidad
    validar_cantidad --> Entrega
    Entrega --> entregar_dinero
    leer_tarjeta --> Fallo
    validar_tarjeta --> Fallo
    validar_cantidad --> Fallo
    entregar_dinero --> [*]
    entregar_dinero --> Fallo
    Fallo --> [*]

}

```