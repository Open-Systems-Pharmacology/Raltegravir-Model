### 2.3.1 Absorption

As no intravenous data is currently available to study systemic clearance of raltegravir *in vivo*, only oral data was used for model building. For oral administration the following parameters play a role with regards to the absorption kinetics of a compound, which can be estimated with PBPK: solubility, lipophilicity and intestinal permeability. Moss et al. ([Moss 2013](#5-References)) published values for raltegravir solubility in population groups with very low-, low-, medium-, high-, and very high intestinal luminal pH, after a single 400 mg dose of raltegravir. For the raltegravir PBPK model we have applied the medium pH group for creating a pH dependent solubility profile throughout the intestinal tract. The lipophilicity as well as pKa of raltegravir was also published by Moss et al ([Moss 2012, Moss 2013](#5-References)) to be 0.58 (as log partition coefficient between octanol and water (pH 7) and 6.67 (acid)), respectively. These values were applied and fixed in the raltegravir PBPK model, without further optimization. Regarding intestinal transcellular permeability (Pint), Moss et al ([Moss 2012](#5-References)) reported a range of apical to basolateral apparent permeability in Caco-2 monolayer at different pH values. Using published functions Pint can be calculated from Caco-2 cell membrane permeability measurements (Parrot et al. ([Parrot 2002](#5-References))), Thelen et al. ([Thelen 2010](#5-References), Sun et al. ([Sun 2002](#5-References)) and Sjögren et al. ([Sjögren 2013](#5-References))). However as no reference/calibrator compound was available to correct for inter-study variability, these functions could not be applied, and it was decided to estimate the Pint from *in vivo* clinical data instead. Nevertheless, for plausibility check, a theoretical Pint was calculated using the aforementioned functions without correction, resulting in a range of Pint from 4.64E-04 to 1.47E-09 cm/min. The finally estimated (based on *in vivo* data) Pint falls within this range.

**Table 2.** Reported Caco-permeability and calculated theoretical effective permeability (intestinal transcellular permeability, Peff) values for raltegravir via different reported functions, lacking a reference compound for correcting inter-study variability.

| Reference publication of reported function | **pH apical to basolateral** | **Peff apical to basolateral (cm/min)** | **Reference compound available for correcting Inter study variability** |
| --------------------------------- | ------------------------- | ----------------- | --------------------------------------------- |
| Raltegravir Caco permeability (Moss 2012 ) | 7.4                       |6.60E-6           | -                                             |
| Raltegravir Caco permeability (Moss 2012) | 6.5                       | 9.20E-6           | -                                             |
| Parrot 2002                   | 7.4                       | 2.14E-04          | Not available                          |
| Thelen 2010             | 7.4                       | 1.47E-09          | Not available                               |
| Sjögren 2013         | 7.4                       | 1.03606E-6        | Not available                               |
| Sun 2002                      | 7.4                       | 2.77E-4           | Not available                               |
| Sun 2002                      | 6.5                       | 2.86E-4           | Not available                               |
| Simcyp (*)                       | 6.5                       | 4.62E-4           | Not available                               |

*Not published as paper, Simcyp applied an adapted version of Sun et al 2002 

### 2.3.2 Distribution

Laufer et al. ([Laufer 2009](#5-References)) published a fu in humans to be 0.17. [Barau et al 2013](#5-References) reported that raltegravir binds to serum albumin, and not alpha glycoprotein, which is built-in as such in the PBPK model.

After testing the available organ-plasma partition coefficient and cell permeability calculation methods built in PK-Sim, observed clinical data was best described by choosing the partition coefficient calculation by Rodgers and Rowland, and cell permeability calculation by PK-Sim standard. Specific organ permeability normalized to surface area was automatically calculated by PK-Sim.

### 2.3.3 Metabolism and Elimination

Kassahun et al. ([Kassahun 2007](#5-References)) studied the absorption, metabolism, and excretion of raltegravir in healthy volunteers after a single oral dose of 200 mg (200Ci) of [14C] raltegravir. Human liver microsomal incubations confirmed the dominant role of UGT metabolism for raltegravir. Additionally, data from incubations using cDNA-expressed UGTs indicate that the major mechanism of metabolism of raltegravir in humans is UGT1A1-mediated glucuronidation. Raltegravir was in particular converted by UGT1A1 and 1A9. The apparent arithmetic mean Km values for the glucuronidation of raltegravir by UGT1A1 and UGT1A9 were 99 (standard deviation (SD): 16) and 296 (SD: 55) µM, respectively. The corresponding Vmax values (nmol/min/mg) were 0.89 (SD: 0.05) for UGT1A1, and 0.53 (SD: 0.06) for UGT1A9.

Based on this information, the reported in vitro Km values for UGT1A1 and 1A9 were included in the model. Reported Vmax values were in units nmol/min/mg protein and thus not directly transferable into the PBPK model. Therefore, a joint scaling factor f<sub>UGT </sub> on the *in vitro* V<sub>max</sub> values was estimated to match observed *in vivo* data, and keeping the relative relationship between those *in vitro* values (0.89 and 0.53 nmol/min/mg) for UGT1A1 and UGT1A9 fixed according to:

V<sub>max,UGT1A1</sub> = f<sub>UGT </sub> *  V<sub>max,in-vitro,UGT1A1</sub>

V<sub>max,UGT1A9</sub> = f<sub>UGT</sub> * V<sub>max,in-vitro,UGT1A9</sub>

It is especially important to fix the relative contribution of both enzymes as a ratio to ensure that, when translating to other populations (e.g. children where both UGT’s undergo a different ontogeny pattern, or patients who have differently reduced amounts of UGT1A1 vs 1A9) the relative contributions can be adequately scaled. 
Note that the estimated scaling factor f<sub>UGT</sub> will be directly implemented into the final *in vivo* V<sub>max</sub> values (only V<sub>max,UGT1A1</sub> and V<sub>max,UGT1A9</sub> will be reported in [section 3](#3-Results-and-Discussion))

Finally, as ~9% of the dose is excreted in human urine as unchanged parent compound, GFR is introduced in the raltegravir PBPK model.
