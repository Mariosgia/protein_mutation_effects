# protein_mutation_effects
Computational workflow for studying the impact of point mutations on protein structure and surface properties, combining ColabFold predictions, DSSP secondary-structure assignment, and solvent-accessible surface area analysis.

# Protein Mutation Surface Analysis

Computational workflow for studying the impact of point mutations on protein structure and surface properties using ColabFold, DSSP, and SASA-based analysis.

---

## Overview

This project investigates how surface mutations affect protein structure and surface properties using lysozyme (PDB: 1LYZ) as a model system.

The pipeline includes:

1. Mutation design based on structural inspection (PyMOL)
2. Structure prediction using ColabFold
3. Secondary structure assignment using DSSP
4. Surface analysis using solvent accessible surface area (SASA)
5. Comparative visualization of mutation effects

---

## Workflow

### 1. Sequence generation
Mutations are introduced into the wild-type lysozyme sequence and saved as FASTA files.

### 2. Structure prediction
Structures are generated using ColabFold. The top-ranked model (`rank_001`) is used for analysis.

### 3. Secondary structure annotation
DSSP is used to assign:
- Helices
- Beta strands
- Coil regions

These are encoded into the PDB B-factor field for visualization.

### 4. Surface analysis
Surface properties are computed using FreeSASA:
- Surface-exposed residues
- Hydrophobic surface residues
- Charged residues (+ / −)
- Net surface charge

### 5. Visualization
Results are plotted using a consistent matplotlib style (`plot_style.mplstyle`).

---

## Project Structure

```text
.
├── labbook.ipynb                  # Full analysis workflow
├── plot_style.mplstyle            # Matplotlib style configuration
├── lysozyme/
│   ├── sequences/                 # WT and mutant FASTA files
│   ├── colabfold_results/         # Raw ColabFold outputs
│   ├── best_models_with_ss/       # DSSP-annotated PDBs
│   ├── analysis/
│   │   └── surface_properties.csv # Final analysis results
│   ├── 1LYZ.pdb                   # Experimental structure
│   └── 1LYZ_with_ss.pdb           # DSSP-annotated WT
