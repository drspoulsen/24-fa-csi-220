# October 28 (Thanks Kyle Wilson for the Lesson Plan Outline)

I have provided a sample csv file on Canvas with some earthquak data pulled from the USGS. Our goal is to do an exploratory data analysis.

Some potential questions:

* Have you seen anything that seems like it should have a story behind it? For example, why does it seem like magnitude 3 earthquakes are so much less common than ones a little stronger, or a little weaker?
* Are there any obvious patterns between strength and depth? What about with other numerical variables?
* Are there certain parts of the world with more earthquakes than others? How could you measure that?
* There's a lot more data than just location, time, and magnitude. What do these other fields mean? Do they connect to magnitude in any interesting ways?
* What's up with all of the "nuclear explosion" records?

If you want to alter which years are included in the dataset, you can modify the following code which does an API request to get the data:

`import requests`
`from io import StringIO`
`import pandas as pd`

`def getYearData(years):`

    #Download earthquake data for the given years. years may be a range object. Return a dataframe.

    url = 'https://earthquake.usgs.gov/fdsnws/event/1/query'
    
    dfs = []
    for year in years:
        for month in range(1, 13):
            
            print("Downloading data for ... {0:02d}/{1:04d}".format(month, year))

            # high-level options
            parameters = {
                'format' : 'csv',
                'minmagnitude' : 3.0,
                'starttime' : '{0:04d}-{1:02d}-01'.format(year, month),
                'endtime' : '{0:04d}-{1:02d}-01'.format(year + (month // 12), (month % 12 + 1))
            }

            # option: searching in a rectangular area (units are degrees WGS84)
            rectangle_params = {
                'minlatitude'  : -90,
                'maxlatitude'  :  50,
                'minlongitude' : -10,
                'maxlongitude' :  10
            }

            # stuff the rectangle search parameters into the other options (dictionary update)
            # (comment the following line out to turn off rectangle filter)
            #parameters.update(rectangle_params) 

            # go out to the web and send the request
            r = requests.get(url, params=parameters)
            r.raise_for_status() # throw an error if the request failed

            # read the data
            filebuf = StringIO(r.text)
            dfs.append(pd.read_csv(filebuf))

    df = pd.concat(dfs, ignore_index=True)
    return df

`df = getYearData(range(2000, 2004))`
`print(len(df))`
