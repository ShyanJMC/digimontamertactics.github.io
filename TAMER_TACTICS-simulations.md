# Tamer Tactics — Historial de playtesting y razonamiento de diseño

Este documento es el complemento de `TAMER_TACTICS.md` (que contiene solo las reglas vigentes, sin comentario). Acá vive **todo el proceso**: qué se probó, qué situación (Z) llevó a decidir qué cambio de regla (X), y por qué. Sirve para no repetir discusiones ya cerradas y para entender el porqué de cada regla que hoy parece "rara" a primera vista.

Metodología: cada ronda se corrió como un conjunto de **simulaciones en paralelo vía subagentes independientes**, cada uno con una consigna puntual (armar mazos, jugar turnos, medir algo específico) sobre el estado del reglamento en ese momento. Los resultados se consolidaban, y las decisiones de qué aplicar las tomó el usuario en cada caso — este documento las registra en orden cronológico.

Van **6 rondas completas**, 42 simulaciones en total, llevando el formato de v0.1 a v0.9, más un **pase de revisión de reglas** (§7) hecho por el usuario que lo cerró en v0.9.0 y lo congeló para mesa real.

---

## Historial de versiones (resumen ejecutivo)

- **v0.1** — borrador inicial: gating de Tamer para jugar Digimon, grupos, alcance de efectos "tus Digimon" = grupo, 1 ataque a seguridad por grupo, ataques internos de grupo sin suspender al atacante.
- **v0.2** (ronda 1, §1 abajo): tope de memoria a partir del 2º Tamer, mínimo de Digi-Egg obligatorio, excepción de turno 1 para eliminar el "turno muerto", re-agrupamiento de huérfanos + válvula de seguridad ante 0 Tamers.
- **v0.3**: se elimina la excepción de "el atacante no se suspende" en peleas internas de grupo — el atacante vuelve a suspenderse como en las reglas oficiales.
- **v0.4**: se ignora el requisito de que el Digimon rival objetivo esté suspendido (RM 11-2-7-1) — cualquier Digimon rival es blanco válido. Objetivo: que evolucionar (subir DP) sea la defensa real.
- **v0.5** (ronda 2, §2 abajo): tope de 3 ataques contra Digimon rivales por turno, re-agrupamiento de huérfanos inmediato y sin límite, aclaración de que `<Progress>` no protege de ser blanco. Se descarta a propósito dar inmunidad a Digimon recién jugados.
- **v0.6** (ronda 3, §3 abajo): el tope de 3 queda absoluto; keywords de ataque extra (`<Blitz>`/`<Vortex>`/`<Execute>`/`<Engage>`) capadas a +1 en conjunto, también absoluto. Se reemplaza el "sin inmunidad" por protección de 1 carta por turno (jugadas/re-agrupamientos). Burst Digivolve también dispara huérfano/re-agrupamiento.
- **v0.7** (ronda 4, §4 abajo): la protección también cubre digivoluciones y remoción por efecto, con tope de 2 usos por línea evolutiva. Declaración en el momento exacto. El +1 de keyword siempre es aparte de los 3 normales.
- **v0.8** (ronda 5, §5 abajo): la protección cubre ser elegida **ni afectada** (incluye remoción "todos los que cumplan X"). Timing de digivolución fijado a después del `[When Digivolving]`. Ventana de gracia para olvidos.
- **v0.9** (ronda 6, §6 abajo): Link agregado como 4ta categoría elegible para la protección. "Efecto de remoción" aclarado en sentido amplio. Cierre explícito de la ventana de gracia ante cualquier otra acción.
- **v0.9.0** (pase de revisión de reglas, §7 abajo): cierre de huecos de interacción que las simulaciones nunca tocaron — entrada a grupo unificada (jugar y mover desde cría), `<Blocker>` global (no de grupo), invariante de Tamer (el último Tamer es inmune a remoción rival), materiales de digivolución/DNA intra-grupo, `[On Play]` de Tamers **reactivado**, un ataque cuenta aunque falle, ataques a Tamers solo vía efecto y dentro del cupo de 3(+1), carta protegida intocable absoluta, nuevo orden de preparación, banlist oficial de Bandai. **Ruleset congelado para llevar a mesa real** (ver `OPEN_ITEMS.md`).

---

## 1. Ronda 1 — playtesting v0.1 → v0.2

