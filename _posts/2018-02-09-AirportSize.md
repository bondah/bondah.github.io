---
layout: post
title: Airport size comparison
tags: data
---

Recently I flew from Los Angeles (airport: LAX) to visit family in Houston (IAH) and Kansas City (MCI). In both Houston and Kansas City, it seemed like the airports were enormous compared to LAX. There was so much open space! I wanted to compare the size to see if it was just perception or reality.

First I needed to find airport boundaries. Looking at an aerial it is easy to see where the terminals, runways, and tarmac are, but the peripheral area owned/operated by the airport containing various buildings, hangars, and amenities is harder to differentiate based on visuals alone. I started my search on OpenStreetMap. All of my airports of interest had polygon boundaries which I was able to download using Overpass Turbo with the query aeroway=aerodrome.

Next, I did some web searches to see what else was available. California has a statewide airport boundary GIS file available from the State transportation agency [^1]. 
![Los Angeles airport]({{ "/images/LAX.jpg" | absolute_url }})

Texas and Missouri did not appear to have a similar resource. Oddly, most agencies seem to model airports as point files which seems inappropriate for infrastructure with such a large footprint. The City of Houston did have an airport boundary GIS file, but it was obviously inaccurate as part of the north runway wasn't inside the boundary [^2]. Both IAH and MCI are owned by their respective cities, so I did a comparison of city owned parcels to the OSM boundary [^3] [^4]. 
![Houston airport]({{ "/images/IAH.jpg" | absolute_url }})
![Kansas City airport]({{ "/images/MCI.jpg" | absolute_url }})

In both cases, as one would expect, the city owned parcels outside and around the airport proper. Kansas City really has a lot of room to grow around MCI, although I suspect they just bought the parcels cheap and are going to sell them for a profit as the city grows (the airport will never be that big!). I considered editing the OSM data for the purposes of this comparison, but while it may not be perfect, it does consistently cover the runways and terminal buildings.

What did I find? Yes, in general LAX is the smallest footprint. MCI is actually smaller than it seems, but a large part of the feeling of expansiveness comes from the emptiness surrounding it. In the overlay I rotated it so the large runway overlapped the longest LAX runway. IAH has the most runways and they are configured at an angle instead of parallel, so that plays a part in the large footprint.
![Airport compare]({{ "/images/AirportCompare.jpg" | absolute_url }})
All airport boundaries were reprojected to California State Plane Zone V US feet and manually moved so that they overlaped.

[^1]: [CalTrans Airport Boundaries](http://www.dot.ca.gov/hq/tsip/gis/datalibrary/Metadata/Airp_bnd2012.html)

[^2]: [City of Houston GIS Viewer](http://mycity.houstontx.gov/houstonmapviewer/) (airport boundary viewable under Transportation/Airport)

[^3]: [Kansas City Parcels](http://maps.kcmo.org/apps/parcelviewer/)

[^4]: [Houston Parcels](http://pdata.hcad.org/GIS/index.html)
