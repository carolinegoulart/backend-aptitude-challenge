# Swat-Intel Backend Aptitude Challenge
Welcome to the SWAT-Intel Aptitude Challenge. You can develop your work as follows:

**Mission:**
Create a supply transport route search REST API.

**Estimated time**
4 Hours

**Premises:**
- The REST API should be written in Java/Kotlin with Spring or C# with .NET Core.
- Database is not necessary.

**What will be evaluated:**
- The code and the quality of your solution.

**You must use the following resources to develop your solution:**
- There is a [CSV from iTrain](iTrain.csv) and a [JSON from UberOnRails](uberOnRails.json) file, each one containing a list of train trips scheduled by the company between 2021/02/10 and 2021/02/18.
- A [JSON of the train stations](trainStations.json) available.
- They are structured as follows:

**iTrain**
| Field | Format
|--|--|
| trip_number | Alphanumeric (6 char length)
| origin_station | Alphanumeric (3 char length)
| destiny_station | Alphanumeric (3 char length)
| date | DATE
| departure_time | TIME
| arrival_time | TIME
| price | decimal

**UberOnRails**
| Field | Format
|--|--|
| trip | Alphanumeric (8 char length)
| origin | Alphanumeric (3 char length)
| destiny | Alphanumeric (3 char length)
| departureDate | DATE
| departure | TIME
| arrival | TIME
| value | decimal

**TrainStations**
| Field | Format
|--|--|
| name | Alphanumeric
| station | Alphanumeric (3 char length)
| city | Alphanumeric

**Challenge A:**
- Provide 1 (one) endpoint that receives two mandatory fields called `Origin station` and `Destiny station`, and a non-mandatory field called `Trip date`, and returns a JSON with all the available routes that match the search criteria. These routes may be composed of one or more trips, and the trips might be managed by different companies (iTrain and/or UberOnRails). For example, a trip from iTrain can connect with a trip from UberOnRails - there is no problem with that.
- The response has to be ordered by both the date and the arrival time.
- Trip connections can be used as long as the interval between the trips is equal to or less than 12 hours.
- The maximum number of trip connections is up to you.

**Challenge B:**
- Provide 1 (one) endpoint that returns a list of all the train stations that completely or partialy match a `Station name` criteria.
- The criteria should not be required, which means the endpoint has to work properly even if the user don't provide any data.
- The criteira matching should not be case sensitive.

**Response example:**

```json
[
	{
		"origin": "GRU",
		"destiny": "LOA",
		"departure": "YYYY-MM-DDTHH:mm:ss.sssZ",
		"arrival": "YYYY-MM-DDTHH:mm:ss.sssZ",
		"steps": [
			{
				"origin": "GRU",
				"destiny": "NYC",
				"departure": "YYYY-MM-DDTHH:mm:ss.sssZ",
				"arrival": "YYYY-MM-DDTHH:mm:ss.sssZ",
				"company": "UberOnRails",
				"price": 1400.00
			},
			{
				"origin": "NYC",
				"destiny": "LOA",
				"departure": "YYYY-MM-DDTHH:mm:ss.sssZ",
				"arrival": "YYYY-MM-DDTHH:mm:ss.sssZ",
				"company": "UberOnRails",
				"price": 350.00
			}
		]
	}
]
```

**Extras:**
Add all the dependencies or resources you think that are necessary in order to develop the best solution for the challenge. You can use the examples below, but don't limitate yourself on it:

- Documentation (Swagger, OpenAPI etc)
- Cache
- Docker
- Tests

**Upload the solution:**
- Your solution should be uploaded on a Github or Bitbucket public repository.
The repository must have:
- The project.
- A README explaining how to run your project.
