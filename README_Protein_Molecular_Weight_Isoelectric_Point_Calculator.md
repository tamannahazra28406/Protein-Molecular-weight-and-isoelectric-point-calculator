# Protein Molecular Weight & Isoelectric Point Calculator

A Python/Jupyter Notebook that analyzes a protein sequence and calculates its **molecular weight**, **theoretical isoelectric point (pI)**, **sequence length**, and **amino acid composition**.

The calculator uses residue masses and pKa values defined directly in the notebook and estimates pI by finding the pH at which the calculated net charge approaches zero.

## Features

Given a protein sequence, the notebook can:

- Validate the amino acid sequence.
- Calculate protein molecular weight in **Daltons (Da)**.
- Estimate the theoretical **isoelectric point (pI)**.
- Count the number of each amino acid present.
- Report protein sequence length.

## Input

The program accepts a one-letter amino acid sequence.

Example:

```text
MKTIIALSYIFCLVFADYKDDDDK
```

The sequence is automatically:

- Stripped of leading/trailing whitespace.
- Converted to uppercase.
- Checked against the supported standard one-letter amino acid codes.

## Calculations

### Molecular Weight

The molecular weight is calculated by summing the residue masses and adding the mass of one water molecule:

```text
Molecular weight = Σ(residue masses) + water mass
```

The notebook uses:

```text
Water mass = 18.01524 Da
```

The output is reported in Daltons.

### Isoelectric Point (pI)

The notebook estimates pI from the protein's net charge as a function of pH.

It considers:

- N-terminal charge.
- C-terminal charge.
- Ionizable amino-acid side chains.
- Their specified pKa values.

The pI is found using a **bisection search between pH 0 and pH 14** until the selected tolerance is reached.

The default tolerance is:

```text
1e-4
```

### Amino Acid Composition

The notebook counts each amino acid appearing in the sequence and returns a dictionary containing the residue counts.

## Supported Amino Acids

The calculator supports the standard one-letter amino acid codes:

```text
A R N D C E Q G H I L K M F P S T W Y V
```

Unsupported characters result in a validation error.

## Example Output

For an entered sequence, the program prints information in this format:

```text
Sample protein sequence : ...
Length                  : ... residues
Molecular weight        : ... Da
Isoelectric point (pI)  : ...

Amino acid composition:
  A: ...
  C: ...
  ...
```

## Requirements

The notebook is written for **Python 3**.

The implementation uses standard Python functionality and does not require external scientific libraries for the core calculations.

## How to Run

### Google Colab

1. Open `Protein_Molecular_Weight_&_Isoelectric_Point_Calculator.ipynb` in Google Colab.
2. Run the code cell.
3. Enter a protein sequence when prompted.
4. Review the calculated molecular weight, pI, length, and amino acid composition.

### Local Jupyter

```bash
jupyter notebook "Protein_Molecular_Weight_&_Isoelectric_Point_Calculator.ipynb"
```

Run the notebook cell and enter the sequence when prompted.

## Implementation Details

The notebook defines:

- `validate_protein(seq)` — validates the sequence.
- `molecular_weight(seq)` — calculates molecular weight.
- `_net_charge_at_ph(seq, ph)` — calculates estimated net charge at a specified pH.
- `calculate_pI(seq, tolerance=1e-4)` — estimates pI using bisection.
- `amino_acid_composition(seq)` — counts amino acid residues.

The residue-mass and pKa constants are explicitly defined in the notebook.

## Limitations

The calculated pI is a **theoretical estimate** based on the pKa values encoded in the notebook. Actual protein behavior can differ because protein structure, local environment, post-translational modifications, solvent conditions, and other factors can affect ionization.

The molecular-weight calculation also represents the sequence-based theoretical mass rather than an experimental mass measurement.

## File

```text
Protein_Molecular_Weight_&_Isoelectric_Point_Calculator.ipynb
```

## Author

Created as a Python-based computational biology/biochemistry project.
