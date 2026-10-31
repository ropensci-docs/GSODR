# GSODR: Global Surface Summary of the Day ('GSOD') Weather Data Client

Provides automated downloading, parsing, cleaning, unit conversion and
formatting of Global Surface Summary of the Day ('GSOD') weather data
from the from the USA National Centers for Environmental Information
('NCEI'). The data were retired on 2025-08-29 and are no longer updated.
Units are converted from from United States Customary System ('USCS')
units to International System of Units ('SI'). Stations may be
individually checked for number of missing days defined by the user,
where stations with too many missing observations are omitted. Only
stations with valid reported latitude and longitude values are permitted
in the final data. Additional useful elements, saturation vapour
pressure ('es'), actual vapour pressure ('ea') and relative humidity
('RH') are calculated from the original data using the improved
August-Roche-Magnus approximation (Alduchov & Eskridge 1996) and
included in the final data set. The resulting metadata include station
identification information, country, state, latitude, longitude,
elevation, weather observations and associated flags. For information on
the 'GSOD' data from 'NCEI', please see the 'GSOD' 'readme.txt' file
available from, <https://www.ncei.noaa.gov/pub/data/gsod/readme.txt>.

## See also

Useful links:

- <https://docs.ropensci.org/GSODR/>

- <https://codeberg.org/ropensci/GSODR>

- Report bugs at <https://codeberg.org/ropensci/GSODR/issues>

## Author

**Maintainer**: Adam H. Sparks <adamhsparks@gmail.com>
([ORCID](https://orcid.org/0000-0002-0061-8359))

Authors:

- Adam H. Sparks <adamhsparks@gmail.com>
  ([ORCID](https://orcid.org/0000-0002-0061-8359))

- Tomislav Hengl <tom.hengl@isric.org>
  ([ORCID](https://orcid.org/0000-0002-9921-5129))

- Andrew Nelson <dr.andy.nelson@gmail.com>
  ([ORCID](https://orcid.org/0000-0002-7249-3778))

Other contributors:

- Hugh Parsonage <hugh.parsonage@gmail.com>
  ([ORCID](https://orcid.org/0000-0003-4055-0835)) \[copyright holder,
  contributor\]

- Taras Kaduk <taras.kaduk@gmail.com> (Suggestion for handling bulk
  station downloads more efficiently) \[contributor\]

- Gwenael Giboire <gwenael.giboire@oda-groupe.com> (Several bug reports
  in early versions and testing feedback) \[contributor\]

- Łukasz Pawlik <lukpawlik@gmail.com> (Reported bug in windspeed
  conversion calculation) \[contributor\]

- Ross Darnell <Ross.Darnell@data61.csiro.au>
  ([ORCID](https://orcid.org/0000-0002-7973-6322)) (Reported bug in
  'Windows OS' versions causing 'GSOD' data untarring to fail)
  \[contributor\]

- Tyler Widdison <Tyler.Widdison@usav.org> (Reported bug where
  \`nearest_stations()\` did not return stations in order of nearest to
  farthest) \[contributor\]

- Wenbo Lv <lyu.geosocial@gmail.com> (Provided suggestions for improving
  documentation) \[contributor\]

- Curtin University ([ROR](https://ror.org/02n415q13)) (url:
  http://www.curtin.edu.au/) \[funder, copyright holder\]
