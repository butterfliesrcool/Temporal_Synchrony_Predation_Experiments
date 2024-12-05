# Is temporal synchrony necessary for effective Batesian mimicry?

**Corresponding authors:** Abigial E. Robinson (aer13@bu.edu), Sean P. Mullen (smullen@bu.edu)

**ABSTRACT:** Batesian mimicry occurs when palatable mimics gain protection from predators by evolving a phenotypic resemblance to an aposematic model species. While common in nature, the mechanisms maintaining mimicry are not fully understood. Patterns of temporal synchrony (i.e., temporal co-occurrence) and model first occurrence have been observed in several mimicry systems, but the hypothesis that predator foraging decisions can drive the evolution of prey phenology has not been experimentally tested. Here, using phenotypically accurate butterfly replicas we measured predation rates on the chemically defended model species Battus philenor and its imperfect Batesian mimic Limenitis arthemis astyanax under four different phenology conditions to understand the importance of temporal synchrony and model first occurrence in mimicry complexes. We predicted that protection for mimics increases when predators learn to avoid the models' aposematic signal right before encountering the mimic, and that learned avoidance breaks down over time in the model's absence. Surprisingly, we found that asynchronous model first occurrence, even on short time scales, did not provide increased protection for mimics. Mimics were only protected under conditions of temporal synchrony, suggesting that predators rely on current information, not previously learned information, when making foraging decisions.   

## **DESCRIPTION OF DATA FILE STRUCUTRE AND VARIABLES**

### **DATA FILES**

**Quabbin_GIS_Data.csv:** latitude and longitude coordinates for all field sites in the Quabbin Reservoir, MA, USA. Coordinates were collected using Garmin® eTrex 10 and 22x GPS units.\
experiment: experimental treatment that was conducted in that field site. Simultaneous treatment (sim), one-week time delay treatment (one), two-week time delay treatment (two), four-week time delay treatment (four)\
site: field site number (1-80)\
start_or_end: “start” indicates that the GPS coordinates are associated with the start of a field site, while “end” indicates the end of a field site\
latitude: latitude coordinate of field site\
longitude: longitude coordinate of field site\
time: date (yyyy-mm-dd) and time (00:00:00) that each coordinate measurement was taken

#### **Spectral Reflectance Data:**

**Limenitis_Facsimile_HW_Blue.csv:** spectral reflectance measurements of the blue hindwing (HW) color patch from 10 *Limenitis arthemis astyanax* facsimiles (i.e., fake butterfly models)\
wavelength: wavelength (NM) associated with each reflectance measurement\
fac_SampleNumber: columns show reflectance measurements of 10 samples labeled fac_1 through fac_10

**Limenitis_Real_HW_Blue.csv:** spectral reflectance measurements of the blue hindwing (HW) color patch from 10 *Limenitis arthemis astyanax* real butterfly wings\
wavelength: wavelength (NM) associated with each reflectance measurement\
real_SampleNumber: columns show reflectance measurements of 10 samples labeled real_1 through real_10

**Limenitis_ Facsimile_FW_Black.csv:** spectral reflectance measurements of the black forewing (FW) color patch from 10 *Limenitis arthemis astyanax* facsimiles (i.e., fake butterfly models)\
wavelength: wavelength (NM) associated with each reflectance measurement\
fac_SampleNumber: columns show reflectance measurements of 10 samples labeled fac_1 through fac_10

**Limenitis_Real_FW_Black.csv:** spectral reflectance measurements of the black forewing (FW) color patch from 10 *Limenitis arthemis astyanax* real butterfly wings\
wavelength: wavelength (NM) associated with each reflectance measurement\
real_SampleNumber: columns show reflectance measurements of 10 samples labeled real_1 through real_10

**Battus_Facsimile_HW_Blue.csv:** spectral reflectance measurements of the blue hindwing (HW) color patch from 10 *Battus philenor* facsimiles (i.e., fake butterfly models)\
wavelength: wavelength (NM) associated with each reflectance measurement\
fac_SampleNumber: columns show reflectance measurements of 10 samples labeled fac_1 through fac_10

#### **Predation Data:**

