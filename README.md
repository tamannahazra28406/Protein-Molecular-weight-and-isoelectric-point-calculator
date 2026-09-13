This file is a **Jupyter Notebook (`.ipynb`) script** written in Python (designed to run in environments like Google Colab) that provides a lightweight bioinformatics toolkit for analyzing **protein amino acid sequences**.

---

### Key Capabilities & Functions

* **Sequence Validation (`validate_protein`)**: Checks whether an input protein sequence contains only valid single-letter amino acid codes.


* **Molecular Weight Calculation (`molecular_weight`)**: Computes the overall molecular weight of a protein in Daltons (Da) by summing individual residue masses and adding terminal water mass.


* **Isoelectric Point Estimation (`calculate_pI`)**: Uses a binary search (bisection method) to calculate the isoelectric point (pI)—the pH level at which the protein carries a net charge of zero—based on N-terminus, C-terminus, and side-chain pKa values.


* **Amino Acid Composition (`amino_acid_composition`)**: Counts the total frequency of each amino acid residue present in the sequence.


* **Interactive CLI Execution**: Prompts the user to enter a custom protein sequence and prints out the sequence length, molecular weight, pI, and a sorted breakdown of amino acid counts.
