# Exercise: thermal expansion of polymers

Files:
 - README.md: markdown formated file. Contains notes and remarks for the exercise. Read carefully!
 - dataset.csv: comma separated CSV txt file (open with any editor) that contains the "coefficient of thermal expansion" (cte) of 11 polymers. 
    
    Columns in CSV files: 
    - name: polymer name
    - abb: short name of polymer 
    - cte_exp: measured cte of the polymer in 1/K
    - Tg: glass transition temperature of the polymer in K
    - smiles: language to represent polymers (see https://www.polymergenome.org/guide and http://opensmiles.org/opensmiles.html)

Instruction:

1. Open the file in Python using the Python package pandas (`pip install pandas`). Use the `read_csv` function.

2. Need to work in a jupyter notebook: visualize the polymers using RDKit (`pip install rdkit`). Use the `Draw.MolsToGridImage` function and the `legend` argument to plot the polymers and the SMILES strings. Hint: `Draw.MolsToGridImage(mols, legends=df.smiles.tolist())`

3. Use matplotlib (`pip install matplotlib`) and plot `cte_exp` (ordinate) vs `abb` (abscissa) using dots with connected with dashed lines.

4. The empirical rule by Boyer-Spencer [1] states that `cte_bs * Tg = 0.08`. Add a column `cte_bs` to the data frame that contains the computed `cte_bs` for each polymer. `Tg` is already available in the data frame for each polymer. Plot both `cte_exp` and `cte_bs` vs `abb` in an new plot.

5. Find a new Boyer-Spencer parameter `a` that better fit to our data set. Use scipy's `curve_fit` function (`pip install scipy`) to fit the function `cte = a / Tg` to the data set. You should find `cte_bs_own = 0.035 / Tg`. Add `cte_bs_own` to the data frame and plot `cte_exp`, `cte_bs`, and `cte_bs_own` vs `abb` to how much better you own rule fits the data.



[1] R. Simha and R.F. Boyer, J. Chem. Phys., 37, 1003 (1962)