# Busradar Münster

Scraping Münster's public transport data 

![Fabian318, CC BY-SA 3.0  via Wikimedia Commons](https://upload.wikimedia.org/wikipedia/commons/a/ad/IMG_5025_M%C3%BCnster_Hbf_SWMS_1015.jpg)*Fabian318, CC BY-SA 3.0  via Wikimedia Commons*


# Scraper

busradar_v2.py is a simple scraper that scrapes the data from https://api.busradar.conterra.de/ 

You can run it e.g. on Github Actions on a regular basis 

# Raw Data

You can find the scraped raw data (every 2 mins bewtween 2021-10-27 and 2022-03-02) here: https://github.com/CHesseling/busradar/blob/main/data/busradar_raw.csv.gz (CSV gzipped, 70.5 MB)

Data scraped from Stadtwerke Münster/Conterra. More info on meta data etc. here: https://opendata.stadt-muenster.de/dataset/%C3%B6pnv-busradar-bus-live-positionsdaten 

Please attribute the source (Stadtwerke Münster GmbH) and please let me know if you build something upon this (info@claushesseling.de).

Please make sure to check the Terms of Use of the raw feed:
"The user is allowed to use the data from the GTFS feed for his own purposes. purposes. The user is further entitled to make this data available to third parties, provided that this service is free of charge for the third party and is not for commercial the user and/or the third party. The user is expressly forbidden to use the raw data from the
from the GTFS Feed or to use it for profit-making purposes.
The User shall also oblige the third party to comply with these Terms of Use." (translated with www.deepl.com - full document here: https://web.archive.org/web/20211213162533/https://www.stadtwerke-muenster.de/fileadmin/stwms/busverkehr/kundencenter/dokumente/GTFS/Allgemeine_Nutzungsbedingungen_SWMS_GTFS_Feeds.pdf)

## Columns

|column name   |dtype   |meaning   |
|---|---|---|
|properties.linienid   |int   |bus line - more info https://netzplan-muenster.de/ |
|properties.richtungsid   |int   |direction   |
|properties.akthst   |int   |ID of current bus stop      |
|properties.delay   |int   |Delay in Seconds   |
|properties.nachhst   |float   |Next stop   |
|properties.richtungstext   |str   |Direction text   |
|properties.betriebstag   |str   |Day of Service   |
|properties.starthst   |float   |Service starts at   |
|properties.sequenz   |int   |Sequence   |
|properties.linientext   |str   |Text of direction   |
|properties.fahrzeugid   |int   |ID of vehicle   |
|properties.abfahrtstart   |float - unixtime   |Starttime of ride   |
|properties.fahrtbezeichner   |str   |ID of journey   |
|properties.fahrtstatus   |str   |Status   |
|properties.ankunftziel   |float - unixtime  |Endtime of ride   |
|properties.visfahrplanlagezst   |int   |   |
|properties.zielhst   |float   |ID of final bus stop   |
|geometry.coordinates   |list   |current coordinates - EPSG 4236   |
|xkoord   |float   |Xkoord - EPSG 4236   |
|ykoord   |float   |Ykoord - EPSG 4236   |


