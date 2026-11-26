# CR — Celestial Resonance

Constitutional resonance system that transforms reality-derived evidence into durable, reusable judgment. The product is **Artificial Inheritance**. Runtime-agnostic: runs on Gemini, Claude, Mistral, GPT, or plain Python — no model owns knowledge; the Crystal owns knowledge.

## Repository index

```
cr-celestial-resonance/
├── README.md                 this index
├── charter.md                Edge of the Everest founding charter
├── docs/
│   └── MKC.md                deep README for the MKC constitutional memory layer
├── resonance-container/      IP VULT: collected resonance lands here directly, from any runtime
│   ├── README.md             container charter: IP, append-only, hash-bound, universal
│   ├── crystal-state.json    current Semantic Crystal + crystal_hash (Genesis: 47e648f7...)
│   ├── usc-chain.jsonl       notarization chain (recovery = replay)
│   ├── collected/            intake bins: lessons, scars, anomalies, evidence, interactions
│   │   └── INDEX.md          bin rules + naming + notarization protocol
│   └── register/             Principle Registry (generalized survivors only)
│       └── REGISTER.md      admission bar + entry shape
├── skills/celestial-resonance/   the portable CR skill (SKILL.md + assets)
│   ├── SKILL.md                  full operating instructions
│   ├── constitution.md           axioms, Climb, gates
│   ├── gemini-gem-design.md      universal runtime porting design (Gems, Projects, skills)
│   └── intake-example.md         worked intake example (arc-000001)
├── mkc/                      constitutional memory layer
│   ├── canonical.py          hashing + deterministic Clock
│   ├── records.py            badges, evidence refs, records, validation
│   ├── ledger.py             append-only ledger + replay
│   ├── usc_chain.py          USC hash chain + verify
│   ├── archive.py            five-class append-only archive
│   ├── governance.py         complexity + dependency taxes
│   ├── founder-log.jsonl     founder intake records (append-only)
│   └── charter.jsonl         charter intake, arc-000001–000013
├── resonance/                selection, cadets, breeding, promotion, crystal compiler
├── crystal/                  semantic_crystal.py, personality_compiler.py
├── runtime/                  interactions, perceptual code, evidence store
├── inheritance/              lessons, scars, principles, principle registry
├── tests/                    test_mkc, test_resonance, test_runtime_inheritance, test_success_criteria
└── personas/                 vibe, focus, scientist, builder, auditor, teacher (genome.json each)
```

## Layers

| Phase | Layer | Modules |
|---|---|---|
| 1 | MKC Ledger | `cr/mkc/ledger.py`, `cr/mkc/records.py` — replayable constitutional memory with badges `fact`, `claim`, `hypothesis`, `assumption`, `refuted`, `unknown`) |
| 1 | USC Chain | `cr/mkc/usc_chain.py` — append-only hash chain `seq`, `prev_hash`, `canonical_hash`, `timestamp`); recovery = replay |
| 1 | Archive | `cr/mkc/archive.py` — append-only classes: `history`, `failure`, `anomaly`, `scar`, `refutation` |
| 1 | Governance | `cr/mkc/governance.py` — complexity tax >= 1.5, dependency tax >= 1.7 |
| 2 | Selection | `cr/resonance/selection.py` — archive records -> archive or cadet; most stay archived |
| 2 | Cadets | `cr/resonance/cadets.py` — principle/scar/anomaly/constraint cadets with `training -> promoted | rejected` |
| 2 | Breeding | `cr/resonance/breeding.py` — cross-breed cadets into stronger candidates |
| 2 | Promotion | `cr/resonance/promotion.py` — auditable accept/reject; accepted = crystal material |
| 3 | Crystal Compiler | `cr/resonance/crystal_compiler.py` — promoted cadets -> Semantic Crystal (deterministic) |
| 3 | Semantic Crystal | `cr/crystal/semantic_crystal.py` — Canonical Surviving Resonance |
| 4 | Personality Compiler | `cr/crystal/personality_compiler.py` — Crystal + Genome + Runtime Context |
| 4 | Personas | genomes in `cr/personas/<name>/genome.json` |
| 5 | Runtime | `cr/runtime/interactions.py`, `cr/runtime/perceptual_code.py`, `cr/runtime/evidence.py` |
| 6 | Inheritance | `cr/inheritance/lessons.py`, `cr/inheritance/scars.py`, `cr/inheritance/principles.py`, `cr/inheritance/principle_registry.py` |

## Constitutional invariants

- No conclusions without lineage; no promotion without evidence.
- No deletes anywhere; every surface is append-only.
- Personalities never own knowledge — they hold references; the Crystal owns knowledge.
- Runtime outputs never modify the Crystal directly; they must pass selection -> cadets -> promotion.
- Everything notarizes through the MKC USC chain.
- Collected resonance lands directly in `resonance-container/` as Edge of the Everest intellectual property, from any runtime.

## Flow

```
any runtime (Gemini/Claude/Mistral/shell) -> interactions -> archive entries
        archive -> selection -> cadets -> cross-breeding -> promotion review
                accepted -> Crystal Compiler -> Semantic Crystal -> resonance-container
                        crystal-state.json -> personalities (any runtime)
        registry principles feed future Crystal compilations
```

## Run tests

```bash
python -m pytest cr/tests -q
```
