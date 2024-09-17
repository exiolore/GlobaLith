# GlobaLith model

The GlobaLith model presents a global carbon footprint model for the lithium-ion battery industry. The code implements a life cycle assessment (LCA) model to predict the 
carbon footprint (CF) of lithium-ion batteries (LIBs) based on various chemistries commonly used in electric vehicles,including NMC111, NMC622, NMC811, NCA and LFP.
The model follows LCA principles employing a cradle-to-gate system boundary, focusing on material and energy contributions to the CF. It incorporates data from multiple literature sources 
to calculate the material demand and carbon footprint for LIB production, and a Monte Carlo simulation is performed to quantify uncertainties in the CF estimations. The geographical scope 
is global, accounting for variations in the carbon intensity of electricity supply in key battery manufacturing locations worldwide. The output of the code includes the cradle-to-gate CF 
of LIB production under different scenarios and projections of greenhouse gas emissions on a global scale. The main code has been used in the publication "Think global act local: 
The dependency of global lithium-ion battery emissions on production location and material sources" to estimate the carbon footprint of battery manufacturing from a global context. 
The full version of the publication is openly accessible here: https://www.sciencedirect.com/science/article/pii/S0959652624011739.

The modelling logic is as follows:
* 
First, the material demand to produce a kWh of battery pack capacity for different chemistries was estimated, including NMC111, NMC622, NMC811, NCA and LFP. The bill-of-materials for all these chemistries was taken from GREET and material demand was estimated using a 2% cut-off rule
Next, for each material used in battery manufacturing, the carbon footprint was extracted from a combination of literature sources, industry reports and LCA databases. The following script simply plots the data shown in the supplementary tables of the original paper.
A Monte Carlo simulation was ran, by combining the material demand to produce each battery chemistry with the carbon footprint of battery materials. The latter was assumed to vary based on a uniform distribution, with min/max values taken from the graph above (Fig.2 in the original paper). 
Next, the material contribution to the carbon footprint of LIBs was estimated through the Monte Carlo simulation. The energy contribution to the carbon footprint of a LIB was estimated by assuming that manufacturing consumes 40 to 80 kWh of energy per kWh of cell capacity. Key manufacturing locations around the world were considered based on gigafactory projections.
The energy and material contributions to the carbon footprint were combined to estimate the cradle-to-gate carbon footprint of LIBs.
Finally, a rough calculation was performed to estimate the carbon emissions of the battery industry globally. 
