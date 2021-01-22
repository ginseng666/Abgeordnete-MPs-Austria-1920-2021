# Nationalratsabgeordnete, Mitglieder des Bundesrates und Abgeordnete zum Europäischen Parlament Österreich/MPs Austria 1920-2021
Current version/last update: 22.01.2021

The JSON contains most of the available information about Austrian Members of Parliament (1. Chamber/Nationalrat and 2. Chamber/Bundesrat) since 1920 as well as information about Austrias Members of the European Parliament since 1995. The data was scraped of the official website of the [Austrian parliament](https://www.parlament.gv.at).

A list of all current MPs on regional level in Austria can be found here: [https://www.austriandemocracylab.at/landtage/](https://www.austriandemocracylab.at/landtage/)

nr_complete.json: the fields in the file for the 1. Chamber (Nationalrat, elected directly) are:

* id: string; just an identifier, "nr_" + running number
* whole_name: string; name of the person, including academic titles
* given_name: string; first name(s) of the person
* surname: string; last name of the person (for sorting and stuff)
* title: array; the first entry contains all titles coming ahead of the name, the second one all titles after the name (empty if no titles are present)
* academic: boolean; true if person holds an academic title
* sex: string; m for man, w for woman
* birth: string; date of birth (dd.mm.yyyy)
* place_of_birth: string; place of birth
* place_of_birth_addition: string; sometimes there is additional information given on the place of birth, like a country or a state - note that this is very selective in the source file and the values are not standardised (you might find "Niederöstereich" as well as "NÖ", although I've tried to correct at least this inconsistency)
* death: string; date of death (dd.mm.yyyy) - empty if still alive; note that several entries from the beginning of the 20th century are not in this format, but only vague like giving a month and year
* place_of_death: string; place of death
* place_of_death_addition: string; see above
* active: boolean; true if person currently holds a seat in the national assembly
* profession: string; profession as stated by the MP
* clubs: array of all parliamentary clubs in which the person was/is a member (note that clubs are not identical with political parties; also there have been several name changes, leading to a larger number of clubs than there were parties in parliament) (Klub)
* sessions: array of all parliamentary sessions in which the person held a seat (independent of the time the seat was held); they are numbered in roman numerals (V. was the first session of the Second Republic in 1945) (Gesetzgebungsperiode)
* nr: array; contains objects of each independent time period the person held a seat in the national assembly; the object itself contains the "club" the person was a member of, the start and the end date (strings; dd.mm.yyyy); if the person holds currently a seat, "end" = "ongoing"
* others: all other seats held by the person as stated in the section "Mandate", split into the following fields :
    * br: array; seats in the 2. chamber (Bundesrat)
    * eup: array; seats in the European Parliament
    * government: array; functions in a government (this is a rough summary of very different functions, including federal ministries, secretaries, temporary assignments and so on)
    * others: array; other functions
    * note that the entries in "br" and "eup" follow the logic of the "nr"-field, containing the club, the start and the end date; for government and other functions, the field "club" has been replaced by "function"
* pol_functions: array; contains all entries on the website of the MP about their political life
* employment: array; contains all entries on the website of the MP about their professional life
* education: array; contains all entries on the website of the MP about their education

<br>
<br>
br_complete.json: the fields for the 2. Chamber (Bundesrat, members are appointed by the regional parliaments) are mostly the same, with four differences:

* the id starts with "br_"
* the field "nr" is renamed "br" (for Bundesrat): array; contains objects of each independent time period the person held a seat in the second chamber; the object itself contains the "club" the person was a member of, the start and the end date (strings; dd.mm.yyyy); if the person holds currently a seat, "end" = "ongoing"
* subsequently, the field "br" in the "others"-section is renamed "nr" and contains possible seats in the Nationalrat
* state: array; this field contains the delegating region, aka the state the Bundesrat is representing

<br>
<br>
eup_complete.json: the fields for the European Parliament are mostly the same, with four differences:

* the id starts with "eup_"
* the field "nr" is renamed "eup" (for European Parliament): array; contains objects of each independent time period the person held a seat in the second chamber; the object itself contains the "club" the person was a member of, the start and the end date (strings; dd.mm.yyyy); if the person holds currently a seat, "end" = "ongoing"
* subsequently, the field "eup" in the "others"-section is renamed "nr" and contains possible seats in the Nationalrat
* there is no field "sessions"

<br>
<br>
Note that the political functions, employment and education follow no standardised pattern, the MPs are free to include/exclude information. As several biographical pages are currently not linked correctly on the parliamentary website, the data about these persons is incomplete.

As the data was scraped automatically errors due to inconsistent tags are possible.

all data (c) https://www.parliament.gv.at

JSONs CC BY 4.0 Flooh Perlot 2021 (see licence)
