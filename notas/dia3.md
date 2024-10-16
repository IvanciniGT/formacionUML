
# Diagramas de máquinas de estados / Diagramas de estados

Estado: Situación en la que se encuentra un objeto o sistema en un momento dado.
Transición: Cambio de estado de un objeto o sistema. (Estado A -> Estado B)
Evento: Acciones externas al sistema que provocan una transición.
Contexto: Propiedades / Variables / Datos que influyen en las transiciones.
Acción:   Cambios en el contexto (en las variables) que se producen al realizar una transición.
Guarda: Condición que debe cumplirse para que se produzca una transición.

Cómo se representa en UML:
Estado: Caja
Transición: Flecha

Las otras 3 se representan en medio de las flechas... como texto
Acciones                                / dato=7;
Guardas (condición):                    [condicion]
Eventos                                 EVENTO

Se pueden mezclar entre si:
    EVENTO /dato=7;
    [condicion] /dato=7;