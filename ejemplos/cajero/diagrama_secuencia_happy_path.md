# Diagrama Secuencia: sacar dinero de un cajero

Dar un overview (CAMINO FELIZ) para que la gente empiece a entender la forma de operar con un cajero cuando voy a sacar pasta.


Representamos las comunicaciones que se hacen entre los distintos participantes de un PROCESO !

```mermaid

sequenceDiagram

    actor                      U as Usuario
    participant                C as Cajero
    participant                S as Servidor central

    U ->>+  C: Introducir tarjeta
    C -->>- U: Pedir PIN
    U ->>+  C: Entrego PIN
    C ->>+  S: Valida Tarjeta
    S -->>- C: OK
    C -->>- U: Pedir cantidad
    U ->>+  C: Entrego cantidad
    C ->>   C: Validar cantidad
    C ->>+  S: Retirar cantidad
    S -->>- C: OK
    C -->>  U: Entregar dinero
    C -->>-  U: Entregar tarjeta
```

---
# Diagrama Secuencia: intentar sacar dinero, pero el pin es incrorrecto

```mermaid

sequenceDiagram

    actor                      U as Usuario
    participant                C as Cajero
    participant                S as Servidor central

    U ->>  C:        Introducir tarjeta
    C -->> U:      Pedir PIN
    U ->>  C:      Entrego PIN malo
    C -->>  U: Mensaje pin incorrecto
    C -->> U:      Pedir PIN Segundo intento
    U ->>  C:      Entrego PIN malo otra vez
    C -->>  U: Mensaje pin incorrecto
    C -->> U:      Pedir PIN Tercer Y ULTIMO intento
    U ->>  C:      Entrego PIN malo otra otra vez
    C -->>  U: Mensaje pin incorrecto
    C -->> U:      Retener tarjeta

```

# Diagrama Secuencia: intentar sacar dinero, pero el pin es incrorrecto

```mermaid

sequenceDiagram

    actor                      U as Usuario
    participant                C as Cajero
    participant                S as Servidor central

    U ->>+  C:        Introducir tarjeta
    rect rgb(255,230,255)
        note right of C:    PIN

        loop              Hasta 3 intentos si no es válido

            rect rgb(255,255,230)
                note right of C:    Obtención del PIN

                C -->>- U:      Pedir PIN
                critical        En Espera de PIN
                    U ->>+  C:      Entrego PIN
                option          En 30 segundos no se introduce PIN
                    break
                    C -->> U:      Retener tarjeta
                    end
                end
            end
            rect rgb(230,255,255)
                note right of C:    Validación del PIN
                alt El PIN es válido
                    C ->>    C: Sigue su proceso
                else El PIN no es válido
                    C -->>    U: Mensaje pin incorrecto
                end
                end
        end
        rect rgb(230,255,230)
                note right of C:    Bloqueo de Tarjeta del PIN
            opt               Si el PIN no es válido
                C -->>- U:      Retener tarjeta
            end
        end
    end

```