**Quabbin_Training_Phase_Data.csv:** data on predator attacks during training phase of predation experiment\
transect: transects that were associated with each experimental treatment; one-week time delay treatment (one), two-week time delay treatment (two), four-week time delay treatment (four)\
experiment.day: integer (1-4) representing the number of days a given facsimile had been in the field\
field.site: field site number (1-60)\
species: facsimile species; the model species *Battus philenor* (battus) or the control *Junonia coena* (junonia)\
attacks: number of facsimiles attacked in each site (count data)\
field.day: numeric value representing the calendar date corresponding to data collection during our 12-day experiment

**Quabbin_Testing_Phase_Data.csv:** data on predator attacks during testing phase of predation experiment\ 
treatment: specifies experimental treatment; simultaneous treatment (zero), one-week time delay treatment (one), two-week time delay treatment (two), four-week time delay treatment (four)\
experiment.day: integer (1-4) representing the number of days a given facsimile had been in the field\
field.site: field site number (1-80)\
species: facsimile species; the model species *Battus philenor* (battus), the mimic species *Limenitis arthemis astyanax* (limenitis) or the control *Junonia coena* (junonia)\
attacks: number of facsimiles attacked in each site (count data)\
field.day: numeric value representing the calendar date corresponding to data collection during our 7-day testing phase experiment

**Quabbin_Synchronous_Treatment_Data.csv:** data on predator attacks on model, mimic, and control facsimiles during the synchronous treatment of the testing phase\
treatment: specifies simultaneous treatment (zero)\
experiment.day: integer (1-4) representing the number of days a given facsimile had been in the field\
field.site: field site number (61-80)\
species: facsimile species; the model species *Battus philenor* (battus), the mimic species *Limenitis arthemis astyanax* (limenitis) or the control *Junonia coena* (junonia)\
attacks: number of facsimiles attacked in each site (count data)\
field.day: numeric value representing the calendar date corresponding to data collection during our 7-day testing phase experiment


### **CODE SCRIPTS**

**PAVO.Rmd:** this script contains annotated code for the pavo analysis and calculations of JND scores. This script uses all spectral reflectance data files described above. Data for the spectral reflectance of the blue hindwing (HW) patches of *Battus philenor* real butterfly wings were taken from:

Stavenga, D.G., Leertouwer, H.L. & Wilts, B.D. The colouration toolkit of the Pipevine Swallowtail butterfly, Battus philenor: thin films, papiliochromes, and melanin. J Comp Physiol A 200, 547–561 (2014). https://doi.org/10.1007/s00359-014-0901-7

**GLMMS.Rmd:** this script contains annotated code for training and testing phase generalized linear mixed models (GLMMs). This script uses all predaton data files described above 

**ebird_analysis.Rmd:** This  script contains code for all analyses of avain predator community dynamics and all associated figures. This script uses data downloaded from ebird.org. *eBird* is an open access data souce, and data used in this analysis can be downloaded directly from *eBird* using this link:  https://support.ebird.org/en/support/solutions/articles/48000838205-download-ebird-data#anchorEBD

To replicate this analysis, download the *eBird* Basic Dataset (EBD) records from all states in the Northeastern USA (Maine, New Hampshire, Vermont, Massachusetts, Rhode Island, Connecticut, New York, New Jersey, Pennsylvania) for all species and all years


## **R VERSION AND PACKAGE VERSION INFORMATION**
$R.version.string
[1] "R version 4.4.1 (2024-06-14)"

> packageVersion("pgirmess")
[1] ‘2.0.3’
> packageVersion("adehabitatHR")
[1] ‘0.4.21’
> packageVersion("vegan")
[1] ‘2.6.6.1’
> packageVersion("pavo")
[1] ‘2.9.0’
> packageVersion("glmmTMB")
[1] ‘1.1.9’
> packageVersion("DHARMa")
[1] ‘0.4.6’
> packageVersion("emmeans")
[1] ‘1.10.2’
> packageVersion("curl")
[1] ‘5.2.1’
> packageVersion("ggplot2")
[1] ‘3.5.1’
> packageVersion("lme4")
[1] ‘1.1.35.4’
> packageVersion("patchwork")
[1] ‘1.2.0’
> packageVersion("ggmap")
[1] ‘4.0.0’
> packageVersion("googleway")
[1] ‘2.7.8’
> packageVersion("rstudioapi")
[1] ‘0.16.0’
> packageVersion("rstatix")
[1] ‘0.7.2’

