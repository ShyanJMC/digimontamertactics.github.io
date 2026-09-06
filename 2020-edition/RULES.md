# Digimon Card Game — Reglas Completas (edición 2020 en adelante)

Extracto revisado y organizado a partir de las fuentes **oficiales** de Bandai. Toda cita `(RM x-y-z)` remite al número de cláusula correspondiente en el **Comprehensive Rules Manual Ver. 4.2** (ver `pdfs/Comprehensive_Rules_v4.2_EN_2026-08-18.pdf`), que es el documento legal completo del juego.

## 0. Fuentes usadas

| Documento | Versión | Última actualización | Archivo local |
|---|---|---|---|
| Official Rule Manual (guía ilustrada para principiantes) | Ver. 6.0 | 2026/04/01 | `pdfs/Official_Rule_Manual_v6.0_EN_2026-04-01.pdf` (+ versión JA) |
| **Comprehensive Rules Manual** (reglamento legal completo, fuente principal de este documento) | **Ver. 4.2** | **2026/08/18** | `pdfs/Comprehensive_Rules_v4.2_EN_2026-08-18.pdf` (+ versión JA, autoridad final ante conflictos) |
| Digimon Card Game Glossary (glosario para jugadores nuevos) | — | 2023/08/21 | `pdfs/Glossary_EN_2023-08-21.pdf` |
| Bandai Organized Play Tournament Rules Manual | — | 2024/06/06 | `pdfs/Tournament_Rules_Manual_2024-06-06.pdf` |
| Errata Card List (listado de cartas con texto corregido) | — | 2026/05/15 | `pdfs/Errata_Card_List_2026-05-15.pdf` |

**Nota importante de Bandai:** ante cualquier discrepancia entre el reglamento en japonés y las traducciones (incluida la inglesa usada aquí), **el texto japonés siempre tiene prioridad**. No existe una lista pública oficial de versiones históricas del reglamento para descarga — Bandai solo publica la versión vigente y la reemplaza en el sitio, por eso este extracto refleja el estado **actual (Ver. 4.2)**, no cada versión que existió desde 2020.

No hay un documento único de "FAQ oficial": las rulings específicas de carta por carta se consultan cláusula por cláusula desde la herramienta de búsqueda en `world.digimoncard.com/rule/?card_no=XXXX`. Lo que sí es un FAQ estructurado y oficial es el propio Comprehensive Rules Manual, que resuelve la enorme mayoría de dudas de interacción de reglas mediante sus más de 1.390 cláusulas numeradas y ejemplos. Este documento organiza y traduce/parafrasea ese contenido.

---

## 1. Resumen rápido

- Juego de cartas 1 vs 1 de Bandai, relanzado el **24/04/2020** (Starter Decks ST-01/02/03 + booster BT-01).
- Cada jugador arma: un **mazo de 50 cartas** (Digimon, Tamer y Option) + opcionalmente un **mazo Digi-Egg de hasta 5 cartas**.
- Se gana atacando con éxito al rival cuando su pila de seguridad está en 0, o si el rival no puede robar por tener el mazo vacío. *(RM 1-2-3)*
- El recurso central es el **Memory Gauge**, compartido entre ambos jugadores, que determina cuándo termina tu turno.

---

## 2. Construcción de mazo *(RM 1-4)*

- **Mazo principal:** exactamente 50 cartas, ni más ni menos. Máximo 4 copias de una carta con el mismo número de carta. *(RM 1-4-1-2)*
- **Mazo Digi-Egg:** 5 cartas o menos (puede tener 0). Mismo límite de 4 copias por número de carta. *(RM 1-4-1-3)*
- **Tokens:** no van en el mazo; se preparan aparte solo si algún efecto los necesita. *(RM 1-4-4)*
- **Index** (chuleta de referencia de palabras clave): no es una carta de mazo, no tiene efecto en la partida, se puede consultar en cualquier momento. *(RM 1-4-5)*

---

## 3. Objetos necesarios *(RM 1-4)*

- Mazo + mazo Digi-Egg.
- **Memory Gauge**: va de -10 a +10 con el 0 en el centro; el lado izquierdo es tu memoria, el derecho la de tu rival. Nunca puede pasar de 10 en ningún lado. *(RM 1-4-2)*
- Un **marcador** (memory marker) compartido para señalar el valor actual.
- Contadores/dados opcionales para llevar cuenta de otros valores.

---

## 4. Zonas de juego *(RM 3)*

