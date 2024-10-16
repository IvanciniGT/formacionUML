
# Cajero automático

Queremos modelar un cajero.. En especial la operación de sacar dinero.

## 1. Casos de uso: 

- Actores: Quién va a usar el cajero?
   - Usuario/cliente
   - Empleado del banco
   - Persona de mantenimiento
- Actor no humano? 
  - Servidor central del banco
- Casos de uso: Qué puede hacer el cajero?
  - Usuario/cliente:
    - Validar tarjeta
    - sacar dinero   (relacionado con: consultar el dinero disponible en el cajero)
    - ingresar dinero
    - consultar saldo
  - Empleado del banco:
    - reponer dinero
    - consultar el dinero disponible en el cajero
  - Persona de mantenimiento:
    - abrir el cajero para repararlo
    - ver el estado del cajero

## 2. Requisitos:

Funcionales y no funcionales: Desgraciadamente en UML no existe una notación estándar para los requisitos. NO hay diagramas de requisitos. Aunque hacemos nuestros apaños.

### Nos centramos en el caso de uso: SACAR DINERO

Qué requisitos surgen de este caso de uso?

- Una persona debe poder sacar dinero si:
  Si tiene tarjeta, valida (no caducada) y sepa el pin.                 430
  Si tiene saldo                                                       1000
  Si hay dinero en el cajero                                            900 (depende de la estructura del saldo del cajero... Cuántos billetes hay de cada tipo)
  Si el cajero está operativo  

  Para definir casos de uso, nos ayuda mucho seguir una estructura de ejemplificación mediante 3 conceptos: GIVEN, WHEN, THEN (DADO, CUANDO, ENTONCES): Escenarios de USO

  RF01: Sacar dinero (HAPPY PATH)

    DADO: 
        - El cajero está operativo
        - El cajero tiene dinero
        - El usuario tiene tarjeta
        - La tarjeta no está caducada
        - El usuario conoce el pin
        - El usuario tiene saldo
        - Que la cantidad que quiere sacar es adecuada según el número de billetes que hay en el cajero
        - Que el servidor central del banco esté operativo
    CUANDO: 
        - El usuario introduce la tarjeta
        - Y el pin
        - Y la cantidad que quiere sacar
    ENTONCES:
        - El cajero entrega el dinero
        - Y actualiza el saldo del usuario
        - Y actualiza el saldo del cajero
        - Y le devuelve la tarjeta al usuario

  RF02: Intentar sacar dinero con una tarjeta caducada 

    DADO: 
        - El cajero está operativo
        - El usuario tiene tarjeta
        - La tarjeta está caducada
        - Y el usuario conoce el pin
    CUANDO:
        - El usuario introduce la tarjeta
        - Y mete el pin
    ENTONCES:
        - El cajero retiene la tarjeta
        - Y muestra un mensaje de error
 
  RF03: Intentar sacar dinero con un pin incorrecto

    DADO: 
        - El cajero está operativo
        - El usuario tiene tarjeta
        - La tarjeta no está caducada
        - Y el usuario no conoce el pin
    CUANDO:
        - El usuario introduce la tarjeta
        - Y mete el pin
    ENTONCES:
        - El cajero le informa de que el pin es incorrecto
        - Y le da otra oportunidad (un máximo de 3 intentos)
        - Si a la tercera oportunidad no acierta:
          - el cajero retiene la tarjeta
          - y muestra un mensaje de aviso al usuario

  RF04: Intentar sacar dinero con cajero no operativo
    
    DADO: 
        - El cajero no está operativo
    ENTONCES:
        - El cliente no puede ni siquiera introducir la tarjeta
        - Y se le informa de que el cajero no está operativo
  
  RF05: Intentar sacar dinero con saldo insuficiente

  RF06: Intentar sacar dinero con cajero sin dinero suficiente

  RF07: Intentar sacar dinero con cantidad no adecuada (billetes no cuadran)

  RF08: Intentar sacar dinero con servidor central del banco no operativo

  RF09: Intentar sacar dinero con tarjeta que no se puede leer

  RF10: Intentar sacar dinero con cajero sin papel

  RF11: Intentar sacar dinero con cuenta bloqueada

  ...

## 3. Comportamiento que debe tener el cajero?

### 3.1 Diagrama de estados: (MAQUINA DE ESTADOS)

Este está guay si tengo muy claro (o más o menos) como se comporta el sistema.
En un diagrama de estados representamos:
- Los posibles estados en los que se puede encontrar el sistema
- Las transiciones entre esos estados
- Eventos externos que provocan esas transiciones
- Guardias, efectos (acciones) asociadas a las transiciones

#### En nuestro cajero:

ESTADOS: 
- Apagado
- Fuera de servicio
- Actualizando
- Funcionando                       ESTADOS JERÁRQUICOS
  - Validando una tarjeta?
  - Esperando pin
  - Esperando opción
  - Preparando dinero
  - Validando cuenta/tarjeta
  - Validando existencias del cliente
  - Entregando dinero
  - Cerrando operación

TRANSICIONES POSIBLES:
- PTE
Todo esto lo representaremos en un diagrama de estados.

### 3.2 Diagrama de secuencia:

Este está guay si no tengo tan claro cómo se comporta el sistema.
En este diagrama representaremos todos los participantes en un caso de uso y cómo interactúan entre ellos. Nos centramos en sus comunicaciones: mensajes!!!!

#### Sacar dinero (HAPPY PATH)

    CLIENTE                 CAJERO                      SERVIDOR CENTRAL
    |                        |                              |
    |-- introduce tarjeta -->|                              |
    |<-- elegir operación ---|                              |
    |-- sacar dinero ------->|                              |
    |<-- dame el pin --------|                              |
    |-- mete el pin -------->|                              |
    |                        | <- Leer la tarjeta           |
    |                        | <- validar pin               |
    |                        | <- Validar caducidad         |
    |                        |--- Validar cuenta ---------->|
    |                        |                              | <- Validar cuenta
    |                        |<-- Cuenta, tarjeta: TODO OK -|
    |<-- cuanto quiere ------|                              |
    |-- quiero 300 billetes->|                              |
    |                        | <- Validar existencias       |
    |                        |--- Solicitará el dinero ---->| <- Validación de existencias
    |                        |<---- OK ---------------------|
    |<--- Entrega el dinero -|                              |
    |<- Mostrar un  mensaje -|                              |
    |<- Dar tarjeta ---------|                              |

    Esto mismo, podría escribirlo (explicarlo como texto):

    Llega el cliente y mete la tarjeta. Entonces el cajero le pide que introduzca el pin. El cajero lee la tarjeta y valida el pin. Valida la caducidad de la tarjeta y solicita al servidor central que valide la cuenta. Si todo está OK, el cajero solicita el dinero al servidor central. El servidor central le da el OK y el cajero entrega el dinero. Muestra un mensaje y devuelve la tarjeta.

## 4. Diagrama de componentes:

Donde empezará a definirse la arquitectura del sistema.

## 5. Diagrama de clases:

Podré empezar a definir cada componente del sistema.