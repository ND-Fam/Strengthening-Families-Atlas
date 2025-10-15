# Strengthening-Families-Atlas
Repository for the data used to create the Strengthening Families Atlas on the ND Fam website.


**Construction of the 1990 Labor Market Commuting Zone (CZ) estimates:**
The individual level data provided in the American Community Survey (ACS) is organzed at the PUMA-level. For a more intuitive and economically-relevant geographic interpretation, we have calculated various statistics at the 1990 Labor Market Commuting Zone (CZ) used by David Autor and David Dorn (2013). Because there are no straight-forward crosswalks between 2020 PUMAs and 1990 CZs, we employ the following methodology to calculate child poverty, children's living arrangments, and median household income at the 1990 CZ level:

**Step 1: Crosswalk 2022 PUMAS to 2012 PUMAs based on geographic overlap and relative population shares**
We utilize David Dorn's 2012 PUMA to CZ crosswalk in step 2 (Autor, Dorn, Hansen 2019). However, the data in the most current ACS is organized at the 2022-defined PUMA level. To crosswalk to CZs, we first need to crosswalk to 2012-defined PUMAs. To do this, we utilize a crosswalk provided by (SOURCE) that maps 2022 PUMAs to 2012 PUMAs based on geographic overlap and relative population population overlap. The variable "afactor2" represents the share of 2022 PUMA X's population that resides in 2012 PUMAs Y and Z


**Step 2: Crosswalk 2012 PUMAS to 1990 CZs based on geographic overlap and relative population shares**
Use the Stata command "joinby" to combine the Census microdata with the crosswalk file using the variable "puma2010". The variable "afactor" in the crosswalk indicates which fraction of a PUMA's population maps to a given CZ. To analyze weighted Census data, the person weight from the Census needs to be multiplied with "afactor".
