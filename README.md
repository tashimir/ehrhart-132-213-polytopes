# Exact refined Eulerian coordinates

Data accompanying Pedro Machado Manhães de Castro, *Ehrhart h-star-Polynomials of (132,213)-Avoiding Permutation Polytopes: A Repair Cone and Eventual Real-Rootedness* (2026).

The dataset contains the exact scaled refined Eulerian coordinates used in the article's finite certificate for every integer $1\le d\le1000$.

## Download

Download [refined_coordinates_d1_d1000.csv](https://github.com/tashimir/ehrhart-132-213-polytopes/releases/download/v1.0.0/refined_coordinates_d1_d1000.csv) from the [version 1.0.0 release](https://github.com/tashimir/ehrhart-132-213-polytopes/releases/tag/v1.0.0). The file is 996,682,200 bytes, approximately 997 MB.

## Reading the data

The file is UTF-8 text with comma-separated fields, one header row, and 500,500 data rows. Each pair $(d,j)$ appears once, in increasing order of $d$ and then $j$.

| Column | Meaning | Values |
| :--- | :--- | :--- |
| `d` | Size of the permutations defining $P_d(132,213)$ | Integers from 1 to 1000 |
| `j` | Refined coordinate index | Integers from 0 to $d-1$ |
| `alpha_scaled` | Exact integer $\alpha_{d,j}=d!a_{d,j}$ | Signed decimal integers |

Read `alpha_scaled` as an arbitrary-precision integer, or as text until converting it to one. Recover the rational coordinate $a_{d,j}$ by dividing by $d!$ with exact rational arithmetic. The coordinates multiply the refined Eulerian basis polynomials defined in Section 5 of the article.

The first six records are:

```csv
d,j,alpha_scaled
1,0,1
2,0,2
2,1,0
3,0,6
3,1,0
3,2,6
```

For a fixed $d$, select its $d$ records and retain the order $j=0,\ldots,d-1$. For example, the records with $d=4$ give the scaled vector $(24,4,76,24)$ and hence the refined coordinate vector $(1,1/6,19/6,1)$.

## Mathematical definitions and verification

Start with **Section 7, “An exact finite certificate”**. It defines the CSV, derives the integer recurrence, and explains the exact sign test. Equation (33) reconstructs each scaled coordinate, and **Algorithm 1, “Verification of the exact finite certificate”**, gives the complete reconstruction and verification procedure.

The preceding sections supply the mathematical foundations:

| Article location | What it explains |
| :--- | :--- |
| Section 5, “The refined Eulerian expansion” | The basis polynomials and the coordinates $a_{d,j}$; the connected-block formula in equation (22) and the coordinate formula in equation (25) |
| Section 6, “The sharp repair cone” | The repaired-tail inequalities at $c_*=2-\sqrt{3}$ and their connection to real-rootedness, particularly Corollary 6.2 |
| Section 7, “An exact finite certificate” | Reconstruction of all 500,500 entries and exact verification of the 498,500 strict tail inequalities for $4\le d\le1000$, together with the three initial cases |

These references apply to the article accompanying version 1.0.0 of the data. Section titles identify the relevant material if numbering changes in a later article version.

## File integrity

The SHA-256 digest of the downloaded CSV is:

```text
8dbb43cad35659199cd23b5fddc23dd50f76d35adff5b636ac366d460069b5ce
```

## Citation

Please cite the data version used and the associated article. A citation for this release is:

> Pedro Machado Manhães de Castro (2026). *Exact refined Eulerian coordinates for (132,213)-avoiding permutation polytopes*, version 1.0.0. https://github.com/tashimir/ehrhart-132-213-polytopes/releases/tag/v1.0.0.

[CITATION.cff](CITATION.cff) provides citation metadata for the dataset and the associated article.

## Copyright

Copyright 2026 Pedro M. M. de Castro. All rights reserved. See [COPYRIGHT.md](COPYRIGHT.md) for the terms of use.
