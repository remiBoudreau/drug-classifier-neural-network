# Drug Classification Neural Network

## Confirmation of “A comparative study on the molecular descriptors for predicting drug-likeness of small molecules”

Identifying lead compounds showing pharmacological activity against a biological target is a focal point in the early-stages of drug discovery. Though high-throughput screening, in which automated machinery assays a library of compounds, remains the method of choice for identifying these lead compounds in the pharma industry, virtual screening is seeing increasing employment due to the high costs and time-demanding character of the former. Virtual screening is not without its drawbacks, however; it requires, attention to the adsorption, distribution, metabolism and excretion (ADME) properties (or generalization of such as explained below) of compounds of interest in order to narrow drug lead libraries down to more manageable sizes. 
Computationally calculating the ADME of compounds within a low margin of error in a reasonable amount of time, is very difficult.  To circumvent this, heuristic approaches have been developed such as Lipinsky’s Rule of 5 which predicts that poor adsorption or permeation is more likely when:
1. there are more than 5 H-Bond donors
2. there are more than 10 H-bond acceptors
3. the molecular weight is greater than 500 Daltons
4. the calculated octanol-water partition coefficient is greater than 5.

This particular rule of thumb has become one of the most popular set of conditions in order to determine the “drug-likeness” of a molecule in virtual screening, however, additional conditions may improve upon this approach. Indeed, this was determined to be true in work by [Mishra et. Al](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2728118/) in which 2 deep neural networks (DNN) with identical architectures were respectively trained using either the four conditions listed above as features or the four above with an additional 3 conditions and 4 features more – the polar surface area, desolvation energy in polar solvent, desolvation energy in nonpolar solvent and charge – to classify molecules as either “drug-like” or not. The definition for “drug-likeness” is based on the ZINC database’s definition of “drug-like”.
I have validated their main findings – that extending the Lipinsky’s rule of 5 approach to include other descriptors and conditions improves the predictive power of the approach – by building a very similar DNN architecture and training it with molecules taken from the same catalogue (ZINC database) and using the exact same methodology they used, but with a larger sample and using the tensorflow framework. Due to the random sampling without setting a seed, the results fluctuate negligibly, however, the relative results are the same: identification of “drug-like” molecules is substantially improved when additional features are taken into account with Lipinsky’s Rule of 5. 
The code is given with extensive commenting in order to follow the code very easily.
