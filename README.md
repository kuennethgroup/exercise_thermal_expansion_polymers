# 🏋 Exercise - thermal expansion of polymers



## Instruction

1. Work in a jupyter notebook.

1. Load the `dataset.csv` file to Python. Use the `df = pd.read_csv` function of the pandas package (`pip install pandas`). The dataset contains multiple polymers with Tg and cte values. See the file description below for more information. 

2. Visualize the polymers using RDKit (`pip install rdkit`). Use the `Draw.MolsToGridImage` function and the `legend` argument to plot the polymers and the SMILES strings. Hint: `Draw.MolsToGridImage(mols, legends=df.smiles.tolist())`

3. Use matplotlib (`pip install matplotlib`) to plot `cte_exp` (ordinate) vs `abb` (abscissa) using dots with dashed lines. Hint: `plt.plot(x,y, 'o--)`.

4. The empirical rule by Boyer-Spencer [1] states that `cte_bs * Tg = 0.08` for polymers in its rubber state. Add a column `cte_bs` to the data frame that contains the computed `cte_bs` for each polymer. `Tg` is already available in the data frame for each polymer. Plot both `cte_exp` and `cte_bs` vs `abb` in an new plot.

5. Find a new Boyer-Spencer parameter `a` that better fit to our data set. Use scipy's `curve_fit` function (`pip install scipy`) to fit the function `cte = a / Tg`. You should find `a = 0.035` (`cte_bs_own = 0.035 / Tg`). Add `cte_bs_own` to the data frame and plot `cte_exp`, `cte_bs`, and `cte_bs_own` vs `abb` in a new plot to find out how much better your own rule fits the data.


[1] R. Simha and R.F. Boyer, J. Chem. Phys., 37, 1003 (1962)


## Files

 - README.md: markdown formated file. Contains notes and remarks for the exercise. Read carefully!

 - dataset.csv: comma separated CSV txt file (open with any editor) that contains the "coefficient of thermal expansion" (cte) of 11 polymers. 
    
    Columns in file: 
    - name: polymer name
    - abb: short name of polymer 
    - cte_exp: measured cte of the polymer in 1/K
    - Tg: glass transition temperature of the polymer in K
    - smiles: language to represent polymers (see https://www.polymergenome.org/guide and http://opensmiles.org/opensmiles.html)


## The Kuenneth group @ UBT

👀 https://kuenneth.uni-bayreuth.de

The Kuenneth Group at the University of Bayreuth is dedicated to democratizing machine learning in materials science. Materials informatics efforts are underway more vigorously than ever before to streamline materials design, discovery, development, and deployment efficiently and effectively. 
