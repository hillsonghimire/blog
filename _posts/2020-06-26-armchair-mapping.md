---
title: Remote Mapping My Locality
date: 2020-06-26 01:00:00 +0545
categories: [GIS, OSM]
tags: [Armchair, Mapping, OSM, HOTOSM, JOSM]
toc: true
---

```
"A map is foundational to a person’s being, almost.
If you’re on the map, if your building, street, neighborhood exists, you exist.
And you have a voice."
Mr Kunce, Senior geospatial engineer at Amerian Red Cross
```

Today morning, after long period in covid lockdown, I woke up to realize that the surrounding places in my locality including tracks, new infrastructures and important landmarks like schools aren't mapped in OSM. I installed JOSM and was ready to map my place !

I already have:

>  Internet Connection,
>  OSM user account,
>  JOSM running,
>  And Active internet connection,
>  Cannot forget the optical mouse (recommended)
# Lets catch the background

### What is Armchair Mapping?

On Contrary to *Outdoor Mapping* which relies on on-site data collection from mapping region, the *Armchair Mapping* relies on information collected by other mappers (Street view photos or traces), companies (Aerial imagery), and on our knowledge of the area.

Armchair Mapping (or Remote Mapping) skips surveying phase where user physically visits the place they are mapping. Hence, the workflows will typicall cover a larger area more rapidly, but with the disadvantages in terms of data accuracy, detail, and community binding. The basis of contribution is *Aerial Imagery* or *Other Data Sources*.

### Advantages of Armchair Mappping

Apart from Remote Workflow, Speed Coverage of large areas. Other significate advantages are:

- Safety, No physical visit in dangerous places.
- Access, Some areas doesn't allow physical access. So, mapping via aerial imager is the only option left.
- Disasters, When any area is affected with hazards, remote mapping can help combine collective efforts from remote mappers around the world for faster response or data collection. Humanitarian mapping for disasters, HOT mapping, is often done entirely as an armchair mapping process, with only smaller scale mapping projects acheved by on-site surveys on ground.
- Several features, like roads and buildings, don't change for decades and can be mapped with reasonable confidence.

Also, when comparing with normal mapping wiht GPS, armchair mapping requires no expensive equipments.



### But there are few things to consider,
- although armchair mapping doesn't interfer with existing surveyed data, it might discourage people from doing better better survey-based mapping of area.
- Quantity and Speed is considered over Quality.
- Sometimes the maps are damaged intentionally by bad mappers.


Apart form those notable advantages and disadvantages, there are specific practical problems while mapping form aerial imageries,
- Connecting roads that don't connect.
- Obstructed view by tree canopes, tunnels, clouds, pergolas, and so on.
- Many POIs cannot be mapped. Can't know a shop name from above.
- Hard to map important amenites. Eg. restrooms.
- Mapping private features are also problematic. Some private backyard swimming pools and tennis courts are best left unmapped.
- Imageries may differ between depending on different providers.


Mapathons, coordinated mapping event, held across the globe from different humanitarian or academic institution, and with collaboration with students' clubs are great mapping effort to engage the youths in collective mapping effort and rapid data collection.

Passionate people are the power that drives disaster planning. There are large number of interested volunteers or enthugiastic mappers across the globe who contribute to OSM or data collection through HOT tasking manager, which operates on the critical end of the scale.

Similarly, Missing Maps, founded by HOT, puts vulnerable people on map and accounts from them long before disaster strikes.

# JOSM Workflow
There are several editors for OSM Maps. One that I'm most familiar is JOSM, which has several tools and plugin support.

Modern Workflow includes assisted mapping with AI. RapID from Facebook OSM Community is AI assisted mapping ID. Such assisted  and semi-automated mapping makes the workflow even more rapid.

NOTE: JOSM requires to have Java Runtime Environment(JRE)

![Desktop View]({{ "../assets/img/osm/josm_armchair.jpg" | relative_url }})

1. Authorization of user thought preferences
2. Download required plugin: One on my list is *building* plugin
3. Download Data from file>download data select Bounding Box for data downloading
4. Select desired imagery from Imagery options.
5. Add missing features from different available toolsets Eg. Buildings, Streets etc.
6. Upload added features

So, I've added the missing features on the OpenStreet Map(OSM).