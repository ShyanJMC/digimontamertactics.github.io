# Formato "Tamer Tactics" — v0.9.1

Reglas completas y vigentes del formato. Para el historial de versiones, las simulaciones que motivaron cada decisión y el razonamiento detrás de cada cambio, ver `TAMER_TACTICS-simulations.md`. Para lo que todavía falta validar y los números que quedaron sujetos a datos de mesa real, ver `OPEN_ITEMS.md`.

Formato casero (no oficial de Bandai) construido **sobre** las reglas del Digimon Card Game 2020+ documentadas en `2020-edition/RULES.md`. Todo lo que no se modifique explícitamente acá sigue funcionando como en el reglamento oficial (`2020-edition/pdfs/Comprehensive_Rules_v4.2_*.pdf`).

**Estado:** v0.9.1 es la versión **congelada** para llevar a mesa real. Ningún número (tamaño de la pila Tamer, costo de memoria, cupos de ataque, tope de protección) se retoca hasta tener partidas con jugadores reales; los parches sobre v0.9.0 solo cierran huecos de reglas, no recalibran.

**Parches sobre v0.9.0:**
- **v0.9.1** — los Tamers de la pila Tamer+Digi-Egg deben ser **todos distintos** (1 copia por Tamer, sin repetir).

## 0. Objetivo de diseño

El juego base permite ganar atacando la pila de seguridad (solo 5 cartas) con **cualquier cantidad de Digimon baratos**, sin necesidad real de desarrollar el board ni evolucionar. Esto puede volver el juego repetitivo (mazos de "enjambre" de bajo costo). `Tamer Tactics` ataca ese problema **sin prohibir cartas**: cambia el límite de "1 ataque a seguridad" de *por Digimon* a *por grupo liderado por un Tamer*, y hace que formar un grupo nuevo sea un recurso escaso y lento de conseguir. Como defensa, ya no alcanza con "no hacer nada" — la única protección real es tener suficiente DP (evolucionar) o gastar recursos puntuales de protección.

---

## 1. Construcción de mazo

| Zona | Regla |
|---|---|
| **Mazo principal** | 50 cartas exactas. Solo Digimon y Option (**los Tamers NO van acá** — ver zona siguiente). Límite estándar de 4 copias por número de carta. |
| **Mazo Tamer + Digi-Egg** (nueva zona, reemplaza al Digi-Egg deck normal) | Entre **4 y 7 Tamers**, más **2 a 5 Digi-Egg**. Mezclados en un mismo mazo. Tamaño total variable (mínimo 6, máximo 12 cartas). **Cada Tamer debe ser un número de carta distinto — 1 sola copia por Tamer, sin repetir** (v0.9.1). Los Digi-Egg mantienen el límite estándar de hasta 4 copias por número de carta. |
| **Legalidad** | Se aplica la lista oficial de Bandai de **Banned / Restricted / Banned Pairs** vigente para torneos sancionados (ver `2020-edition/DECKBUILDING.md` §A.4 y `world.digimoncard.com/rule/restriction_card/`). **El formato no agrega prohibiciones propias** — ese es el punto (§0). |
| **Preparación** | Ver §2.0. |

---

## 2. Tamers, Digimon y arranque de partida

### 2.0 Preparación de la partida (reemplaza el arranque de `RULES.md` §5–6)

Orden exacto:

1. **Piedra-papel-tijera** decide quién será el primer jugador.
2. Cada jugador **baraja su mazo principal** (50) y su **pila Tamer+Digi-Egg** por separado.
3. Cada jugador **busca 1 Tamer** en su pila Tamer+Digi-Egg, lo coloca **directamente en su área de batalla** (no pasa por el área de cría), y **baraja el resto** de esa pila.
4. Empezando por el primer jugador, cada uno **resuelve el efecto `[On Play]`** de su Tamer inicial (ver §2.3). Se resuelve acá, en la preparación, con el mazo ya barajado pero antes de robar la mano inicial.
5. Ambos roban 5 cartas. **Mulligan** opcional, una vez, empezando por el primer jugador (RM 5-2-1-4/5).
6. Se colocan las 5 cartas superiores de cada mazo como pila de seguridad, boca abajo (RM 5-2-1-6).
7. Marcador de memoria a 0.
8. Empieza el turno 1 del primer jugador (que **no roba** en su primer turno, regla base).