Se corrieron 4 simulaciones en paralelo (subagentes independientes) para estresar distintos ángulos del borrador v0.1. Resultados y qué se cambió en respuesta:

### 1.1 Stress test anti-swarm (mazo enjambre-de-Tamers vs. midrange)
El límite de "1 ataque a seguridad por grupo" **sí frena** el enjambre clásico (1 grupo, muchos cuerpos baratos) — pierde por completo su alfa-strike de turno 3-4. Pero encontró un agujero real: un mazo que arma **0 Digi-Egg** y dedica el 100% de sus breeding phases a meter Tamers consigue 2 grupos activos para el turno 4 y 3 para el turno 6, recreando 2-3 ataques de seguridad simultáneos casi tan rápido como en el juego base — solo corrido unos turnos. Además, como mover Tamers era gratis, toda la memoria del enjambre iba a cuerpos, acelerando su curva.
**Cambio aplicado:** mínimo de 2 Digi-Egg obligatorio + costo de 2 memoria por cada Tamer a partir del segundo movido a batalla.

### 1.2 Casos borde de Tamer eliminado
Los Tamers no pueden ser objetivo de batalla (no son Digimon) — solo mueren por efectos de remoción específicos, menos comunes que la remoción de Digimon. Aun así, perder un Tamer dejaba a su grupo sin poder atacar seguridad *para siempre*, y perder el *único* Tamer del board podía dejar a un jugador 2-5 turnos sin poder jugar ningún Digimon nuevo (softlock real).
**Cambio aplicado:** re-agrupamiento gratis (1/turno, main phase) + válvula de seguridad que garantiza un Tamer en la próxima eclosión si el jugador se queda en 0.

### 1.3 Partida completa "honesta" (medir ritmo)
Confirmó el objetivo de diseño: en el tramo tardío (turno 8-12) hubo 1-2 ataques de seguridad por turno en vez de los 4-6 simultáneos que un enjambre ancho podría lograr en reglas oficiales — reducción drástica y notoria, sin que la partida se sintiera estancada. Pero reveló un costo no buscado: el turno 1 completo quedaba muerto para ambos jugadores (nadie podía jugar ni un Digimon), porque el Tamer garantizado recién llegaba al área de batalla en el turno 2.
**Cambio aplicado:** excepción de turno 1 — el Tamer garantizado arranca ya colocado en el área de batalla.

### 1.4 Interacción con las 47 keywords oficiales
La mayoría de las keywords conviven bien con las reglas nuevas (Blocker, Alliance, Retaliation, Rush sin problemas reales). Pero encontró un hallazgo crítico: `<Blitz>`, `<Vortex>`, `<Execute>` y `<Engage>` — todas keywords que otorgan una declaración de ataque *extra*— podían saltear el tope de "1 duelo por turno" de Tamer Tactics, porque la regla base del juego (RM 1-3-1) dice que el texto de carta siempre gana sobre la regla general. Sin aclararlo, esto reintroducía "un solo cuerpo arrasa todo el board rival en un turno", el mismo problema que el formato buscaba evitar.
**Cambio aplicado en v0.2:** el tope de "1 duelo por Digimon por turno" se declaró **absoluto**, acumulando todas las fuentes de ataque combinadas, sin excepción de texto de carta.
**Superado en v0.3:** en vez de parchear la excepción de "no suspenderse", se eliminó la excepción en sí — pelear contra Digimon rivales vuelve a seguir 100% las reglas oficiales (el atacante se suspende como siempre), lo cual resuelve el problema de raíz sin necesitar ninguna regla especial de tope.

---

## 2. Ronda 2 — playtesting v0.4 → v0.5

Después de v0.4 (se ignora el requisito de que el objetivo esté suspendido), se corrieron **7 simulaciones en paralelo** para estresar la nueva regla desde distintos ángulos. Hallazgo transversal: como en este juego **defender nunca cuesta nada** (solo el atacante se suspende, no hay daño parcial, gana el DP más alto), quitarle al defensor la protección pasiva de "estar sin suspender" eliminó *toda* defensa pasiva, no solo la de "no evolucionar" — un board evolucionado podía limpiar varios Digimon rivales por turno sin arriesgar nada. A continuación, cada simulación y qué se hizo con su hallazgo:

### 2.1 `tt-v4-boardwipe` — riesgo de limpiar el board rival entero en un turno
Un board evolucionado (pocos Digimon, alto DP) podía elegir un objetivo distinto por cada uno de sus atacantes y eliminar la mayoría del board rival en un solo turno, sin pérdidas propias, porque nada limitaba cuántos Digimon rivales distintos podían recibir ataque.
**Cambio aplicado:** tope de **3 ataques contra Digimon rivales por turno, por jugador**.

### 2.2 `tt-v4-evo-incentive` — ¿evolucionar realmente es mejor que desplegar cuerpos?
Confirmado: un solo Digimon bien evolucionado es prácticamente invulnerable a un swarm sin evolucionar (el defensor nunca "gasta" nada al ganar una batalla). El objetivo de diseño se cumple, incluso más fuerte de lo esperado. **Sin cambio de regla** — es el comportamiento buscado.

### 2.3 `tt-v4-initiative` — ¿hay ventaja de "quién ataca primero"?
No hay snowball por iniciativa en mazos espejo (los intercambios se compensan turno a turno). El efecto real es que **cualquier** diferencia de DP, por chica que sea, ahora es explotable sin que el rival pueda cubrirse quedándose quieto — pero esto es consistente con el objetivo de v0.4. **Sin cambio de regla.**

### 2.4 `tt-v4-keywords` — cómo cambian de valor las keywords defensivas
`<Evade>` pasa de casi inútil a herramienta de primer nivel; `<Barrier>`, `<Decoy>`, `<Scapegoat>`, `<Guard>`, `<Blocker>` suben de valor por mayor frecuencia de combate. `<Progress>` **no** cambia — no protege de ser elegido como blanco, solo de efectos, y esto generaba confusión.
**Cambio aplicado:** aclaración explícita de que `<Progress>` no protege de ser atacado.

### 2.5 `tt-v4-security-neglect` — ¿se deja de atacar seguridad por priorizar pelear Digimon?
No — atacar seguridad se volvió casi automático porque ya no hay costo de exposición extra por usar un Digimon para eso (todo estaba expuesto igual). La partida se decidió por seguridad con normalidad. **Sin cambio de regla.**

### 2.6 `tt-v4-orphan-compound` — huérfanos combinados con exposición total
Sin protección pasiva, un rival podía eliminar 3+ Digimon huérfanos en 1-2 turnos, más rápido de lo que se podían re-agrupar al ritmo de 1 por turno (regla de v0.2) — un blowout notoriamente peor que antes de v0.4.
**Cambio aplicado:** re-agrupamiento **inmediato y sin límite de cantidad**, Digimon por Digimon, cada uno a un grupo propio distinto si se quiere.

### 2.7 `tt-v4-earlygame` — ¿el arranque de partida (turnos 2-6) se vuelve demasiado azaroso?
Hay 1 turno de gracia natural (un Digimon recién jugado no puede ser blanco el mismo turno porque nadie más tuvo turno de por medio todavía). Desde el turno 3 se vuelve una carrera de "quién sacó el DP más alto primero". El agente propuso dar inmunidad hasta el próximo turno propio.
**Decisión en v0.5:** **rechazada a propósito** — los Digimon recién jugados no reciben ninguna inmunidad especial, quedan expuestos igual que el resto desde el turno del rival. Se prioriza mantener la presión de v0.4 sobre suavizar el arranque.
**Revisitada en v0.6:** ver §3.2 — se termina agregando una protección acotada (1 sola carta por turno), no la inmunidad general que se había rechazado acá.

---

## 3. Ronda 3 — playtesting v0.5 → v0.6

Con el tope de 3 ataques ya en juego, se corrieron **7 simulaciones más en paralelo** para estresar los parches de v0.5 y confirmar que no quedaran huecos. Resultados y qué se cambió:

### 3.1 `tt-v5-cap3-effectiveness` — ¿el número 3 está bien calibrado?
Sí. Corta el board wipe casi total de v0.4 a "3 bajas por turno, con ventanas reales de reacción entre medio". Rara vez restringe a un board honesto. **Sin cambio de regla.**

### 3.2 `tt-v5-sniping` — remoción dirigida constante dentro del límite de 3
Con solo 1 de los 3 ataques disponibles, un jugador puede matar la pieza más cara del rival apenas la juega, cada turno, indefinidamente — nunca la deja sobrevivir para evolucionarla de nuevo. Asfixiante, no un intercambio sano.
**Cambio aplicado:** protección de **1 sola carta por turno**, a elección del jugador, entre lo que jugó/re-agrupó ese turno.