| Zona | Pública/Privada | Notas |
|---|---|---|
| **Deck** | Privada | Boca abajo, orden no se puede alterar. |
| **Digi-Egg Deck** | Privada | Boca abajo, orden no se puede alterar. |
| **Campo (Field)** | Pública | Se divide en área de cría y área de batalla. |
| **Área de cría (Breeding Area)** | — | Solo 1 carta a la vez. Las cartas aquí **no** son afectadas por efectos, no activan gatillos, no pueden elegirse, salvo que el efecto lo mencione explícitamente. *(RM 3-4-7)* |
| **Área de batalla (Battle Area)** | Pública | Cualquier cantidad de cartas. Solo Digimon nivel 3+ pueden estar aquí de forma estable. |
| **Mano** | Privada (el dueño la ve libremente) | Orden libre. |
| **Trash** (descarte) | Pública | Boca arriba, en pila. |
| **Pila de seguridad** | Privada | Boca abajo, pero *desplegada* para que se vea la cantidad de cartas. |

Reglas generales de zonas: al moverse de área una carta se convierte en una "carta nueva" (pierde estados/efectos previos) *(RM 3-1-3-1)*; cuando varias cartas salen de un área al mismo tiempo, se consideran movidas simultáneamente y el dueño del efecto que las movió elige el orden en que se colocan *(RM 3-1-3-4)*.

---

## 5. Terminología básica clave *(RM 4)*

- **Memory / costo:** pagar un costo mueve el marcador X espacios hacia el lado del rival. Nunca se paga de más ni de menos que el valor exacto. *(RM 4-2-2)*
- **Digimon:** las cartas Digi-Egg y Digimon puestas en el campo se tratan como "Digimon". Heredan los *inherited effects* de las cartas de digivolución debajo suyo. *(RM 4-3)*
- **Tamers:** cartas Tamer puestas en el campo.
- **Security Digimon:** una carta Digimon revelada desde la pila de seguridad al hacer un chequeo de seguridad. *(RM 4-5)*
- **Cartas DUAL:** cartas que pueden tratarse como Digimon u Option (el jugador declara cuál usa). *(RM 4-6)*
- **Cartas apiladas (Stacked cards):** todas las cartas de digivolución bajo un Digimon. El orden de apilado no puede cambiarse; si se retira la carta de arriba, la revelada. *(RM 4-7)*
- **Cartas de Link:** se insertan de costado (no cuentan como "apiladas"); máximo 1 carta de link por Digimon. *(RM 4-9)*
- **Orientación:** una carta está "sin suspender" (vertical) o "suspendida" (horizontal). *(RM 4-13)*
- **Overflow:** regla de las cartas ACE — al salir del campo, mueve el marcador de memoria según el valor indicado. *(RM 4-19)*
- **Arts Digivolve:** regla de cartas DUAL — en vez de mandar al trash una Option usada, una carta propia en el campo puede digivolucionar a esa carta DUAL sin pagar costo. *(RM 4-20)*
- **Tokens:** cartas no-mazo jugadas por efectos; no pueden apilarse ni tener link; al salir del campo se eliminan del juego. *(RM 4-21)*
- **Requisitos de color:** para usar una Option se necesita un Digimon o Tamer propio del mismo color en el campo. *(RM 4-22)*

---

## 6. Preparación de la partida *(RM 5)*

1. Cada jugador baraja su mazo y su mazo Digi-Egg; ambos se colocan boca abajo.
2. Piedra-papel-tijera decide quién empieza.
3. Ambos roban 5 cartas como mano inicial.
4. **Mulligan (opcional, una sola vez por jugador):** empezando por el primer jugador, cada uno puede devolver toda su mano al mazo, barajar y robar 5 cartas nuevas. *(RM 5-2-1-4/5)*
5. Se toman las 5 cartas superiores del mazo y se colocan boca abajo, sin mirarlas, como pila de seguridad (la carta superior del mazo queda como la carta *inferior* de la pila de seguridad). *(RM 5-2-1-6)*
6. El marcador de memoria se pone en 0.
7. Empieza el turno del primer jugador.

---

## 7. Estructura del turno *(RM 6)*

Un turno avanza por estas fases, en orden fijo, y **no pasa a la siguiente hasta resolver todo lo pendiente de la actual**:

1. **Unsuspend Phase:** el jugador de turno "des-suspende" (endereza) todas sus cartas del campo a la vez. *(RM 6-2)*
2. **Draw Phase:** roba 1 carta. **El primer jugador no roba en su primer turno.** *(RM 6-3)*
3. **Breeding Phase:** una sola acción entre: eclosionar un Digi-Egg, mover una carta del área de cría al área de batalla, o no hacer nada. *(RM 6-4)*
4. **Main Phase:** el jugador de turno puede, en cualquier orden y cuantas veces quiera (siempre que no haya nada pendiente sin resolver): jugar un Digimon/Tamer, digivolucionar, usar una Option, hacer link, atacar, activar un efecto de tipo activación, o **pasar**. *(RM 6-5)*

### Fin de turno — el Memory Gauge