**Consecuencia:** desde el turno 1 ya hay exactamente 1 Tamer en batalla por lado, con su `[On Play]` ya resuelto, y se pueden jugar Digimon del mazo principal de entrada — no hay "turno muerto".

### 2.1 Invariante de Tamer

**En todo momento cada jugador tiene al menos 1 Tamer en su área de batalla.** Es el piso estructural del formato (de ahí el Tamer garantizado en la preparación). En la práctica:

- **El último Tamer en el área de batalla de un jugador no puede ser elegido ni afectado por ningún efecto de remoción del rival** — eliminación, devolver a mano, poner boca abajo, mover, reducir a datos, etc., en el mismo sentido amplio que la protección de §4. Si un efecto del rival afectaría a varios Tamers propios a la vez y dejaría al jugador en 0, ese jugador **elige 1 de sus Tamers que queda sin afectar**.
- El jugador **sí puede** quedarse voluntariamente sin Tamers en batalla pagando el costo de un **Burst Digivolve** (RM 8-3: devolver 1 Tamer propio a la mano; en este formato ese Tamer queda fuera de la partida para siempre, §2.5). Si eso lo deja en 0 Tamers en batalla **y** sin Tamers en el área de cría, se aplica la **válvula de seguridad**: su próxima eclosión de la pila Tamer+Digi-Egg no es al azar — busca y eclosiona un Tamer, barajando el resto después.

### 2.2 Cómo entran los Tamers al campo

- El **Tamer inicial** entra en la preparación (§2.0), directo al área de batalla.
- **Del segundo Tamer en adelante:** se eclosionan desde la pila Tamer+Digi-Egg al área de cría (igual que un Digi-Egg) y se mueven al área de batalla en una breeding phase posterior. Sigue siendo **1 sola acción de cría por turno** (eclosionar, O mover, O nada — regla base sin cambios).
- **Costo de memoria:** mover el **primer** Tamer de cría a batalla es gratis. **A partir del segundo Tamer en batalla**, mover uno nuevo de cría a batalla cuesta **2 de memoria** (se paga como cualquier costo, mueve el marcador hacia el lado del rival).
- Un Tamer **no puede digivolucionar a un Digimon** en este formato (dejaría al grupo huérfano). Las cartas Tamer que traen una cara o efecto de digivolución a Digimon funcionan **solo como Tamer** — esa mitad queda inactiva acá. *(Revisable más adelante — ver `OPEN_ITEMS.md`.)*
- **No se puede jugar ningún Digimon del mazo principal hasta que haya al menos 1 Tamer en el área de batalla** (siempre se cumple desde el turno 1 por §2.0/§2.1).
- Los Digi-Eggs de esta pila funcionan exactamente igual que en las reglas oficiales (eclosionan, digivolucionan en cría o se mueven a batalla al llegar a nivel 3+).

### 2.3 Efectos `[On Play]` de los Tamers — SÍ se activan

A diferencia de versiones anteriores del formato, en v0.9.0 **el `[On Play]` de un Tamer sí se dispara**, en el momento en que el Tamer **entra al área de batalla**:

- al **moverse** del área de cría al área de batalla (no al eclosionar — en cría todavía no está "en juego", RM 3-4-7);
- o al **colocarse durante la preparación** (§2.0, paso 4).

A falta de Tamers diseñados específicamente para este formato, se reusa el texto `[On Play]` impreso para ambos casos. Sus efectos persistentes, `[Your Turn]`/`[All Turns]` y de activación `[Main]` funcionan con normalidad, como siempre.

