Map-Quality-using-Google-Earth-and-ESRI-Arcgis-Desktop

Requirements of map quality computation system:

Accuracy: the results must be accurate
Reliability: the results must be repeatable and accessible
Scalability: supporting metrics computation of both a single region and the world
Robustness: the failure of metrics computation for one map region must not affect the computation of other regions


Ensuring map quality:
Using map data from a variety of third-party map providers, with a goal to enable a great experience for public transit users. To ensure high quality of these maps, we utilize an iterative process of analyzing map data, identifying map defects, and fixing them. This creates a positive feedback loop for improving the maps. Here are some examples of that:

1. Trace coverage: 

Using GTFS data, trace coverage helps identify missing road segments or incorrect road geometry for transit routes. The computation uses two inputs: map data under testing and historic GPS traces of all public transit vehicles (such as buses and subways) taken over a certain period of time. We overlay those GPS traces onto the map, comparing and matching them with road segments and public transit routes. If we find GPS traces where no road or route is shown, we can infer that our map is missing a road segment or transit route and take steps to fix the deficiency.

Example: In a city, GPS traces from bus routes show a segment where no road is mapped. By analyzing these traces, we discover a newly constructed road that hasn't been updated in the map data. We update the map to include this new road segment, ensuring accurate navigation and routing for public transit users. 

![image](https://user-images.githubusercontent.com/118595650/204043156-f06809e8-9919-44d2-b6c5-ad478bcd8393.png)

2. Routing evaluation: 

Another critical metric of map quality, evaluating routes lets us identify incorrect turn restrictions and road directionality on our maps. Here, we compare the routes our navigation algorithm suggests for public transit vehicles with the actual routes they take. If there is a sustained discrepancy between the suggested and actual routes, we investigate for potential map defects.

Example: A subway route suggests a path that is significantly different from the actual route taken by trains. By investigating this discrepancy, we find that the map data incorrectly models the track layout. We correct the track information in the map, ensuring accurate routing for subway users.

![image](https://user-images.githubusercontent.com/118595650/204043227-7a942e89-2bca-4e26-a531-a08271a983b2.png)


3. Preferred access (pick-up) point accuracy: 

Stops and stations are critical to the public transit experience, especially at large venues such as airports and stadiums. For this metric, we compute the distance of a stop or station’s location, as shown by the map pin, from all actual stop and station points used by public transit vehicles. We then set the closest actual location to be the accurate stop or station point for the said location pin. When a rider requests a location indicated by the map pin, the map guides them to the accurate stop or station. We continually compute this metric with the latest actual stop and station locations to ensure freshness and accuracy.

Example: A bus stop near a stadium is frequently used, but the map pin indicates a location 50 meters away from the actual stop. By analyzing data from bus arrivals and departures, we update the map pin to the precise location of the stop, improving the rider experience by providing accurate stop information.

![image](https://user-images.githubusercontent.com/118595650/204043277-01892b8d-f389-4cd4-b8a8-3d9d699e7fc9.png)

Incorporating factors such as traffic congestion, climatic changes, urban economy, population, stops, routes, shapes, trips, calendar, calendar dates, frequencies, buses, and subways ensures comprehensive and high-quality maps for public transit analysis and planning. This holistic approach helps in better understanding and managing the public transit system, leading to an improved user experience and more efficient transit operations.

Computing quality map :

The below image will be the final outcome

![image](https://user-images.githubusercontent.com/118595650/204043584-a1762fc4-ae08-4af6-aecf-5de5b37ed082.png)