- **Condición de fin de turno:** se cumple en cuanto la memoria está en 1 o más del lado del rival Y no queda ningún proceso pendiente en la fase actual → el turno termina ahí mismo, en la fase en la que estés. *(RM 6-1-4)*
- Pasar ("pass") mueve inmediatamente la memoria a 3 del lado del rival. *(RM 6-5-1-7)*
- Si la memoria queda en 0 o más del lado del jugador de turno al llegar el fin de turno, **el fin de turno se pospone** y la fase actual continúa. *(RM 6-6-4)*
- No hay "pasos" fijos de intercambio de turno como en otros TCG: el turno se termina dinámicamente en cuanto cruzás la memoria al terreno rival. Esto es lo que le da al juego su ritmo característico: jugar de más puede regalarle el turno al rival.

---

## 8. Jugar una carta, DigiXros y Assembly *(RM 7)*

### Jugar una carta (regla base)
1. Se declara y se revela la carta.
2. Se paga el costo de juego.
3. Se coloca en el campo (sin suspender) y se resuelve el procedimiento. *(RM 7-1-3)*

Un Digimon/Tamer recién jugado **no puede atacar el turno que entra**, salvo que tenga `<Rush>`. *(RM 7-1-2-1, RM 1-3-1)*

### DigiXros *(RM 7-2)*
- Al jugar un Digimon con requisitos de DigiXros, podés colocar cualquier cantidad de las cartas especificadas (desde mano y/o área de batalla) debajo de la carta jugada; el costo de juego baja según el valor indicado **por cada carta colocada**.
- Se declara justo antes de pagar el costo de juego (después de que se resuelvan los efectos "on play" que gatillan al jugar la carta).
- No es obligatorio. Si se coloca 0 cartas, no se considera que hubo DigiXros aunque se haya declarado.
- El orden de apilado sigue el orden mostrado en los requisitos de DigiXros (de izquierda a derecha = de arriba a abajo), salvo que el requisito indique cantidades, en cuyo caso el jugador elige el orden.

### Assembly *(RM 7-3)*
Igual mecánica que DigiXros pero usando cartas del **trash** en vez de mano/campo, y con una cantidad *exacta* de cartas a colocar (no "hasta X", sino el número exacto especificado).

---

## 9. Digivolución *(RM 8)*

### Digivolución estándar
1. Se revela 1 carta Digimon de la mano y se elige 1 requisito de digivolución de esa carta.
2. Se elige la carta propia del campo que cumple el requisito.
3. Se paga el costo de digivolución.
4. Se coloca encima, **se roba 1 carta como bono**, y se resuelve.

La carta digivolucionada **hereda la orientación** (suspendida/sin suspender) de la carta base. *(RM 8-1-2-3)*

### DNA Digivolution *(RM 8-2)*
Combina **múltiples** cartas propias del campo en 1 sola carta Digimon revelada con `[DNA Digivolution]`. A diferencia de la digivolución normal:
- La carta de arriba entra **sin suspender**, sin heredar el estado previo.
- Todas las cartas que pasan a ser digivolución se tratan como **cartas nuevas** (pierden link, efectos aplicados, cuenta de "X per turn", etc.).
- Si el Digimon estaba atacando o era objetivo de ataque, eso se considera terminado.

### Burst Digivolve *(RM 8-3)*
Se revela una carta con `[Burst Digivolve]`, se devuelve 1 Tamer propio del área de batalla a la mano (según lo que indique la carta), y esa carta digivolve gratis/con descuento. Al final del turno en que ocurrió, se manda al trash la carta superior de la pila resultante (pending processing).

### App Fusion *(RM 8-4)*
Se revela una carta con `[App Fusion]`, se elige un par de cartas **linkeadas** en el área de batalla que coincida con los requisitos, y se apila la **carta de link** de esas cartas encima del Digimon revelado (digivolucionando el conjunto).

---

## 10. Usar cartas (Option) *(RM 9)*

1. Se declara el uso y se revela la Option.
2. Se paga el *use cost*.
3. Se activa su primer efecto `[Main]`.

Mientras se resuelve, la carta usada **no está en ninguna zona**; en cuanto termina de resolverse su primer `[Main]`, se manda al trash automáticamente (pending processing), salvo que algún efecto la coloque en otra zona (p. ej. cartas DUAL con Arts Digivolve). Se usa 1 carta a la vez.

---

## 11. Link *(RM 10)*

Una carta con `[Link]` se enchufa de costado en un Digimon propio del área de batalla que cumpla el requisito de link, pagando su *link cost*. Si el Digimon ya tenía una carta apilada, la de link nueva se inserta abajo del todo.

---

## 12. Atacar *(RM 11)*

El ataque avanza por **timings fijos**, cada uno debe resolverse por completo antes de pasar al siguiente:

1. **Attack Declaration:** el jugador de turno suspende 1 Digimon del área de batalla y elige el objetivo: el jugador rival, o 1 Digimon suspendido del rival. *(RM 11-2)*
2. **Counter Timing:** el rival puede activar (como máximo) 1 efecto `[Counter]` por ataque. *(RM 11-3)*
3. **Block Timing:** el rival puede suspender un Digimon con `<Blocker>` para redirigir el ataque hacia él. *(RM 11-4, ver §13)*
4. **Confirmar si el ataque tiene éxito:** *(RM 11-5)*
   - Si el objetivo es el jugador y tiene 1+ cartas de seguridad → se hace un **chequeo de seguridad**.
   - Si el objetivo es el jugador y tiene 0 cartas de seguridad → **¡gana la partida quien ataca!** (excepto si el Digimon atacante no puede hacer ningún chequeo de seguridad).
   - Si el objetivo es un Digimon → ocurre una **batalla**.
   - Si el atacante fue eliminado antes de esta instancia, el ataque no tiene éxito y termina sin efecto.
5. **End of Attack:** el ataque termina una vez resuelto todo lo pendiente.

Reglas clave: solo puede atacar el jugador de turno; 1 Digimon = 1 ataque, no se puede atacar con varios a la vez; no se puede declarar un nuevo ataque durante otro ataque (ni con `<Blitz>`); un Digimon que no puede suspenderse no puede atacar.

---

## 13. Bloquear *(RM 12)*

- Un bloqueo cambia el objetivo del ataque a un Digimon propio con `<Blocker>`, suspendiéndolo.
- **Solo 1 bloqueo por ataque.** No se puede declarar un nuevo bloqueo durante un bloqueo ya en curso.
- Un Digimon que no puede suspenderse no puede bloquear.
- El Digimon que ya era el objetivo del ataque no puede bloquear (no tiene sentido bloquearse a sí mismo).
- Solo puede bloquearse si el atacante sigue en el área de batalla.

---

## 14. Chequeos de seguridad *(RM 13)*

1. Se revela la carta superior de la pila de seguridad (si ya estaba revelada, sigue así).
2. Si algún efecto se gatilla por el chequeo, se resuelve antes de seguir.
3. Si la carta revelada es un Digimon (**Security Digimon**), ocurre una **batalla** contra el atacante.
4. La carta revelada se manda al trash (salvo que un efecto la reubique).
5. Si el Digimon que chequeó puede hacer *otro* chequeo (p. ej. por `<Security Attack +1>`), se repite el proceso.

Solo se puede hacer **1 chequeo por ataque**, salvo que un efecto del atacante modifique esa cantidad (ver `<Security A.>` en la tabla de keywords). El chequeo es siempre obligatorio si corresponde.

---

## 15. Batallas *(RM 14)*

Una "batalla" es simplemente comparar el DP de dos cartas:

- Mayor DP gana; el de menor DP **se elimina inmediatamente**.
- Si hay empate de DP, **ambos pierden** (ambos se eliminan a la vez).
- **Los Security Digimon nunca se eliminan** aunque pierdan la batalla (solo se manda al trash la carta revelada por el chequeo, como ya indica el proceso de chequeo).

---

## 16. Reglas de efectos — cómo se resuelve todo *(RM 15)*

Esta es la sección más "abogado de reglas" del juego — resuelve casi cualquier disputa de interacción.

### 16.1 Categorías de efecto *(RM 15-8)*

| Categoría | Cómo funciona |
|---|---|
| **Persistent** | Activo todo el tiempo mientras se cumplan sus condiciones, sin "gatillarse". Deja de aplicar apenas deja de cumplirse la condición. Si varios persistentes chocan, gana el que se activó después (salvo que sea un efecto prohibitivo). |
| **Trigger-type** | Se gatilla apenas se cumple su condición (aunque estés en medio de resolver otra cosa) y queda "pendiente de activación" hasta que le toque activarse. |
| **Activation-type** | Efectos opcionales tipo `[Main]` que el jugador declara activar en su main phase cuando no hay nada pendiente. |
| **Immediate-type** | Se gatilla e **interrumpe justo antes** de la causa (texto "when X would..."). A diferencia de los trigger-type, no esperan cola: cortan el proceso en el momento exacto. Solo pueden activarse una vez por causa hasta que esa causa se resuelva. |

### 16.2 Simultaneidad y orden de activación *(RM 15-4)*

- Si varios efectos se gatillan al mismo tiempo, **el jugador de turno elige y activa los suyos primero, uno por uno**, hasta que no le queden pendientes; recién ahí el rival hace lo mismo con los suyos. *(RM 15-4-3-5)*
- Un efecto "derivado" (que se gatilla mientras se están resolviendo otros efectos simultáneos) se activa **antes** que los que ya estaban en cola, incluso si es del jugador no-de-turno. *(RM 15-4-5)*
- Si en algún momento simultáneo hay dudas de prioridad, **el efecto `[Security]` siempre tiene prioridad** sobre cualquier otro que se gatille al mismo tiempo — se activa inmediatamente, sin quedar pendiente. *(RM 15-16-10-2)*

### 16.3 Principios fundamentales *(RM 1-3)*