> Al armar la pila Tamer+Digi-Egg, evaluá cada Tamer por su cuerpo/DP, sus pasivas **y su `[On Play]`** — todo cuenta ahora. Y como **no se puede repetir Tamer** (v0.9.1), cada lugar de la pila es una elección única: buscá 4-7 Tamers que se complementen, no 4 copias del mismo.

### 2.4 Formación de grupos

- Al **jugar cualquier Digimon desde el mazo principal**, o al **mover un Digimon del área de cría al área de batalla**, el jugador declara obligatoriamente **a qué Tamer propio en el área de batalla se une** — eso forma (o se suma a) el **grupo** de ese Tamer.
- Un Tamer puede tener cualquier cantidad de Digimon en su grupo, **incluido 0**: un grupo vacío es válido (no tiene atacantes ni hace ataque a seguridad ese turno, pero sigue contando como "un Tamer en batalla" para §2.1).
- Cuando un **efecto** juega un Digimon (desde trash, seguridad, deck, o un token), ese Digimon entra en **un grupo con Tamer, a elección del jugador que controla el efecto**.
- **Convención de mesa:** agrupá físicamente las cartas de cada grupo cerca de su Tamer. Si el board se llena, usá una ficha/dado de color distinto por grupo. (Esto no es el keyword `Link` oficial, que es carta→Digimon, no Tamer→Digimon.)
- **Digimon "huérfano"** (su Tamer fue eliminado, o devuelto por Burst Digivolve): queda en el campo sin grupo. Mientras esté huérfano puede seguir peleando contra Digimon rivales (§4) pero **no puede atacar la seguridad**.
  - **Re-agrupamiento inmediato:** apenas queda huérfano, se re-agrupa **de inmediato**, sin esperar ninguna fase, **Digimon por Digimon**, a elección del jugador, a cualquier otro grupo propio (otro Tamer propio ya en el área de batalla). Sin límite de cantidad ni costo. Solo queda huérfano de verdad (sin poder atacar seguridad) si en ese momento no le queda ningún otro grupo propio.
  - Por §2.1 un jugador nunca pierde su **último** Tamer por remoción rival, así que un huérfano por remoción solo puede ocurrir en grupos que no son el último. El estado de 0 Tamers solo se alcanza por Burst Digivolve voluntario (§2.1, §2.5).

### 2.5 Burst Digivolve y Tamers

Cuando un Tamer sale del área de batalla como parte del costo de un Burst Digivolve (RM 8-3), sus Digimon quedan huérfanos igual que si el Tamer hubiera sido eliminado, y se re-agrupan de inmediato con la regla de §2.4. Como en este formato los Tamers no se juegan desde la mano, ese Tamer devuelto **queda fuera de la partida para siempre** — es un costo real, no una forma gratuita de reorganizar grupos. Si el jugador queda en 0 Tamers, la válvula de seguridad de §2.1 le garantiza un Tamer en la próxima eclosión.

---

## 3. Alcance de los efectos ("tus Digimon" = "los de tu grupo")

- Cualquier efecto propio que diga *"tus Digimon"*, *"1 de tus Digimon"*, etc. (activado por un Digimon, un Tamer, o una Option) **solo puede elegir/afectar Digimon del mismo grupo** que la fuente del efecto.
- Los efectos que apuntan a Digimon **rivales** ("1 Digimon de tu oponente") no tienen esta restricción — pueden elegir cualquier Digimon rival, sin importar en qué grupo rival esté.
- Los efectos de área ("todos tus Digimon get +X DP") también quedan acotados al grupo de la fuente, no a todo tu board.
- Los efectos de una carta de Link se tratan como efectos propios del Digimon anfitrión (RM 4-3-5) — un "tus Digimon" en un efecto de link se acota al grupo igual que cualquier otro.
- **Digivolución y DNA Digivolution:** los materiales **deben pertenecer todos al mismo grupo**. Cada grupo es un board independiente — no se puede digivolucionar usando como base un Digimon de otro grupo, ni combinar en DNA Digimon de dos grupos distintos.
- **`<Blocker>` es la excepción al alcance de grupo:** no es un efecto "de grupo". Redirige el ataque **a sí mismo** (RM 12), así que **cualquier `<Blocker>` propio puede interceptar cualquier ataque** —a seguridad o a un Digimon— sin importar a qué grupo iba dirigido.
- En cambio `<Decoy>`, `<Guard>`, `<Scapegoat>`, `<Save>` y similares **sí** están acotados al grupo, porque su texto refiere a "otro Digimon propio" (regla de arriba).

