The original data is available at:
https://www.mvg.de/verbindungen/Fahrplandaten.html

It is a part of a General Transit Feed Specification (GTFS) dataset, the format of which is documented here:
https://gtfs.org/documentation/schedule/reference/

Only the tables
* stops
* routes
* trips
* stop_times
* calendar
are included. Other tables are not necessary for the exam. In particular, the shape database is not required. All information on positions and distances is included in stops and stop_times. Likewise, not all columns in all tables are required for the exam. The data has been slightly simplified and modified, compared to the original data.

Some additional comments in relation to the exam:

**Summarized stops/stations**
Some stops are part of larger stops, which is indicated by an assigned parent_station. For the purpose of the exam, summarize all such sub-stations into their parent station and only show parent stations in the plots.

**Summarized routes and route types**
* In the dataset many routes exist in various different "sub-routes", indicated by separate assigned route_id's but given the same value in the column route_short_name. For instance, there are 19 instances of the route "19". These seem to be necessary to handle intricacies in the schedules and variations in the served stops. For questions concerning "how many routes serve a given station", treat the column route_short_name as unique route identifier and only count the number of distinct values of this column.

* Ignore the column route_type. Instead use the column route_desc to classify routes by type of transport. It is not necessary to understand the details between the different bus types. Just treat them as different route types.

**Calendar**
The stop_times table only contains timing information of a trip within a day. On which days a trip is served is handled through the calendar table (and the omitted calendar_dates table). The calendar table has been strongly simplified for this exam.
