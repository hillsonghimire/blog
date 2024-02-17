---
title: Spatial Database on Microsoft Azure
date: 2021-05-27 01:00:00 +0545
categories: [Linux/Cloud, PostGIS on Azure]
tags: [Cloud Computing, PostGIS, Remote Database, PostgreSQL, Server, QGIS, Azure]
toc: true
---

Almost every GIS operation is shifting from Conventional GIS application to the Cloud Resources. This provides broad spectrum of services to users across the globe. Any organization can "plug-in" to virtual environments and use the computing resources available as on required basis.

## Why is cloud hosted database required?
There are several advantages of hosting database on cloud. Some points to note are:
- Support for Large Data Volumes
- Scaling
- Performance
- High Availability
- Maintenance
- Concurrent Connections

## Server Creation

![Desktop View]({{ "../assets/img/azure-postgresql-database/azure_services_dashboard.png" | relative_url }})
After logging into the azure dashboard, we can easily navigate to 'Azure Database for PostgreSQL servers' and follow along as:

1. Add
2. Single Server

![Desktop View]({{ "../assets/img/azure-postgresql-database/single_server.png" | relative_url }})

After the process is complete, Azure Database for PostgreSQL servers is created.

![Desktop View]({{ "../assets/img/azure-postgresql-database/azure_server_created.png" | relative_url }})



We can fill up all the requirements according to our needs and then create the server.
After creation the dashboard is loaded as:

![Desktop View]({{ "../assets/img/azure-postgresql-database/server_dashboard_capture.png" | relative_url }})


From the setting Heading, we can select the connection strings and then use these connection strings according to our application needs. The connection string page is as:

![Desktop View]({{ "../assets/img/azure-postgresql-database/connection_strings.png" | relative_url }})


We might also want to modify the connection security parameters. In my case, I modified the firewall setting, to make the server accessible from the clients local machine IP address. This will prevent any unauthorized access to the server from unknown IPs not specified in the firewall rule.


Now, Azure provides you with Cloud Shell, you can either select ‘bash’ or ‘powershell’. I am familiar with bash so that goes to my bucket. We can communicate to our database server using this cloud shell.

![Desktop View]({{ "../assets/img/azure-postgresql-database/azure_cli.png" | relative_url }})


Now, We can log in to the remote PostgreSQL Database Server on the cloud from our device terminal or from the pgAdmin4 interface. But in my case, I am working on spatial datasets and trying to establish database connection to the Database Engine in QGIS Desktop for analysis purposes.

## QGIS and Azure Database for PostgreSQL/PostGIS


Used Dataset: 


1. [Nepal Road Network (main roads) from WFP GeoNode](https://geonode.wfp.org/layers/geonode:npl_trs_roads_osm)

2. Nepal Admin Shapefile


I have data locally on my machine. These dataset can be loaded as postgis object using different techniques pointed below:
- Using shp2pgsql CLI utility
- Using shp2pgsql GUI utility (already discussed)
- Using QGIS DBmanager (easier approach)
- Using ogr2ogr

Among these techniques, I am going to import using “ogr2ogr” command line utility.
"ogr2ogr" is the swiss-army knife when it comes to conversion of GIS data. It is available as part of FW Tools.

The general syntax for conversion is:
```
>> ogr2ogr -f "file_format" destination_data source_data
```

Now, to convert ESRI Shapefile to PostGIS object:
```
>> ogr2ogr.exe -f "PostgreSQL" PG:"dbname=my_database user=postgres" "source_data.shp" -skip-failures
```


[Importing spatial data to PostGIS](https://techcommunity.microsoft.com/t5/azure-database-for-postgresql/importing-spatial-data-to-postgis/ba-p/1255421) by @tjukanov is an amazing resource if you are trying it.

This is what I did to get my file on the remote postgreSQL server.

```
>> ogr2ogr -f "PostgreSQL" PG:"host=gis-resource-server.postgres.database.azure.com dbname=hillson user=hillson@gis-resource-server password=********” shapeFileName.shp 
```

We're hosted by here!

Now, we can easily import these dataset into our QGIS Application through DBManager in QGIS. This part is already explained in my previous [blog](https://hillsonghimire.github.io/blog/posts/raspberrypi-postgis-server-blog/)
![Desktop View]({{ "../assets/img/azure-postgresql-database/connection_data_loading in qgis.png" | relative_url }})


## References

[Quickstart: Create server - Azure portal - Azure Database for PostgreSQL - single server](https://docs.microsoft.com/en-us/azure/postgresql/quickstart-create-server-database-portal)

[Take your spatial data analysis to the next level with PostGIS at Azure PostgreSQL](https://techcommunity.microsoft.com/t5/azure-database-for-postgresql/take-your-spatial-data-analysis-to-the-next-level-with-postgis/ba-p/1124288)

[Hosting a PostGIS Database on AWS](https://www.freygeospatial.com/blog/hosting-postgis-on-aws)

[QGIS + Azure Database for PostgreSQL/PostGIS](https://techcommunity.microsoft.com/t5/azure-database-for-postgresql/qgis-azure-database-for-postgresql-postgis/ba-p/1152249)