---

## 4. Ataques

| Tipo de ataque | Objetivo válido | Límite | Suspende al atacante |
|---|---|---|---|
| **Ataque a la pila de seguridad del rival** | El jugador rival | **1 por grupo, por turno** (sin importar cuántos Digimon tenga el grupo) | Sí, regla oficial sin cambios. |
| **Ataque contra un Digimon rival** | **Cualquier Digimon rival, esté suspendido o sin suspender** — se ignora el requisito de suspensión del objetivo de RM 11-2-7-1, salvo la carta protegida del turno (ver más abajo) | Ver "Cupo de ataques" abajo | **Sí, regla oficial sin cambios.** |
| **Ataque contra un Tamer rival** | Solo posible si un **efecto de carta específico lo habilita** — la regla base RM 11-2-7-1 sigue vigente: un Tamer no es objetivo de batalla por sí solo. **Nunca** puede apuntar al último Tamer del rival (§2.1). | Cuenta **dentro** del cupo de ataques de abajo. | Sí. |

**Cupo de ataques que no van a seguridad (contra Digimon o Tamer rival):**

- **Máximo 3 por turno, por jugador, absoluto.** Cuenta la **declaración de ataque**, tenga éxito o no — un ataque frustrado en counter timing, bloqueado, o cuyo atacante muere antes de resolver, igual consumió 1. Ningún texto de carta lo puede exceder.
- **Aparte de esos 3**, las keywords que otorgan una declaración de ataque extra (`<Blitz>`, `<Vortex>`, `<Execute>`, `<Engage>` o similares) solo pueden sumar, **en conjunto, +1 ataque adicional por turno — también absoluto**, sin importar cuántas copias o cuántas de estas keywords tenga disponibles el jugador.
- **Techo real: 4 ataques por turno que no van a seguridad, por jugador.**

Un jugador con varios Tamers en juego tiene varios "ataques a seguridad" disponibles por turno (uno por grupo) — pero conseguir cada Tamer nuevo es lento y cuesta memoria a partir del segundo (§2.2), así que multiplicar grupos no es una salida gratis al límite.

Pelear contra Digimon (o Tamers habilitados) rivales, en cambio, ya no depende de que el rival haya "actuado" ese turno: **todo el board rival es blanco válido en todo momento**, salvo la única carta protegida del turno. Esto sube mucho el valor de invertir en DP (evolucionar) y baja el valor de simplemente desplegar cuerpos y no hacer nada con ellos. El techo de 3+1 por turno evita que esto se traduzca en limpiar el board rival entero y gratis en una sola pasada.

### Protección de 1 carta por turno

