These benchmarks are made of generated files for Earth Observing Satellites Problems (EOSP).
Each benchmark names follows the pattern OS-V-S-P-jan_2x8_POI_XXXX, where:
    "OS" indicates the number of ONE-SHOT requests
    "V" indicates the number of VIDEO requests
    "S" indicates the number of STEREO requests
    "P" indicates the number of PERIODIC requests
	"jan" indicates that the weather used is based on the weather of first of january 2020
	"2x8" indicates that the constellation is composed by 8 orbits containing 2 satellites each
	"XXX" denotes the number of points of interests (POI) as an integer for concentrated instances ("None" is indicated for spread instances)

Each of these benchmarks contains several instances of different sizes, referred to as:
* 	small (around 50 requests)
* 	medium (around 250 requests)
* 	big (around 500 requests)
* 	large (around 1000 requests)


The requests types follow the definition as introduced in the following paper: Squillaci, S., Roussel, S., Pralet, C.: Parallel scheduling of complex requests for
a constellation of Earth observing satellites. In: Passerini, A., Schiex, T. (eds.)
Frontiers in Artificial Intelligence and Applications. IOS Press (2022). (available in https://ebooks.iospress.nl/pdf/doi/10.3233/FAIA220068)

4 types of requests can be found, referred to as ONE-SHOT, STEROSCOPIC, VIDEO and PERIODIC.
A study of algorithms solving these problems is available in XXXX.

Each input file works as follows:

NUMBER_OF_REQUESTS
for each request:
  REQUEST_ID,NUMBER_OF_OBSERVATIONS,REQUEST_TYPE
  for each observation :
    ONE_SHOT,VIDEO case:
      OBSERVATION_ID,SATELLITE_ID,WINDOW_START,WINDOW_END,DURATION,LATITUDE,LONGITUDE,ALTITUDE,SCORE
    STEROSCOPIC case:
      PAIR_ID,OBSERVATION_ID,SATELLITE_ID,WINDOW_START,WINDOW_END,DURATION,LATITUDE,LONGITUDE,ALTITUDE,SCORE
    PERIODIC case:
      TIME_SLOT_NUMBER,OBSERVATION_ID,SATELLITE_ID,WINDOW_START,WINDOW_END,DURATION,LATITUDE,LONGITUDE,ALTITUDE,SCORE


NUMBER_OF_DOWNLOAD_OPPORTUNITIES
for each download opportunity:
  DOWNLOAD_ID,SATELLITE_ID,WINDOW_START,WINDOW_END,LATITUDE,LONGITUDE,ALTITUDE


The scores are based on weather data. They differs from whose present in the CPAIOR paper because in the latter we compute classes of these scores as described in the paper.

The bounds of visiblity windows are expressed as integer representing the number of seconds spent since 0am.
The duration are expressed as integer, measures in seconds.

The domain of observations ID's and downloads ID's are disjoint.
The latitude and longitude of download opportunities represent the latitude and longitude of the ground station.
