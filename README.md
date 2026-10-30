# GenLabs.Genome

Complete bacterial genomes as plain text, ready to load in a single read. They are the inputs for [GenLabs.DnaUtils](https://github.com/valburkin/GenLabs.DnaUtils), for example its [origin-of-replication sample](https://github.com/valburkin/GenLabs.DnaUtils/tree/main/samples/OriFinder).

| File | Organism | Length (bp) | Source |
|---|---|---:|---|
| [`escherichia_coli.txt`](escherichia_coli.txt) | *Escherichia coli* K-12 substr. MG1655 | 4,639,675 | GenBank [U00096.2](https://www.ncbi.nlm.nih.gov/nuccore/U00096.2) |
| [`salmonella_enterica.txt`](salmonella_enterica.txt) | *Salmonella enterica* subsp. *enterica* serovar Typhi CT18, chromosome | 4,809,037 | GenBank [AL513382.1](https://www.ncbi.nlm.nih.gov/nuccore/AL513382.1) |

## Format

Each file holds one chromosome as a single line of uppercase `A`, `C`, `G` and `T`, with no FASTA header and no line breaks. Position 0 is the first base of the GenBank record.

```csharp
using GenLabs.DnaUtils;

var genome = new Sequence(File.ReadAllText("escherichia_coli.txt").Trim());
genome.GetMinSkewPositions();   // [3923620, 3923621, 3923622, 3923623]
```

## Source and terms

The sequences are taken unchanged from the GenBank records linked above. NCBI places no restrictions on the use or distribution of GenBank data; see the [NCBI policies](https://www.ncbi.nlm.nih.gov/home/about/policies/).
