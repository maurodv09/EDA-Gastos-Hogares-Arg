### Feature Selection
The columns to be used for this project are selected:
- Identification: `id` `provincia`
- Household Composition: `cantmiem` `cantping` `reldep`
- Total and Per Capita Income and Expenses: `ingtoth` `ingpch` `gastot` `gastotpc`
- Types of Expenses: `gc_01` `gc_02` `gc_03` `gc_04` `gc_05` `gc_06` `gc_07` `gc_08` `gc_09` `gc_10` `gc_11` `gc_12`
- Payment Methods: `fp_contado` `fp_credito` `fp_especie` `fp_prodprop` `fp_tarjetas` `fp_otras` `fp_indef`.

### Missing Values
- `reldep`(17): These arise from `cantping` values equal to 0. These records were removed.
- `pf_indef`:(2): These records contained only null values for all their columns, so they were removed.

### Data Integrity

**Province**
- No errors were found in the province codes.

**Members**
- No records with 0 members.
- No records where the number of members (`cantmiem`) is less than the number of people receiving income (`cantping`).
- No errors in the calculation of the dependency ratio (`reldel`) = `cantmiem` / `cantping`.

**Income**
- No records with income equal to 0.
- No errors in the calculation of per capita income (`ingpc`) = (`ingtoth`) / (`cantmiem`).

**Expenses**
- Only category `g7` contained negative values (208 - less than 1%). These records were removed.
- No errors in the summation of types of expenses.
- No errors in the calculation of per capita expense (`gastopc`) = (`gastot`) / (`cantmiem`).

**Payment Methods** (fp_)
- A high number of errors and inconsistencies were detected in the calculation of payment methods, so it was ultimately decided to omit these columns for this analysis.
