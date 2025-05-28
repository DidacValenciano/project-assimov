# 🧠 Assimov System Architecture

This document outlines the modular architecture of the **Assimov Project**, which is designed as a multi-phase pipeline for generating structured documents via orchestration of multiple LLMs, guided by functional roles.

## 📂 Directory Overview

### `assimov/config/`
- `config.yaml`: Global configuration file (API keys, model priorities, limits, etc.)

### `assimov/core/`
Contains the main generation pipeline split into functional phases:
- `phase_0_gramaneute.py`: Prompt intake and role assignment via the "Grammarnaut"
- `phase_1_yaml_generator.py`: Generates YAML structure per section
- `phase_2_section_expander.py`: Expands sections using assigned LLMs
- `phase_3_coherence_refiner.py`: Refines argumentation and narrative coherence
- `phase_4_tex_writer.py`: Compiles output into `.tex` format
- `phase_5_final_polisher.py`: Optional stylistic polish by a purist LLM

### `assimov/engine/`
Support logic and orchestration tools:
- `planner.py`: Manages document plans and sequencing
- `roles.py`: Defines functional writing roles
- `llm_selector.py`: Assigns LLMs to roles based on context and resources
- `orchestrator.py`: Coordinates execution between phases and models

### `assimov/gui/`
- `app.py`: Optional graphical or terminal-based interface (to be implemented)

### Root scripts
- `executor.py`: Main pipeline launcher
- `__init__.py`: Module initializer
- `README.md`: Project overview

---

## 🧩 Modular Philosophy

The architecture follows a **functional-role + phase-based design**, where each component has a limited responsibility and communicates via YAML or structured memory. This approach enables substitution, scaling and parallelization, while preserving interpretability.

---

## 🚧 Work in Progress

All Python files are placeholders at the moment (`0 bytes`). This structure scaffolds the intended development workflow and will be expanded iteratively.

