# Tamer Tactics — Ítems abiertos para mesa real

`TAMER_TACTICS.md` v0.9.0 está **congelada**. Nada de este archivo se toca hasta tener datos de partidas con jugadores reales. Esto es la lista de lo que hay que medir o decidir **con** esos datos.

---

## 1. El gap de fondo: no hay ni una partida real

Las 6 rondas / 42 simulaciones de `TAMER_TACTICS-simulations.md` las corrieron subagentes LLM, no jugadores. Sirven para encontrar huecos de reglas evidentes; **no** para calibrar balance. Todo lo que en ese documento dice "sin cambio de regla, funciona bien" está apoyado en una sola corrida de un agente.

Antes de una v1.0:

- **30–50 partidas mínimo** con humanos, con decklists del meta real (era BT-22/23/24).
- **Registrar por partida:** turno de cierre, largo en turnos, quién empezó y quién ganó, cantidad de grupos de cada jugador por turno, ataques a seguridad y ataques a Digimon por turno.
- Comparar la **distribución de turno de cierre** contra el juego base: ¿el formato alarga las partidas o solo retrasa el swarm ~3 turnos?

---

## 2. Números a instrumentar (no cambiar a ciegas)

| Número | Valor v0.9.0 | Qué medir / alternativas si falla |
|---|---|---|
| **Winrate de primer jugador** | — | Objetivo 50–55%. Ahora P1 arranca con el `[On Play]` de su Tamer ya resuelto y sin robar en el turno 1 — hay que ver si eso compensa o se pasa de fuerte. Es el número #1 a medir. |
| **Ratio Tamers:Digi-Egg** | rango 4–7 : 2–5 | Curva "grupos online por turno" según lo que elija cada jugador (7/2 vs 4/5 dan curvas muy distintas). Si un extremo del rango domina, angostar el rango. Falta calcular P(2º grupo en turno N) y P(3º grupo en turno N). |
| **Memoria por 2º+ Tamer** | 2 | Probar 1 y 3. |
| **Cupo de ataques que no van a seguridad** | 3 (+1) | Probar 2 (+1). Vigilar el vaciado de boards chicos/medianos (4–5 Digimon) en un solo turno — hallazgo `tt-v6-4cap-test` (§4.1 de simulations), nunca cerrado. |
| **Protección** | 2 usos por línea, 1 declaración/turno | Probar 1 y 3 por línea; 1 vs 2 declaraciones por turno. |

---

## 3. Riesgos de arquetipo a vigilar

- **Turtle de 1 grupo con Tamer intocable.** Con §2.1 (el último Tamer es inmune a remoción rival) + protección de 1 carta/turno + DP concentrado, un mazo de un solo grupo evolucionado y amurallado puede ser muy difícil de matar. El incentivo a ir ancho (más grupos = más ataques a seguridad) tiene que ganarle a amurallarse en un grupo protegido. La sim 6.6 dijo que hay triángulo de counters sano, pero fue **antes** de §2.1.
- **Decapitación de Tamers** (el riesgo opuesto): en principio contenido por §2.1 + que solo se puede atacar Tamers vía efecto específico. Confirmar que quedó contenido y no sobre-contenido.
- **Stacking de Tamers de ramp pasivo** (3 en grupos, +memoria por turno cada uno). Se aceptó como no degenerado (la mayoría pide un piso de 2 de memoria, pocos dan +1) — verificar en mesa.
- **Pump global de Options acotado al grupo** (§3): puede inclinar el meta hacia agro. Verificar balance agro/control.
- **`[On Play]` de Tamers reactivado** (§2.3): reintroduce parte del swing que el formato venía podando, ahora por la tubería lenta de eclosión. Vigilar qué Tamers se rompen como "pick de setup" (el que se coloca en la preparación con su `[On Play]` gratis para ambos jugadores).

---

## 4. Pool de cartas

- **Legalidad** = lista oficial de Bandai (Banned/Restricted/Banned Pairs) para torneos sancionados. Sin banlist propia del formato.
- Falta un **audit de cuánto del pool real queda muerto o marginal**: Tamers cuyo valor era exclusivamente su `[On Play]` desde mano, Tamers que solo digivolucionan a Digimon (§2.2), cartas que dependían de tener un Tamer en el mazo principal para requisito de color de Options, etc. Si el subconjunto muerto es grande, decidir si el formato necesita una whitelist o una errata propia.

---

## 5. Faltan decklists de referencia

No existe ninguna. Armar **3–4 mazos completos y legales** en el formato como base común de testeo:

1. Agresivo ancho (curva baja, multi-cuerpo por grupo).
2. Control evolucionado (pocos Digimon, DP alto).
3. Multi-grupo (rushea Tamers, varios grupos chicos).
4. Tamer-turtle (1 grupo, Tamer intocable, muralla) — para estresar el riesgo de §3.

---

## 6. Casos de reglas menores a confirmar en mesa

- **Grupo vacío** (Tamer sin ningún Digimon): resuelto como "grupo válido sin atacante" (§2.4); confirmar que no genera fricción de mesa.
- **Ventana de gracia de la protección** y **tope de 2 por línea evolutiva**: los mecanismos más nuevos, nunca ejercitados en una partida completa de las simulaciones (hallazgo 6.7).
- **`[On Play]` de Tamer resolviéndose en la preparación** con la mano inicial todavía sin robar: confirmar que no genera interacciones raras (efectos que piden descartar, robar antes de tener mazo listo, etc.). El orden de §2.0 pone la resolución después de barajar el mazo justamente para esto.
- **Blocker global vs Decoy/Guard/Scapegoat/Save acotados al grupo** (§3): confirmar en mesa que la asimetría no confunde ni rompe nada.