### 3.3 `tt-v5-group-economy` — ¿multi-grupo sigue siendo viable?
Confirmado que "rushear muchos grupos chicos" ya no es la jugada dominante temprana (el costo de memoria + oportunidad de breeding phase de v0.2 sigue funcionando), incluso ahora que el tope de ataque a Digimon es por jugador y no por grupo. **Sin cambio de regla.**

### 3.4 `tt-v5-orphan-retest` — ¿el re-agrupamiento instantáneo cierra el problema de huérfanos?
Corrección importante: el re-agrupamiento instantáneo (v0.5) solo protegía el *ataque a seguridad*, no la *exposición a ser atacado* — un Digimon recién re-agrupado seguía siendo blanco tan válido como cuando era huérfano, así que el blowout de `tt-v4-orphan-compound` seguía sin resolverse del todo. También se encontró que el documento no aclaraba si Burst Digivolve dispara el mismo mecanismo.
**Cambios aplicados:** la protección de 1 carta por turno (§3.2) también puede usarse en una carta recién re-agrupada, no solo recién jugada; y se aclaró que Burst Digivolve del Tamer sí dispara huérfano/re-agrupamiento.

### 3.5 `tt-v5-earlygame-retest` — ¿el tope de 3 suaviza el arranque?
No — en los turnos 2-6 nunca hay suficientes atacantes disponibles como para que el tope de 3 llegue a activarse; la volatilidad de arranque queda intacta. Confirma que sigue siendo un tema genuinamente abierto, no resuelto de rebote.
**Cambio aplicado:** indirectamente atendido por la protección de 1 carta por turno (§3.2), que ahora también se puede usar tempranamente si hace falta, aunque no es una solución dedicada al arranque.

### 3.6 `tt-v5-full-pacing` — partida completa con todo v0.5
Se jugó de punta a punta sin encontrar problemas — la tensión "más grupos vs. más evolución" funcionó bien como eje táctico central. **Sin cambio de regla.**

### 3.7 `tt-v5-keyword-cap` — ¿el nuevo tope de 3 tiene el mismo agujero que el viejo tope de "1 duelo"?
Sí, confirmado: `<Blitz>`, `<Vortex>`, `<Execute>` y `<Engage>` podían saltear el "máximo 3" porque el texto no lo declaraba absoluto ante texto de carta — mismo problema estructural que ya se había resuelto una vez para el tope anterior (§1.4).
**Cambio aplicado:** el tope de 3 ataques normales queda absoluto, y las keywords de ataque extra quedan limitadas en conjunto a **+1 ataque adicional por turno**, también absoluto.

---

## 4. Ronda 4 — playtesting v0.6 → v0.7

Con el techo de 4 ataques y la protección de 1 carta ya en juego, se corrieron **7 simulaciones más en paralelo** enfocadas en estresar específicamente los parches de v0.6. Resultados y qué se cambió:

### 4.1 `tt-v6-4cap-test` — ¿el techo real de 4 reabre el board wipe?
Contra boards grandes (7-8 Digimon) el techo de 4 es 25-33% más rápido que el tope de 3 solo, pero razonable. Contra boards **chicos/medianos (4-5 Digimon)** en turnos 5-7, 4 ataques puede vaciar casi todo el board rival en un solo turno — parecido al problema original de v0.4, acotado a ese tamaño de board.
**Decisión:** **sin cambio de regla por ahora** — se deja como algo a vigilar en la próxima mesa real, no a corregir en base a simulación.

### 4.2 `tt-v6-protection-adapt` — ¿el sniper se adapta a la carta no protegida?
Hallazgo grave: digivolucionar no es "jugar" (RM 7 vs RM 8), así que la protección de v0.6 nunca cubría el resultado de una digivolución — justo la pieza más valiosa en la mayoría de los turnos. El rival ignoraba la carta protegida (la más barata) y mataba la evolucionada de siempre, recreando el problema de `tt-v5-sniping` disfrazado.
**Cambio aplicado:** la protección ahora también puede elegirse sobre **el resultado de una digivolución hecha ese turno**.

