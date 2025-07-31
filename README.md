# BIKE2.1

## BIKE model version 2.1
Foodborne exposure assessment model for biological and chemical hazards

This is a Bayesian model for estimating foodborne exposures based on dietary data on food consumption frequencies and amounts, and corresponding occurrence data on hazard concentrations (chemical and microbiological) and hazard prevalence (microbiological). The model can be used as a shiny app providing a user interface. Data need to be specified in files that are read by R-code, which then creates the necessary BUGS code of the Bayesian model which is simulated using OpenBUGS in the background. Results are processed in R and presented in the shiny app. Users need to have both R and OpenBUGS installed.

## Instructions
1. First install R, RStudio and OpenBUGS to your computer.

https://posit.co/download/rstudio-desktop/

OpenBUGS is no longer on this site:
https://www.mrc-bsu.cam.ac.uk/software/bugs/openbugs/
But it could be downloaded from here:
https://openbugs.software.informer.com/download/?cf25c9ce#downloading
And the file OpenBUGS323setup.exe is also copied in this BIKE2.1 folder for convenience. 

2. Download the BIKE-code files and unzip in local folder.
3. Open the app.R file in RStudio.
4. Install R-packages as needed.
5. Run the app.

# 
#### Original publication:
Ranta J, Mikkelä A, Suomi J, Tuominen P. BIKE: Dietary Exposure Model for Foodborne Microbiological and Chemical Hazards. Foods. 2021; 10(11):2520. https://doi.org/10.3390/foods10112520 

#### Cite BIKE app as:
Ranta J, Marinova-Todorova M, Mikkelä A, Suomi J, Tuominen P 2023. BIKE foodborne exposure model - A graphical user interface for the Bayesian dietary exposure assessment model for microbiological and chemical hazards (BIKE). Finnish Food Authority, Helsinki, Finland. Available at https://bike-expo-shiny.rahtiapp.fi/

#### Updates:
Consumption frequency estimated as population average "p0" from Bayesian model (uncertainty). Individual consumption frequencies predicted (variability between consumers) only where needed.

Exposure quantile estimation (2D simulation of uncertainty & variability) computations improved by vectorizing some evaluations which previously were indexed in loops.

Radio buttons for model choice on correlation model for consumption frequencies corrected to be nested (conditional on upper level model choice).  

Some individuals are allowed to have less observed days than others in consumption data. Their "observations" on missing days need to be coded as NA, so that the consumption data table remains a full table spanned by the maximum number of observation days among all individuals. 
 