- El texto de una carta **siempre** tiene prioridad sobre la regla general (ej: `<Rush>` permite atacar el turno que entra, pese a la regla base que lo prohíbe).
- Un efecto prohibitivo ("no puede") siempre gana sobre uno habilitante ("puede").
- Si se pide una acción imposible, no se hace; si es parcialmente imposible, se hace lo que sí se pueda.
- Los costos nunca terminan siendo negativos (se limitan a 0).
- Si dos jugadores deben elegir algo al mismo tiempo, **el jugador de turno elige primero**.
- Al modificar un valor numérico varias veces, primero se suman/restan todas las modificaciones entre sí y **después** se aplica el resultado neto al valor original (ej: +3000 y -2000 DP simultáneos → se aplica +1000 neto).

### 16.4 Timings de efecto más comunes *(RM 15-16)*

| Icono | Se gatilla quando... |
|---|---|
| `[On Play]` | Termina la acción de jugar la carta |
| `[When Digivolving]` | Termina la acción de digivolucionar a esa carta |
| `[On Deletion]` | La carta con el efecto es eliminada |
| `[When Attacking]` | Se declara el ataque con esa carta |
| `[When Linking]` | La carta pasa a ser carta de link |
| `[When Moving]` | La carta se mueve (cría → batalla) |
| `[Main]` | Efecto de activación en tu main phase |
| `[Counter]` | Timing de contraataque del rival |
| `[Security]` | Se hace un chequeo de seguridad sobre esa carta |
| `[Start/End of Your Turn]`, `[Start/End of Opponent's Turn]`, `[All Turns]` | Inicio/fin de turno respectivo, o ambos |
| `[Start of Your/Opponent's Main Phase]` | Al llegar el main phase respectivo |
| `[End of Attack]` | Termina el ataque hecho con esa carta |

### 16.5 Efectos ganados, información añadida/cambiada *(RM 15-12, 15-13)*

- Una carta puede "ganar" un efecto de otra fuente; si eso pasa, conserva ese efecto (y su estado) aunque se apilen o quiten cartas encima. *(RM 15-13)*
- Los efectos que **agregan** información (DP/costo/nivel) se acumulan salvo que la misma fuente ya la haya puesto antes (ahí se sobreescribe). Los efectos **persistentes** siempre ganan por sobre modificaciones puntuales pasadas, mientras sigan activos.
- Los efectos que **cambian** información (ej: cambiar el nombre de una carta) no pueden aplicarse sobre datos que la carta no tenía originalmente.

### 16.6 Bucles infinitos *(RM 18-3)*

Si un set de procesos se repite indefinidamente y ningún jugador puede pararlo, la partida **termina en empate**. Si alguno puede pararlo, se le pide declarar cuántas veces lo repite (turno primero el jugador de turno), se ejecuta esa cantidad y se corta.

---

## 17. Palabras clave (Keyword Effects) — glosario completo oficial *(RM 16)*

Las 47 palabras clave vigentes en Ver. 4.2, con la definición oficial resumida:

| # | Keyword | Definición |
|---|---|---|
| 16-4 | **`<Security A. ±X>`** | Modifica la cantidad de chequeos de seguridad que hace ese Digimon al atacar. Efecto persistente; si un mismo Digimon tiene varias instancias, se suman los valores (pero no se convierte en un solo `<Security A. +N>`). Nunca baja de 0 chequeos reales. |
| 16-5 | **`<Blocker>`** | Permite, suspendiendo ese Digimon, convertirlo en el objetivo del ataque (bloquear). Persistente. Solo 1 bloqueo por Digimon por timing de bloqueo aunque tenga varias instancias. |
| 16-6 | **`<Recovery X>`** | Devuelve X cartas del trash a la pila de seguridad. |
| 16-7 | **`<Piercing>`** | Si este Digimon elimina al rival en batalla, igual hace un chequeo de seguridad antes de terminar el ataque. Es trigger-type; el chequeo es obligatorio; si no hay Digimon disponible para chequear, no pasa nada. |
| 16-8 | **`<Draw X>`** | Robás X cartas del mazo. Obligatorio. |
| 16-9 | **`<Jamming>`** | Este Digimon no es afectado por [Blocker]/[Security A.]/similares del rival durante la batalla que libra (persistente, según texto exacto de la carta). |
| 16-10 | **`<Digisorption>`** | Al digivolucionar a este Digimon, podés suspender 1 Digimon propio para obtener un beneficio (efecto inmediato al momento de la digivolución). |
| 16-11 | **`<Reboot>`** | Este Digimon se des-suspende (fuera de fase). Persistente, obligatorio, ocurre junto al des-suspendido normal de la unsuspend phase. |
| 16-12 | **`<De-Digivolve X>`** | El jugador manda al trash X cartas de digivolución de un Digimon elegido, empezando de arriba. No puede bajar a un Digimon de nivel 3 o menos. Obligatorio una vez activado. |
| 16-13 | **`<Retaliation>`** | Si en una batalla **solo** este Digimon fue eliminado, se elimina también al que lo eliminó. Trigger-type, obligatorio. |
| 16-14 | **`<Digi-Burst>`** | Ejecuta otro efecto especificado por esta carta (opcional). |
| 16-15 | **`<Rush>`** | Puede atacar el mismo turno en que fue jugado/entró al campo. Persistente. |
| 16-16 | **`<Blitz>`** | Puede atacar aunque ya haya declarado un ataque este turno, siempre que la memoria rival esté en 1+ (no puede usarse si la memoria propia del rival está en 0 o menos). |
| 16-17 | **`<Delay>`** | Mientras esté en el área de batalla, puede impedir alguna acción específica del rival (según el texto exacto). No puede activarse el mismo turno que se jugó la carta con este efecto. |
| 16-18 | **`<Decoy>`** | Cuando otro Digimon propio especificado sería eliminado, podés eliminar este Digimon en su lugar (inmediato, opcional). |
| 16-19 | **`<Armor Purge>`** | Cuando este Digimon sería eliminado, podés mandar al trash la carta superior de su pila para evitar la eliminación (inmediato, opcional). |
| 16-20 | **`<Save>`** | Permite colocar esta carta debajo de 1 Tamer propio (en vez del trash) al ser eliminada. Opcional. |
| 16-21 | **`<Material Save>`** | Al eliminarse, sus cartas de digivolución (o parte de ellas, según DigiXros) se colocan bajo un Tamer en vez de ir al trash. |
| 16-22 | **`<Evade>`** | Suspendiendo este Digimon, evita que sea eliminado (inmediato, opcional). |
| 16-23 | **`<Raid>`** | Puede cambiar el objetivo del ataque hacia el Digimon rival sin suspender de mayor DP. Trigger, opcional; si hay empate entre varios candidatos, el rival elige cuál. |
| 16-24 | **`<Alliance>`** | Al atacar, suspendiendo otro Digimon propio, este Digimon suma el DP del suspendido al suyo para esa batalla/ataque. Trigger, opcional. |
| 16-25 | **`<Barrier>`** | Mandando al trash la carta superior de tu pila de seguridad, este Digimon evita ser eliminado. Inmediato, opcional. |
| 16-26 | **`<Blast Digivolve>`** | Permite digivolucionar instantáneamente a un Digimon propio como parte del efecto (sin pasar por la acción normal de digivolución en main phase). |
| 16-27 | **`<Fortitude>`** | Si este Digimon (con cartas de digivolución) es eliminado, podés volver a jugarlo sin pagar costo. Trigger, obligatorio. |
| 16-28 | **`<Mind Link>`** | Coloca a un Tamer con este efecto de una forma especial (según texto de la carta). |
| 16-29 | **`<Partition>`** | Al chocar/interactuar con otro Digimon específico, se coloca 1 de cada carta especificada en cierta zona (opcional). |
| 16-30 | **`<Collision>`** | Mientras este Digimon está atacando, obliga a todos los Digimon del rival aptos a ganar `<Blocker>` (persistente, se activa solo mientras dura el ataque). |
| 16-31 | **`<Blast DNA Digivolve>`** | Realiza una DNA Digivolution instantánea sobre Digimon propios especificados, como parte del efecto. |
| 16-32 | **`<Scapegoat>`** | Eliminando a otro Digimon propio, evita que este sea eliminado. Inmediato, opcional. |
| 16-33 | **`<Vortex>`** | Permite atacar a un Digimon del rival al final de tu turno, incluso el turno en que fue jugado. Trigger, opcional. |
| 16-34 | **`<Overclock>`** | Al final de tu turno, eliminando 1 Token u otro Digimon propio especificado, obtenés un efecto. Trigger, opcional. |
| 16-35 | **`<Iceclad>`** | Cambia las reglas de la batalla: en vez de comparar DP, se compara la cantidad de cartas de digivolución de cada Digimon (gana quien tenga más; empate = ambos pierden). |
| 16-36 | **`<Decode>`** | Cuando este Digimon sería [algo específico según texto], podés evitarlo (inmediato, opcional). |
| 16-37 | **`<Fragment>`** | Cuando este Digimon sería [algo específico], se elige y se manda al trash una cantidad de cartas especificada (opcional). |
| 16-38 | **`<Execute>`** | Al final de tu turno, este Digimon ataca y luego se elimina a sí mismo. Trigger, opcional. |
| 16-39 | **`<Progress>`** | Mientras ataca, este Digimon no es afectado por efectos del rival. Persistente, solo mientras dura el ataque. |
| 16-40 | **`<Link +X>`** | Suma X al límite máximo de cartas de link que puede tener este Digimon. Persistente, acumulable. |
| 16-41 | **`<Training>`** | Suspendiendo este Digimon, obtenés un beneficio (efecto de activación). Opcional. |
| 16-42 | **`<Use Req.>`** | Permite ignorar los requisitos de color al usar la carta especificada. Persistente. |
| 16-43 | **`<Ascension>`** | Al ser eliminada esta carta, se dispara un efecto (trigger, opcional). |
| 16-44 | **`<Engage>`** | Puede atacar al final de tu turno (trigger, opcional). |
| 16-45 | **`<Guard>`** | Cuando otro Digimon propio sería [algo específico], podés redirigirlo/protegerlo (inmediato, opcional). |
| 16-46 | **`<Detach>`** | Cuando este Digimon dejaría el campo, podés mandar al trash 1 de sus cartas de link especificadas para evitarlo (trigger, opcional). |
| 16-47 | **`<Succession>`** | Este Digimon gana todos los efectos [de la carta que especifique el texto]. Persistente. |