- Cada turno, el jugador puede declarar **una sola carta propia** como protegida, elegida entre: una carta recién jugada del mazo principal, una carta recién re-agrupada (§2.4), el resultado de una digivolución hecha ese turno, o un Digimon que acaba de recibir una carta de Link ese turno (RM 10).
- **Momento de declaración:** se declara **en el momento exacto** de jugar la carta, re-agrupar la carta, hacer el link, o —en el caso de una digivolución— **inmediatamente después de resolver su efecto `[When Digivolving]`** si lo tiene (en línea con RM 8-1-3-3). **Ventana de gracia:** si el jugador se olvida de declararla en el momento correspondiente, todavía puede hacerlo más tarde ese mismo turno, siempre que no haya iniciado ya su siguiente acción de main phase (jugar otra carta, digivolucionar otra cosa, hacer otro link, atacar, declarar protección sobre otra carta, etc.) — **cualquiera de esas acciones cierra automáticamente y para siempre esa ventana de gracia ese turno.**
- **Duración y alcance:** dura hasta el inicio del próximo turno de su dueño (sobrevive un turno completo del rival). Mientras dura, **nada del rival la afecta**: no puede ser elegida ni afectada por ningún ataque ni por ningún efecto del rival — eliminación, devolver a mano, poner boca abajo, reducir DP, restringir su capacidad de atacar/bloquear, de-digivolución, remoción masiva del tipo "todos los que cumplan X", redirección forzada de objetivo (`<Raid>`, `<Collision>`), lo que sea. Es **absoluto** mientras dure.
- **Tope por línea evolutiva:** una misma línea evolutiva (el mismo Digimon en el campo, apilando digivoluciones sobre sí — RM 4-7) puede recibir esta protección **como máximo 2 veces en toda la partida**. Llevá la cuenta con una ficha o anotación junto a la carta. Una **DNA Digivolution** cuenta como línea evolutiva nueva (RM 8-2-2-1-2), así que arranca con su propio tope de 2 desde cero.
- Solo se puede proteger 1 carta por turno en total, sin importar cuántas cartas nuevas/evolucionadas/linkeadas/re-agrupadas haya ese turno — es una elección estratégica única.

### Otras aclaraciones de ataque

- `<Blocker>` funciona sin cambios y **no está acotado a su grupo** (ver §3): sigue siendo formalmente un "ataque" (RM 11) y puede redirigir a sí mismo tanto un ataque a seguridad como un ataque contra otro Digimon, de cualquier grupo.
- **El +1 de keyword es siempre aparte de los 3 normales:** cualquier ataque originado por `<Blitz>`, `<Vortex>`, `<Execute>`, `<Engage>` (o keyword similar) **siempre** consume el único +1 disponible por turno — nunca cuenta como uno de los 3 ataques normales, ni siquiera si el jugador todavía no usó los 3. Si hay varios Digimon elegibles para ese único golpe extra, el jugador elige libremente cuál lo usa.
- `<Progress>` ("mientras ataca, no es afectado por los efectos de tu oponente") y cualquier efecto de tipo "no afectado por efectos" **no protegen de ser elegido como objetivo de un ataque ni de participar en la batalla resultante** — ser atacado y perder una batalla por comparación de DP es un procedimiento de regla (RM 11, RM 14), no un efecto de carta. Solo bloquean modificadores como -DP o restricciones de acción aplicadas por efectos.
- `<Piercing>`, `<Security A. ±X>` y `<Recovery>` **mantienen su regla base sin cambios** en este formato.

Todo lo demás del procedimiento de ataque (counter timing, block timing, chequeo de seguridad, batallas por DP) sigue **sin cambios** respecto a `RULES.md` §12–15.

---

## 5. (reservado)

*Los "casos abiertos" que antes vivían acá se movieron a `OPEN_ITEMS.md` junto con lo demás que falta validar en mesa real.*

---

## 6. Qué falta validar

Ver **`OPEN_ITEMS.md`**: el gap de fondo (no hay partidas reales), los números sujetos a datos de mesa, los riesgos de arquetipo a vigilar, el pool de cartas, y la falta de decklists de referencia.

---

## 7. Registro de reglas especiales (referencia rápida)

