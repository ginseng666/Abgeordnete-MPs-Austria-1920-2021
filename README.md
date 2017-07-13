# Nationalratsabgeordnete Österreich/MPs Austria 1920-2017
JSON with biographical and political data of Austrian Members of Parliament (Nationalrat/1. Chamber) since 1920.

The JSON contains available information about Austrian Members of Parliament (Nationalrat) since 1920. The data was scraped of the official website of the [Austrian parliament](https://www.parlament.gv.at). Last update July 13th, 2017.

The fields are:

* id: string; just an identifier
* name: string; name of the person, including academic titles
* surname: string; only the last name (for sorting and stuff)
* sex: string; m for man, w for woman
* birth: string; date of birth (dd.mm.yyyy)
* place_of_birth: string; place of birth
* death: string; date of death (dd.mm.yyyy) - empty if still alive
* place_of_death: string; place of death
* active: boolean; true if person currently holds a seat
* profession: string; profession as stated by the mp
* lists: string; the list(s) on which the person won their seat(s) (Wahlvorschlag)
* clubs: array of all parliamentary clubs in which the person was/is a member (note that clubs are not identical with political parties; also there have been several name changes, leading to a larger number of clubs than there were parties in parliament) (Klub)
* sessions: array of all parliamentary sessions in which the person held a seat (independent of the time the seat was held); they are numbered in roman numerals (V. was the first session of the Second Republic in 1945) (Gesetzgebungsperiode)
* mp_nr: array; contains objects of each independent time period the person held a seat in parliament; the object itself contains the "club" the person was a member of, the start and the end date (strings; dd.mm.yyyy); if the person holds currently a seat, "end" = "ongoing"
* pol_functions: array; contains all entries on the website of the mp about their political life
* employment: array; contains all entries on the website of the mp about their professional life
* education: array; contains all entries on the website of the mp about their education

Note that the political functions, employment and education follow no standardised pattern, the mps are free to include/exclude information. As several (about 30) biographical pages are currently not linked correctly on the parliamentary website, the data about these persons is incomplete.

As the data was scraped automatically errors due to inconsistent tags are possible.

all data (c) https://www.parliament.gv.at

JSON (c) Flooh Perlot (see licence)