> Los keywords marcados con texto genérico ("según texto de la carta") tienen una mecánica base fija pero su condición exacta varía carta por carta — consultá siempre el texto impreso, que **siempre prevalece** sobre esta tabla resumen (RM 1-3-1).

---

## 18. Rule Checks (revisiones automáticas de reglas) *(RM 17)*

En ciertos momentos el juego revisa automáticamente el estado del campo y aplica, **todas a la vez**:

- **Se elimina** cualquier Digimon en área de batalla con 0 DP.
- **Se manda al trash**: Digimon sin DP en área de batalla; Options en área de batalla (salvo que un efecto las haya puesto ahí a propósito); cartas que no sean Digimon en el área de cría (salvo excepción similar); cartas boca abajo sueltas en el campo; cartas de link que excedan el límite permitido o que ya no cumplan los requisitos de link.

Los rule checks **no** se hacen en medio de procesar una regla o un efecto — recién después de que termine ese proceso.

---

## 19. Otra información *(RM 18)*

- **Pending processing:** procesamiento pendiente de una regla/efecto que se resuelve en su momento predeterminado, igual que un efecto gatillado (ej: "gana 3 memoria. Perdé 3 memoria al final del turno").
- **Overwrite processing:** cuando el texto dice "en cambio" (*instead*), reemplaza el procesamiento normal por el indicado. Puede ser obligatorio u opcional según el texto.
- **Bucles infinitos:** ver §16.6 arriba.

---

## 20. Preguntas frecuentes / cómo resolver situaciones comunes

**P: ¿Puedo bloquear el ataque que va dirigido a mi propio Digimon?**
R: No. El Digimon que ya es el objetivo del ataque no puede bloquear (RM 12-1-5). Solo podés redirigir el ataque usando OTRO Digimon con `<Blocker>`.

**P: Ataco con un Digimon `<Piercing>`, elimino al bloqueador en batalla. ¿Igual reviso seguridad?**
R: Sí. `<Piercing>` te da un chequeo de seguridad extra inmediatamente antes de que termine el ataque, aunque el ataque haya ido contra un Digimon y no contra el jugador directamente (RM 16-7).

**P: Tengo memoria en -2 de mi lado y juego una carta de costo 5. ¿Qué pasa?**
R: La memoria se mueve 5 espacios hacia el lado rival: pasa de -2 (tuyo) a +3 (rival). Como quedó en 1 o más del lado rival, en cuanto termines de resolver todo lo pendiente de la fase actual, tu turno **termina inmediatamente ahí** (RM 6-1-4).

**P: ¿Puedo digivolucionar un Digimon que está en el área de cría a una carta de nivel 3+?**
R: Sí, y automáticamente pasa a poder moverse al área de batalla en la siguiente breeding phase (o puede considerarse ya "de nivel 3+" para las reglas de la zona), pero mientras siga físicamente en el área de cría sigue sin poder atacar, bloquear ni activar sus efectos `[When Digivolving]` — esos no se gatillan estando en cría (RM 3-4-7-6).

**P: Digivolución normal vs DNA Digivolution: ¿la nueva carta hereda el estado de suspendido/sin-suspender?**
R: En digivolución **normal**, sí, hereda la orientación de la carta base (RM 8-1-2-3). En **DNA Digivolution**, NO: la carta resultante siempre entra sin suspender, sin importar el estado previo de las cartas combinadas (RM 8-2-2-1-1).

**P: Tengo dos efectos que se gatillan a la vez, uno mío y uno del rival (en mi turno). ¿Quién decide el orden?**
R: Vos (el jugador de turno) activás todos los tuyos primero, uno por uno, hasta agotarlos. Recién ahí el rival activa los suyos (RM 15-4-3-5).

**P: ¿DigiXros y Assembly se pueden combinar o usar junto con un efecto "on play" de la misma carta?**
R: Sí. Primero se resuelve cualquier efecto que se gatille al jugar la carta ("cuando esta carta sería jugada..."), y **recién después** se declara el DigiXros/Assembly, justo antes de pagar el costo (RM 7-2-2-2, 7-3-2-2).

