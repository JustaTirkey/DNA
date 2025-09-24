# DNA Genome Sequencing

## Overview

This project implements a **DNA sequence analysis tool** using **Trie data structures**.
It can:

* Build a Trie from given DNA sequences.
* Search for disease-causing DNA substrings.
* Count the frequency of substrings in the genome.
* Detect if a DNA is diseased based on frequency thresholds.
* Apply **mutation rules** (before → after) and recheck for disease presence.

The implementation is in **C++** and uses standard input/output for interaction.

---

## Features

* **Trie Construction**: Efficient storage and lookup of DNA substrings.
* **Pattern Matching**: Finds all positions (indices) of disease-related sequences.
* **Frequency Analysis**: Checks if a substring occurs at least `f` times.
* **Mutation Handling**: Supports mutation transformations of disease patterns.
* **Disease Detection**: Prints `"Yes"` if DNA is diseased, `"No"` otherwise.

---

## Input Format

```
k n p IsMutated
<list of n DNA strings>
<list of p disease strings with frequency requirement>
[if IsMutated == 1]
    m
    <list of m mutation pairs: before after>
```

* `k` → length of DNA strings
* `n` → number of DNA strings
* `p` → number of disease strings
* `IsMutated` → `0` (no mutation) or `1` (mutation enabled)
* Each disease string is followed by its required frequency `f`.
* If mutations are enabled, `m` pairs of `(before → after)` substrings are provided.

---

## Output Format

1. Indices of DNA strings where disease patterns are found.
2. `"Yes"` if disease detected, `"No"` otherwise.
3. If mutation enabled:

   * Indices after applying mutations.
   * `"Yes"`/`"No"` result after mutations.

---

## Example

### Input:

```
3 4 2 1
ATG
GTC
ATG
TGA
ATG 2
GTC 1
2
ATG GGG
GTC TTT
```

### Output:

```
0 2 1 
Yes
0 2 1 
Yes
```

---

## How to Run

Compile and run the program with g++:

```bash
g++ DNA_genome_sequencing.cpp -o dna_seq
./dna_seq < input.txt
```

Or run interactively by entering input directly.

---

## File Structure

```
DNA_genome_sequencing.cpp   # Main source code
README.md                   # Documentation
```

---

## Future Improvements

* Add file-based input/output handling.
* Support for larger genomes with optimized memory.
* Visual representation of mutation effects.
* Parallel processing for faster analysis.

