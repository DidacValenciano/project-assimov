```plaintext
                         +---------------------+
                         |     executor.py     |
                         |   (Punt d'entrada)  |
                         +---------+-----------+
                                   |
                                   v
                  +-------------------------------+
                  |     phase_0_gramaneute.py     |
                  |  (Interpreta prompt, assigna  |
                  |   rols i models amb ajuda de  |
                  |   llm_selector i roles)       |
                  +-------------------------------+
                                   |
                                   v
                  +-------------------------------+
                  |   phase_1_yaml_generator.py   |
                  |   (Genera estructura YAML)    |
                  +-------------------------------+
                                   |
                                   v
                  +-------------------------------+
                  | phase_2_section_expander.py   |
                  | (Expandeix contingut per      |
                  | secció, segons YAML)          |
                  +-------------------------------+
                                   |
                                   v
                  +-------------------------------+
                  | phase_3_coherence_refiner.py  |
                  | (Millora coherència, to i     |
                  | argument amb revisors LLM)    |
                  +-------------------------------+
                                   |
                                   v
                  +-------------------------------+
                  |    phase_4_tex_writer.py      |
                  | (Compila el text final en .tex|
                  | usant formatter, etc.)        |
                  +-------------------------------+
                                   |
                                   v
                  +-------------------------------+
                  |  phase_5_final_polisher.py    |
                  | (Opcional: poliment estilístic|
                  | final humà o LLM)             |
                  +-------------------------------+

    ┌────────────────────────────────────────────────────────┐
    │                    Mòduls de suport                    │
    ├────────────────────────────────────────────────────────┤
    │  engine/planner.py         -> Planificació estructural │
    │  engine/roles.py           -> Definició de rols        │
    │  engine/llm_selector.py    -> Tria de LLMs             │
    │  engine/orchestrator.py    -> Control de flux          │
    └────────────────────────────────────────────────────────┘

    ┌────────────────────────────────────────────────────────┐
    │                     Interfície GUI                     │
    ├────────────────────────────────────────────────────────┤
    │  gui/app.py             -> Interfície Flask/FastAPI    │
    │  gui/templates/         -> Plantilles HTML/Jinja       │
    └────────────────────────────────────────────────────────┘
```
