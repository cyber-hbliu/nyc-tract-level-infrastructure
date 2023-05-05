# Intro
In capstone, my [projects](https://storymaps.arcgis.com/stories/370a10688d2c4874bdc5ddd57467f6b5) talks about the association between urban infrastructure and women's uncertain public safety in NYC. 
This project is a python script related to capstone project, it finally generates a simple interactive map to visualize various infrastructure features across NYC and provide insights into the tract level distribution of these features.

  

# Identify data:
I collected infrastructure dataset from open data New york city including streetliight conditions, pavement ratings, vacant and unsecure buildings, facilities, subway stations, women's resource network.  But in this case, i am going to merge those data into census data and calculate the amount of each features per tract. I would like to create a function to extract these dataset throught API, it also allows user to get the updating real time data after april 2021.

  

# warehouse, BigQuery
After extracting through APIs, these data will be stored in Google BigQuery, In this case, streetlight and pavement dataset both have nearly 60,000 records. vacant_building dataset has 1431 records, facilities one has 32437 records, women_resources one has 680 records and the subway_stations onehas 473 records.

  

# ELT
I created a dataset in BigQuery then created another function to load these dataset into it for further transformation, like convert format, aggregate features into census data, handlr missing values and calculate the number of each feature per tract.

  

# Visualization
I use dash to develop an Interactive dropdown based on mapbox and plotly to select a feature for visualization. The interface has two parts: one is the choropleth map to examine the number of different features per tract, another is the histogram to indicate the distribution of features. Users can select the feature data to see the distribution. and there is a callback function to update the visualization. Then deploy dash web into [Heroku](https://nyc-tract-level-infrastructure.herokuapp.com/).
