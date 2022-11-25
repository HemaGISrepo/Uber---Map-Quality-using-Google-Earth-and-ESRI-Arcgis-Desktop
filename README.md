# Uber---Map-Quality-using-Google-Earth-and-ESRI-Arcgis-Desktop

Requirements of Uber’s map quality computation system:

Accuracy: the results must be accurate
Reliability: the results must be repeatable and accessible
Scalability: supporting metrics computation of both a single region and the world
Robustness: the failure of metrics computation for one map region must not affect the computation of other regions


Ensuring map quality:

Uber uses map data from a variety of third-party map providers, with a goal to enable a great Uber experience to our users. To ensure high quality or these maps, we utilize an iterative process of analyzing map data, identifying map defects, and fixing them. This creates a positive feedback loop for improving the maps. Here are some examples of that:

1. Trace coverage: 

A comparative coverage metric, trace coverage identifies missing road segments or incorrect road geometry. The computation uses two inputs: map data under testing and historic GPS traces of all Uber rides taken over a certain period of time. We overlay those GPS traces onto the map, comparing and matching them with road segments. If we find GPS traces where no road is shown, we can infer that our map is missing a road segment and take steps to fix the deficiency.  

![image](https://user-images.githubusercontent.com/118595650/204043156-f06809e8-9919-44d2-b6c5-ad478bcd8393.png)

2. Routing evaluation: 

Another critical metric of map quality, evaluating routes lets us identify incorrect turn restrictions and road directionality on our maps. Here, we compare the routes our navigation algorithm suggests for drivers with the actual routes they choose to take. If there is a sustained discrepancy between the suggested and actual routes, we investigate for potential map defects. Image, below, shows an example of a large discrepancy between the suggested and actual routes. Our consequent comparison revealed incorrectly modeled turn restrictions on road segments that made it impossible to use the suggested route.

![image](https://user-images.githubusercontent.com/118595650/204043227-7a942e89-2bca-4e26-a531-a08271a983b2.png)


3. Preferred access (pick-up) point accuracy: 

Pick-up points are an extremely important metric to the rider experience, especially at large venues such as airports and stadiums. For this metric, we compute the distance of an address or place’s location, as shown by the map pin in the image, below, from all actual pick-up and drop-off points used by drivers. We then set the closest actual location to be the preferred access point for the said location pin. When a rider requests the location indicated by the map pin, the map guides the driver to the preferred access point. We continually compute this metric with the latest actual pick-up and drop-off locations to ensure freshness and accuracy of the suggested preferred access points.

![image](https://user-images.githubusercontent.com/118595650/204043277-01892b8d-f389-4cd4-b8a8-3d9d699e7fc9.png)


Computing quality map :

The below image will be the final outcome

![image](https://user-images.githubusercontent.com/118595650/204043584-a1762fc4-ae08-4af6-aecf-5de5b37ed082.png)