### 4.3 `tt-v6-protection-edge` — casos borde de timing y alcance
Encontró que el momento de declaración no estaba definido, y que la protección solo cubría "ser blanco de ataque", dejando un hueco real contra remoción por efecto (sin pasar por batalla).
**Cambios aplicados:** declaración obligatoria en el momento exacto de jugar/evolucionar/re-agrupar (no después); la protección ahora cubre también remoción por efecto, no solo ataques.

### 4.4 `tt-v6-burst-chain` — ¿encadenar Burst Digivolve es un motor de valor roto?
No — cada uso adicional compone el mismo costo ya existente (menos Tamers/carriles de seguridad, mayor riesgo de punto único de falla si se consolida todo bajo 1 Tamer). **Sin cambio de regla.**

### 4.5 `tt-v6-keyword-stack` — ¿el pool compartido de +1 tiene ambigüedades?
`<Blitz>` nunca compite con los 3 normales (por diseño, siempre es un "segundo" ataque). Pero `<Vortex>`/`<Execute>`/`<Engage>` pueden ser el único ataque de esa carta en el turno, y el texto no aclaraba de qué pool salían.
**Cambio aplicado:** cualquier ataque de estas 4 keywords consume siempre el +1, nunca los 3 normales, sin excepción; el jugador elige libremente qué Digimon lo usa si hay varios candidatos.

### 4.6 `tt-v6-full-pacing` — partida completa con v0.6
Se jugó de punta a punta sin encontrar problemas nuevos — la protección funcionó bien en el único caso donde aplicaba (una pieza recién jugada, no evolucionada), aunque eso mismo confirmó el hallazgo de 4.2. **Sin cambio de regla adicional** más allá de lo ya aplicado en 4.2/4.3.

### 4.7 `tt-v6-protect-choice` — ¿elegir entre varias piezas nuevas en un mismo turno es sano?
Sí — es una decisión interesante, y el techo compartido de 4 ataques del rival (repartido entre todo el board, no solo las piezas nuevas) evita que "sin proteger" sea sinónimo de "muerte garantizada". **Sin cambio de regla**, y se descarta escalar la cantidad de cartas protegibles por turno.

---

## 5. Ronda 5 — playtesting v0.7 → v0.8

Con la protección ya cubriendo digivoluciones y remoción, se corrieron **7 simulaciones más en paralelo** para confirmar que los parches de v0.7 funcionaran de punta a punta y buscar huecos residuales. Fue la ronda con menos hallazgos accionables hasta ese momento — señal de que el formato estaba convergiendo. Resultados:

### 5.1 `tt-v7-sniping-retest` — ¿proteger digivoluciones cierra el sniping?
Sí, en gran parte: la remoción dirigida queda frenada en las primeras 1-2 evoluciones de una línea. Cuando se agota el tope de 2, el rival puede esperar y snipear en la 3ra — pero es el trade-off buscado a propósito, no un agujero nuevo. **Sin cambio de regla.**

### 5.2 `tt-v7-lineage-cap` — ¿el tope de 2 por línea genera una trampa al agotarse?
Contra ataques normales no (el DP acumulado ya protege). Contra remoción que ignora DP sí genera una vulnerabilidad permanente una vez agotado — se interpreta como tensión de matchup esperable, no un hueco de regla. **Sin cambio de regla.**

### 5.3 `tt-v7-removal-retest` — ¿la protección contra remoción por efecto tiene huecos?
Cierra por completo la remoción dirigida (individual). Pero la remoción de tipo "todos los que cumplan X" (sin elegir objetivo individual, RM 15-11-2) eludía la protección porque la carta nunca era "elegida" en sentido estricto.
**Cambio aplicado:** la protección ahora cubre ser **elegida NI afectada** por ataques o remoción, cerrando también el caso de remoción masiva.

### 5.4 `tt-v7-declaration-timing` — ¿la declaración inmediata es práctica en mesa?
Recomendó mantenerla estricta (preserva la tensión de decidir sin ver todo el turno), fijar que en digivolución el momento exacto es después de resolver `[When Digivolving]`, y dar una ventana de gracia acotada para olvidos reales de mesa.
**Cambios aplicados:** ambas precisiones sumadas al texto de la protección.

### 5.5 `tt-v7-protection-tax` — ¿protección + evolución crea un núcleo intocable?
No — la ventana de inmunidad real es de solo ~1 turno rival completo, y usarla temprano tiene costo de oportunidad real (no podés proteger otra cosa esos turnos). **Sin cambio de regla.**