| Pregunta | Resolución |
|---|---|
| ¿El atacante se suspende al pelear contra un Digimon rival? | Sí, regla oficial sin cambios. |
| ¿El Digimon rival objetivo necesita estar suspendido? | No — cualquier Digimon rival es blanco válido, suspendido o no. |
| ¿Se puede atacar a un Tamer rival? | Solo si un efecto de carta específico lo habilita (regla base RM 11-2-7-1 sin cambios). Cuando ocurre, cuenta dentro del cupo de 3(+1). Nunca puede apuntar al último Tamer del rival. |
| ¿Cuántos ataques que NO van a seguridad puede hacer un jugador por turno? | 3 normales (absoluto, cuenta la declaración tenga éxito o no) + máximo 1 adicional entre todas las keywords tipo Blitz/Vortex/Execute/Engage (absoluto) = techo real de 4. Independiente del límite de seguridad por grupo. |
| ¿Un Tamer que entra al área de batalla dispara su `[On Play]`? | **Sí** — al moverse de cría a batalla, o al colocarse en la preparación. Reactivado en v0.9.0. |
| ¿Un Tamer puede digivolucionar a un Digimon? | No en este formato (dejaría al grupo huérfano). Las cartas Tamer con cara de digivolución a Digimon funcionan solo como Tamer. |
| ¿Tamaño y composición de la pila Tamer+Digi-Egg? | 4-7 Tamers + 2-5 Digi-Egg, total 6-12. Los **Tamers, todos distintos** (1 copia cada uno, v0.9.1); los Digi-Egg, hasta 4 copias por número de carta. |
| ¿Cuesta memoria mover un Tamer a batalla? | El primero no. Del segundo en adelante, 2 de memoria. |
| ¿Se puede perder el último Tamer? | No por remoción rival — el último Tamer en batalla no puede ser elegido ni afectado por efectos del rival (§2.1). Sí voluntariamente por Burst Digivolve, y ahí aplica la válvula de seguridad. |
| ¿A qué grupo va un Digimon movido desde cría, o jugado por un efecto? | Movido desde cría: lo declara el jugador al moverlo, igual que al jugarlo. Jugado por un efecto: a un grupo con Tamer, a elección de quien controla el efecto. |
| ¿Con qué materiales se digivoluciona / hace DNA? | Solo con materiales del mismo grupo. Cada grupo es un board separado (DNA cruzando grupos: prohibido). |
| ¿Qué pasa con un Digimon huérfano? | Se re-agrupa de inmediato, sin límite de cantidad, cada Digimon elige a qué otro grupo propio se une. Huérfano total (sin atacar seguridad) solo si no queda ningún otro grupo. |
| ¿Un Tamer que sale de batalla por Burst Digivolve genera huérfanos? | Sí. Mismo mecanismo que la eliminación por efecto rival — con el costo de que ese Tamer queda fuera de la partida para siempre. |
| ¿`<Blocker>` está acotado a su grupo? | No — redirige el ataque a sí mismo y puede interceptar cualquier ataque de cualquier grupo. `<Decoy>`/`<Guard>`/`<Scapegoat>`/`<Save>` sí están acotados al grupo. |
| ¿Los Digimon recién jugados/evolucionados/linkeados/re-agrupados tienen alguna inmunidad especial? | Solo 1 por turno, a elección, entre esas 4 categorías. Mientras dura, nada del rival la afecta (absoluto). Se declara en el momento exacto (en digivolución, después del `[When Digivolving]`), con ventana de gracia hasta la siguiente acción de main phase. Tope de 2 usos por línea evolutiva; DNA arranca un tope nuevo. |
| ¿`<Progress>` protege de ser elegido como objetivo de ataque? | No. Solo bloquea modificadores de efecto, no el procedimiento de ataque/batalla en sí. |
| ¿`<Piercing>` / `<Security A.>` / `<Recovery>` cambian en este formato? | No, mantienen su regla base. |
| ¿El +1 de Blitz/Vortex/Execute/Engage puede salir del cupo de los 3 normales si sobra cupo? | No, nunca. Siempre es el +1 aparte, sin excepción. |
| ¿Cuántas veces puede protegerse la misma línea evolutiva en toda la partida? | Máximo 2. DNA Digivolution arranca un tope de 2 nuevo. |
| ¿Aplica una banlist? | La lista oficial de Bandai (Banned/Restricted/Banned Pairs) para torneos sancionados. El formato no agrega prohibiciones propias. |
