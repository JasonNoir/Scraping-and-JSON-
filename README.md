# Scraping and working with JSON #


"What can Python web scraping do?
Instead of looking at the job site every day, you can use Python to help automate your job search's repetitive parts. Automated web scraping can be a solution to speed up the data collection process. You write your code once, and it will get the information you want many times and from many pages."

### JSON ###

* "JSON, is the initial for JavaScript Object Notation. Like csv, it is another format to store data. Easy for humans to read and write.
* Reading a JSON file in Python. There are two ways."
```python
import json
with open('data.json') as f:
  data = json.load(f)
print(data)
```

* "(Easy way) We can parse the content to pandas and treat it like a dataframe."

```python
import pandas as pd
df=pd.read_json('data.json')
print(df)
```
* Querying data can result in your IP being blocked. To avoid this, there are several options such as working with the time function or avoiding too many requests. In this example, we work with a stored dataset to avoid being blocked.  
JSON File:

```json
"events":[
      {
         "tournament":{
            "name":"A-League Men",
            "slug":"a-league-men",
            "category":{
               "name":"Australia",
               "slug":"australia",
               "sport":{
                  "name":"Football",
                  "slug":"football",
                  "id":1
               },
               "id":34,
               "flag":"australia",
               "alpha2":"AU"
            },
            "uniqueTournament":{
               "name":"A-League Men",
               
               
 ```

```python
def live():
    for element in jsondata['events']:
        leage =  element['tournament']['name']
        status = element["status"]["description"]
        hometeam = element['homeTeam']['name']
        awayteam = element['awayTeam']['name']
        homescore = element["homeScore"]["current"]
        awayscore = element['awayScore']['current']
        idTeam = element['tournament']["category"]["alpha2"]
        print(leage+"\n"+ hometeam+ " vs " + awayteam)
        print(status,"  ",homescore ,"|", awayscore)
        print()
live()
```
* output:

```console
A-League Men
Brisbane Roar vs Central Coast Mariners
1st half    0 | 0

J.League
Avispa Fukuoka vs FC Tokyo
2nd half    3 | 1

Queensland Premier League 3, South Coast, Women
Mudgeeraba vs Robina City FC
2nd half    0 | 1

Vysshaya Liga Reserve
Dinamo Minsk Reserve vs BATE Borisov Reserve
1st half    0 | 0

2nd League
FC Bavarians vs Tuuliin Tom Tulnuud
2nd half    3 | 1
```


* We define a function to make the data from the JSON file readable. The obtained data of the player scores in this example can then be further processed, as shown in the Concept Arts. There are many other ways to use the obtained data by implementing it in other projects, such as creating an IMDB clone or comparing prices with eBay data. Other applications include graphic representation, calculation and GUI.

### sources ###
[source1](https://realpython.com/beautiful-soup-web-scraper-python/)
[source2](https://github.com/je-suis-tm/web-scraping/blob/master/README.md)
[source3](https://www.youtube.com/@JohnWatsonRooney)