### 5.6 `tt-v7-multilineage` — ¿desarrollar varias líneas rompe la escasez de 1-por-turno?
No — el cuello de botella real sigue siendo "1 declaración por turno", no el tope de 2 por línea; acumular protecciones en varias líneas es una estrategia de seguro legítima, pagada con menos DP concentrado, no un exploit. **Sin cambio de regla.**

### 5.7 `tt-v7-full-pacing` — partida completa con v0.7
La protección se usó 8 veces repartidas en los 3 tipos elegibles (jugada/evolución/re-agrupamiento), sin ninguna ambigüedad nueva encontrada en la práctica — confirmó que el parche de v0.7 funciona de punta a punta. **Sin cambio de regla**, recomendó pasar a mesa real.

---

## 6. Ronda 6 — playtesting v0.8 → v0.9

Con el formato ya bastante estable, se corrieron **7 simulaciones más en paralelo** enfocadas en verificar los parches recién aplicados y cubrir ángulos nuevos (Blocker, DigiXros/Assembly, Link real, diversidad de arquetipos). Fue la ronda más limpia hasta ahora — 6 de 7 confirmaron que todo funciona bien. Resultados:

### 6.1 `tt-v8-grace-window-abuse` — ¿la ventana de gracia permite decidir con info de más?
No — jugar una segunda carta sin declarar protección en la primera ya cierra la ventana de esa primera, así que nunca hay más de 1 candidato "abierto" a la vez para comparar. **Sin cambio de regla**, aunque se dejó explícito por las dudas (ver 6.7 más abajo).

### 6.2 `tt-v8-overall-removal-retest` — ¿el fix de remoción masiva de v0.8 funciona?
Confirmado: cierra el hueco original y también la cadena "-DP hasta 0 para forzar rule check". Sugirió aclarar que "efecto de remoción" se interpreta en sentido amplio (no solo eliminación/trash).
**Cambio aplicado:** aclaración de alcance amplio agregada al texto de la protección.

### 6.3 `tt-v8-blocker-viability` — ¿Blocker sigue siendo viable frente a la protección?
Sí, es complementario, no redundante — pero un mazo Blocker-only sin DP propio pierde por desgaste ante decks evolucionados. Insight de deckbuilding, no de regla. **Sin cambio de regla.**

### 6.4 `tt-v8-digixros-protection` — interacción de DigiXros/Assembly con la protección
Ninguna de las 3 combinaciones revisadas (carta protegida usada como material, carta jugada con DigiXros, Assembly desde trash) generó hueco ni exploit. **Sin cambio de regla.**

### 6.5 `tt-v8-link-group` — Link real (RM 10) + sistema de grupos
El alcance de efectos de link dentro de un grupo funciona sin ambigüedad. Pero encontró que hacer Link no estaba en la lista de elegibilidad de la protección — mismo patrón que el hueco ya cerrado entre "jugar" y "digivolucionar" (ronda 4).
**Cambio aplicado:** Link agregado como 4ta categoría elegible para la protección.

### 6.6 `tt-v8-archetype-diversity` — ¿algún arquetipo domina?
No — probó Agresivo ancho, Control evolucionado y Multi-grupo cruzados entre sí y encontró un triángulo de counters sano (control contiene al agresivo, multi-grupo presiona al control, agresivo gana al multi-grupo en partidas cortas). **Sin cambio de regla** — buena señal de metagame.

### 6.7 `tt-v8-full-pacing-final` — partida completa final con v0.8
Consistente con partidas de referencia anteriores (11 turnos). Notó que ni la ventana de gracia ni el tope de 2 por línea se ejercitaron en esa partida puntual — sugirió prestarles atención en la primera mesa real por ser los mecanismos más nuevos, sin indicio de falla. **Sin cambio de regla** más allá de las aclaraciones ya aplicadas.

**Cambio aplicado (a partir del hallazgo 6.1, confirmado por el usuario):** se dejó explícito en v0.9 que iniciar cualquier otra acción de main phase cierra automáticamente la ventana de gracia de la acción anterior sin proteger.

---

## 7. Pase de revisión de reglas — v0.9 → v0.9.0