**P: Si igualo el DP en una batalla, ¿quién gana?**
R: Nadie: **ambos** Digimon se eliminan a la vez (RM 14-2-1-3). Excepción: un Security Digimon nunca se elimina por perder una batalla, gane o empate (RM 14-2-3).

**P: ¿Un Security Digimon puede "morir" en la batalla contra el atacante?**
R: No. Los Security Digimon están exentos de la eliminación por batalla; solo se van al trash porque así lo dicta el procedimiento normal del chequeo de seguridad, no por perder la batalla (RM 14-2-3, RM 13-1-8-4).

**P: ¿Puedo declarar un segundo ataque en el mismo turno sin `<Blitz>`?**
R: No. Después de la primera declaración de ataque, no podés hacer una nueva declaración de ataque hasta que termine por completo el ataque en curso; sin `<Blitz>` (u otro efecto que lo permita explícitamente) solo se ataca una vez por turno por Digimon, y un Digimon ya usado para atacar queda suspendido (RM 11-2-4).

**P: Si el mazo se queda en 0 cartas, ¿pierdo automáticamente?**
R: No en el momento en que llega a 0, sino la próxima vez que te toque robar en tu draw phase y no puedas hacerlo — ahí perdés (RM 1-2-3-2).

**P: Se gatillan varios efectos `[Security]` y `[On Deletion]` al mismo tiempo por el mismo chequeo. ¿Cuál va primero?**
R: `[Security]` tiene prioridad de activación inmediata sobre cualquier otro efecto simultáneo, sin pasar por la cola de "pendiente de activación" (RM 15-16-10-2).

**P: ¿Cuántas veces por turno puedo usar un efecto "[X Per Turn]"?**
R: X veces por copia física de la carta (no por nombre de carta) — cada copia individual lleva su propia cuenta, y se resetea al cambiar el turno o si la carta se convierte en "carta nueva" (RM 15-14-1-3/5).

---

## 21. Reglas de torneo (resumen) — *Bandai Organized Play Tournament Rules Manual*

Documento completo archivado en `pdfs/Tournament_Rules_Manual_2024-06-06.pdf` (última actualización oficial: 06/06/2024). Puntos clave según la política pública de Bandai:

- Regula el formato de torneos oficiales (Swiss, single elimination, límites de tiempo por ronda, procedimientos de "deck check", conducta y penalizaciones).
- **Lista de cartas prohibidas y restringidas:** Bandai publica y actualiza periódicamente (última actualización pública: 16/03/2026) tres tipos de restricción de formato:
  - **Banned** (prohibidas): no pueden incluirse en el mazo.
  - **Restricted** (restringidas): se puede incluir hasta el número indicado (menor a las 4 copias normales).
  - **Banned Pairs:** ciertas combinaciones específicas de dos cartas no pueden estar ambas en el mismo mazo simultáneamente, aunque cada una sea legal por separado.
- La lista vigente se consulta en `world.digimoncard.com/rule/restriction_card/` (cambia con cada nuevo set relevante; no se reproduce aquí porque queda desactualizada de inmediato).

---

## 22. Historial de versiones del Comprehensive Rules Manual

Extraído del changelog incrustado al final del propio documento oficial. Es una lista de versiones con confianza alta (fechas y números de versión limpios); para el detalle exacto de **qué cambió** en cada cláusula, consultar la sección "Update History" al final de `pdfs/Comprehensive_Rules_v4.2_EN_2026-08-18.pdf`.

| Versión | Fecha (JP) | Nota |
|---|---|---|
| 1.0 | 2023/10/31 | Primera versión del Comprehensive Rules Manual |
| 1.1 | 2023/12/15 | |
| 2.0 | 2024/04/05 | Reescritura completa de todas las secciones |
| 2.1 | 2024/05/24 | |
| 2.2 | 2024/06/21 | |
| 2.3 | 2024/08/01 | |
| 2.4 | 2024/09/20 | |
| 2.5 | 2024/11/22 | |
| 2.6 | 2025/01/24 | |
| 3.0 | 2025/04/04 | |
| 3.1 | 2025/06/13 | |
| 3.2 | 2025/07/04 | |
| 3.3 | 2025/09/05 | |
| 3.4 | 2025/10/03 | |
| 3.5 | 2025/11/21 | |
| 3.6 | 2025/12/25 | |
| 3.7 | 2026/03/13 | |
| 4.0 | 2026/03/27 | |
| 4.1 | 2026/06/19 | |
| **4.2** | **2026/08/18** | **Versión vigente al momento de escribir este documento (21/08/2026)** |

*(Antes de octubre de 2023 el juego funcionaba solo con el "Official Rule Manual" ilustrado, sin un reglamento comprensivo separado — por eso no hay versiones anteriores a la 1.0.)*
