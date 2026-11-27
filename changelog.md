# Changelog

## v1.0 (2026-11-30)

### Flare catalogue

- STIX flares ≥ M5 were checked manually due to errors in the operational STIX flare list that was used to compute the SOLER Flare Catalogue. STIX flares were often duplicated due to introduction of the attenuator during strong events. These events were merged into single events, and the event parameters were updated. The associations between STIX and GOES flares were also manually revised resulting in further events being merged if they were observed by both spacecraft. As a result, the number of SOLER flares has changed since the first version release, while the covered time interval in solar cycle 25 remained the same. The flare indices and associations with CMEs and SEP events have been updated accordingly.
- The presence of metric type II radio bursts associated with each event has been added and includes 4 four new columns:
  - `Decametric Type II Burst Start Time (UT) (HH:MM)`
  - `Decametric Type II Burst End Time (UT) (HH:MM)`
  - `Decametric type II burst frequency range (MHz)`
  - `Radio Comments`
- In the cases where no type II radio burst associations were found, the columns remain empty. The type II events have been extracted from the National Oceanic and Atmospheric Administration (NOAA) Space Weather Prediction Centre (SWPC) event reports. The events were selected such that they occurred within one hour of the flare start time.
- The presence of coronal waves associated with flare events has now been added in the column `Coronal waves`. In the cases where an association was found, the word `yes` is included in this column, otherwise the entry remains empty. The coronal wave events have been extracted from the _Large-scale Coronal Propagating Fronts_ list maintained by Nariaki Nitta (<https://aia.lmsal.com/AIA_Waves/>, see for example Nitta et al., 2013).
- Associations with CMEs and SEP events have been re-checked manually and indices have been updated accordingly.

### CME catalogue

- Two new columns were introduced that contain the flare class of associated flare observed with both GOES and STIX, respectively. For flares weaker than M5, the flare class is also listed for events ≥ C1, even though the corresponding flare is not included in the flare catalogue. For those flares fully or partially occulted, resulting in no X-ray flare or a flare strength < C1, a notation, `o`, has been included instead of the flare class to notify this. In cases where the flare association with the SOLER CME was unclear, the notation `u` is used instead of the flare class. The CME associations with flares for both GOES and STIX flares were initially performed automatically, however,  a manual check has been performed and missed events, as well as occulted events, have been added manually.
- The presence of metric type II radio bursts associated with each event has been added and includes 4 four new columns:
  - `Decametric Type II Burst Start Time (UT) (HH:MM)`
  - `Decametric Type II Burst End Time (UT) (HH:MM)`
  - `Decametric type II burst frequency range (MHz)`
  - `Radio Comments`
- In the cases where no type II radio burst associations were found, the columns remain empty. The type II events have been extracted from the NOAA SWPC event reports. The type II events were selected such that they occurred up to two hours before the Large Angle and Spectrometric Coronagraph Experiment (LASCO) CME start time.
- The presence of coronal waves associated with CME has now been added in the column `Coronal waves`.  In the cases where an association was found, the word `yes` is included in this column, otherwise the entry remains empty. The coronal wave events have been extracted from the _Large-scale Coronal Propagating Fronts_ list maintained by Nariaki Nitta (<https://aia.lmsal.com/AIA_Waves/>, see for example Nitta et al., 2013).
- Associations with flares and SEP events have been re-checked manually and indices have been updated accordingly.

### SEP catalogue

- Extension of the catalogue for the year 2024 (69 new events added).
- All 1 MeV electron events observed by SOHO/EPHIN have been re-analyzed with a new level 3 data set (Jensen et al., 2026).
- Electron to proton ratios between ~1 MeV electrons and >25 MeV protons have been added. For Parker Solar Probe, BepiColombo, and SOHO we directly use the peak intensity entries of the catalogue. For Solar Orbiter and STEREO A we follow the procedure described in Dresing et al. (2024).

- Old events (2020-11-29 to 2023-12-31) have been revisited resulting in the following changes:
  - For SEP0043 Flare_IDX and CME_IDX removed.
  - CME0054 added to SEP0047.
  - CME0073 added to SEP0051.
  - Flare for SEP0073 is replaced with SOLER FLARE0129.
  - Flare for SEP0098 is replaced with SOLER FLARE0160.
  - STIX flare class is updated to M5 for SEP0011 for FLARE0001.
  - Flare for SEP0031 is replaced with a STIX Flare with class M2.
  - Flare for SEP0039 is removed. No suitable flare candidate is identified.
  - Flare for SEP0043 is removed. No suitable flare candidate is identified.
  - STIX flare class for FLARE0048 for SEP0044 is updated to M9.
  - Flare for SEP0050 is replaced with a STIX flare with class M2.
  - Flare for SEP0052 is removed. No suitable flare candidate is identified.
  - Flare for SEP0062 is replaced with a GOES flare with class C9.7.
  - Flare for SEP0050 is replaced with a STIX flare with class M2.
  - Flare for SEP0087 is replaced with a STIX flare with class C3.
  - Flare for SEP0097 is replaced with a STIX flare with class C3.3.
  - 1MeV electron SOHO data is replaced with a new SOHO level 3 data set for analysis.
  - `p25MeV PyOnset date (yyyy-mm-dd)` and `p25MeV inferred injection date (yyyy-mm-dd)` corrected for SEP0064 from 2023-05-05 to 2023-05-09.
  - `e100kev comment` column added for 100keV electrons (was accidentally missing in the first release).
  - Solar-MACH links have been updated accordingly in case of changes in flare associations.

### References

Dresing, N., Yli-Laurila, A., Valkila, S., Gieseler, J., Morosan, D. E., Farwa, G. U., Kartavykh, Y., Palmroos, C., Jebaraj, I., Jensen, S., Kühl, P., Heber, B., Espinosa, F., Gómez-Herrero, R., Kilpua, E., Linho, V.-V., Oleynik, P., Hayes, L. A., Warmuth, A., Schuller, F., Collier, H., Xiao, H., Asvestari, E., Trotta, D., Mitchell, J. G., Cohen, C. M. S., Labrador, A. W., Hill, M. E., & Vainio, R. (2024): The solar cycle 25 multi-spacecraft solar energetic particle event catalog of the SERPENTINE project. A&A, 10.1051/0004-6361/202449831

Jensen, S., Heber, B., Hörlöck, M., Kollhoff, A., Kühl, P., Sierks, H., & Thoma, A. (2026): Energy spectra of near-relativistic and relativistic electrons: A new data product from SOHO EPHIN. A&A, 10.1051/0004-6361/202557974

Nitta, N. V., Schrijver, C. J., Title, A. M., and Liu, W. (2013): Large-scale Coronal Propagating Fronts in Solar Eruptions as Observed by the Atmospheric Imaging Assembly on Board the Solar Dynamics Observatory—an Ensemble Study, ApJ, 10.1088/0004-637X/776/1/58.

## v0.5 (2026-07-15)

- Initial release for SOLER User Workshop 2 in Potsdam, Germany on June 30 - July 3, 2026