**No es una ronda de playtesting.** Es un pase de revisión que hizo el usuario sobre el texto de v0.9, a partir de un análisis de huecos, cerrando interacciones que las 42 simulaciones nunca habían tocado (casi todas alrededor de dos puntos ciegos: el sistema de grupos, y las vías por las que un Digimon/Tamer entra al campo sin "jugarse"). Cada decisión y su porqué:

1. **Entrada a grupo unificada.** Un Digimon movido del área de cría a batalla también declara grupo-Tamer, igual que uno jugado desde el mazo principal (antes solo estaba definido para "jugar"). Cierra el hueco de los Digimon de línea Digi-Egg —obligatorios en el formato— que quedaban sin grupo asignado.
2. **`<Blocker>` global, no de grupo.** Redirige el ataque a sí mismo; su texto no dice "tus Digimon", así que puede interceptar ataques dirigidos a cualquier grupo. `<Decoy>`/`<Guard>`/`<Scapegoat>`/`<Save>` sí quedan acotados al grupo (su texto sí refiere a "otro Digimon propio"). Asimetría aceptada a propósito.
3. **Invariante de Tamer.** El último Tamer en el área de batalla **no puede ser elegido ni afectado por remoción rival** (se eligió esta opción de "mini-protección permanente" sobre las alternativas de "eclosión de reemplazo instantánea" o mixta). Da un piso estructural duro: los Tamers son una capa estratégica de cálculo, no un punto único de falla explotable. Quedarse en 0 sigue siendo posible solo voluntariamente (Burst Digivolve), con la válvula de seguridad ya existente.
4. **Digimon jugados por efecto** (trash, seguridad, deck, token) entran a un grupo con Tamer, **a elección de quien controla el efecto**.
5. **Materiales de digivolución y DNA: mismo grupo.** Cada grupo es un board separado. Elimina la ambigüedad de DNA cruzando grupos (queda prohibido) y de digivolucionar sobre una base de otro grupo.
6. **`<Piercing>` / `<Security A.>` / `<Recovery>`: sin cambios.** El límite de 1 ataque a seguridad por grupo ya contiene lo que haga falta; no se les agrega restricción de formato.
7. **Un ataque cuenta aunque falle.** El cupo de 3(+1) cuenta declaraciones de ataque, exitosas o no (bloqueadas, frustradas en counter, atacante muerto antes de resolver).
8. **Ataques a Tamers.** Solo posibles vía efecto de carta específico (regla base RM 11-2-7-1 sin cambios); cuando ocurren, cuentan dentro del cupo de 3(+1); nunca pueden apuntar al último Tamer del rival (punto 3).
9. **Carta protegida = intocable absoluto** mientras dure la protección — nada del rival la afecta, sin interpretación caso por caso.
10. **`[On Play]` de Tamers: reactivado.** Se dispara cuando el Tamer entra al área de batalla (mover de cría→batalla, o colocarse en la preparación). A falta de Tamers diseñados para el formato, se reusa el texto impreso para ambos casos. **Deroga** la regla de v0.1–v0.9 de que el `[On Play]` de un Tamer quedaba muerto. Razón: sin esto, una porción grande del pool de Tamers quedaba inservible y el criterio de armado de la pila se volvía artificialmente estrecho. También resuelve el "caso abierto" #2 de v0.9. *Riesgo a vigilar en mesa: reintroduce parte del swing podado — ver `OPEN_ITEMS.md` §3.*
11. **Un Tamer no puede digivolucionar a un Digimon** (dejaría al grupo huérfano). Las cartas Tamer con cara de digivolución a Digimon funcionan solo como Tamer. Revisable más adelante.
12. **Nuevo orden de preparación** (`TAMER_TACTICS.md` §2.0): piedra-papel-tijera → barajar ambos mazos → cada jugador busca y coloca su Tamer inicial en batalla → resolver sus `[On Play]` (primero el jugador inicial, con el mazo ya barajado pero antes de la mano inicial) → robar 5 + mulligan → seguridad → memoria a 0 → turno 1.
13. **Legalidad:** lista oficial de Bandai (Banned/Restricted/Banned Pairs) para torneos sancionados. Sin banlist propia del formato.

A partir de acá el ruleset queda **congelado en v0.9.0**. La próxima iteración se hace con datos de partidas reales, no de simulación — la lista de qué medir está en `OPEN_ITEMS.md`.
