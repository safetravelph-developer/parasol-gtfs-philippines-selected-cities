# parasol-gtfs-philippines-selected-cities
The PARASOL system builds GTFS Static files of the public transport services and routes of selected cities, where the SafeTravelPH NGO team and partners had deployments. Local government and LTFRB and other national government agencies can collaborate with us to build and publish on Google Maps these important local public transport system information. 

These are NOT OFFICIAL GTFS files of these cities.

Using the SafeTravelPH app and Parasol tools/programs, we identified the realtime tracks, travel/stopping times and distances, and stopping patterns. Then, we use AddTransit.com to easily validate syntactically the generated GTFS files.

## Option for Editing, Visualizing, and Analyzing the GTFS Files
The GTFS Static files in this repository can be opened, edited, visualized, and analyzed directly in your browser using GTFS·X — a free, no-signup GTFS editor and transit service planner. This is useful for reviewing the routes and trips we've built, correcting stop or schedule data, and exploring the service coverage before publishing.

Getting started:

1. Open GTFS·X at https://www.gtfsx.com/ — no account is required to start editing.

2. Import a feed from this repo. Download the GTFS .zip for the city you want to work with from this repository (or clone the repo and locate the relevant feed folder), then use GTFS·X's import option to load the existing feed. You can also start from a blank map if you're building something new.

3. Visualize the network. Routes, stops, trips, and schedules are displayed on a live map, so you can immediately see how the stopping patterns and travel times we collected translate into the published service.

4. Edit and validate. Make changes to routes, stops, trips, and schedules, and GTFS·X will validate against the GTFS spec as you work — catching errors before export rather than after publishing.

5. Analyze the service. GTFS·X's planning tools compute operating cost, demographic coverage, Title VI equity, stop spacing, and scenario comparisons straight from the feed — handy for sanity-checking a locality's dataset or preparing a board memo / grant narrative.

6. Export. When you're done, export a spec-clean GTFS .zip (or GeoJSON) and either host it anywhere or share it back with the SafeTravelPH team for review.

If you are an public transport agency or operator, or a local government unit, feel free to reach out to us to collect routes and trips data, and co-create and validate your locality's GTFS datasets. You can email us at developer@safetravel.ph.

## Philippine Fares (Unofficial Extension)

The ph_fares.txt file in this repository is an unofficial, community-maintained extension and is not part of the official GTFS specification or endorsed by the GTFS maintainers. Standard GTFS fare files (fare_attributes.txt, fare_rules.txt and the Fares v2 tables) can't represent how Philippine fares actually work, such as base fares covering a minimum distance (4 km for non-bus modes, 5 km for buses) with per-km charges beyond it, LGU-set tricycle rates, metered taxi fares with flag-down and time components, and TNVS pricing with per-km, per-minute and surge components. 

This file therefore uses a custom schema with added fields like fare_model, base_distance_km, per_minute_rate and surge_multiplier_max, so consumers should treat it as a supplementary reference and not as an interoperable GTFS feed. 

We aim to keep the rates current by updating them whenever the LTFRB publishes new fare orders, but rows marked illustrative in data_status have not yet been verified against an official source, and the LTFRB's published issuances always take precedence over this dataset. 

App developers are welcome to use this file in their own fare estimators, trip planners and other commuter tools as our contribution to the Philippine transit community, with the understanding that they should check rates against official LTFRB sources before showing them to end users. 

Please open an issue or pull request, ideally with a link to the relevant LTFRB memorandum circular or fare order, if you spot an outdated or incorrect value.
