<h1 style="text-align:center">New York City - Segmentation On Basis Of NightLife</h1>

## Overview

Machine learning allows us to study and analyze the data and reach an inference based on common patterns based on data.

Here we use clustering technique of machine learning to do data segmentation based on nightlife in different neighbourhoods of New York City

This project aims to create computational models capable of identifying patterns across dataset. We leverage the Foursquare location data and machine learning algorithms to identify most active areas of nighlife in New York city neighbourhoods

## Background

Nightlife of a city influences various businesses in a city and has a target audience that is growing very fast . Activities that a city has to offer can vary from lounges to night shows to beach bars to cafes all these sectors contribute to the economy and have various interconnected ecosystems within them . Here we study and organise clusters of neighborhoods based on these nighlife activities to study the patterns in data so we can suggest a hotel chain on where they can open their next hotel


# Problem

Cities are composed of various nighlife activities for local residents and tourists alike. A hotel chain firm is planning to expand their business and opena new hotel in New York. 

Chain is not bothered about the pricing and is focused mostly on nightlife activities in the city since most of their clients are tourists looking for nightlife activities . 

They aproach us to use machine learning to segment various neighbourhoods based on two basic parameters-

a) how many nighlife activities are present in 1km radius of the central location of the neighborhood
b) what are the primary nightlife activities in these neighborhoods

This project aims to quantify and monitor the state of neighborhoods in a major metropolitan city, New York City, and identify clusters of similar Nighlife activity scenes.

# Target Audience
The target audience for this could be anyone who is searching for neighborhood in relation with segmentation on basis of nighlife activity .
this could be used fot reas eastate companies, travellors, tourists , cab services businesses and any other bussiness market that may be effected by the locality and activities based around nighlife in the neighborhood


# Stakeholders

Different parties may be interested in a model that is able to quantify neighborhood similarity based on the types of nightlife available. Such a model would be able to inform renters and home buyers who prefer to live where the nightlife is happening that their next home is properly located. Future nighlife activity start-ups can utilize the model to identify neighborhoods lacking nightlife and ensure they are investing in an area that is not saturated. 

# Methodology

## Data Sources and Usage

There are two datasources used - <br>

a) NYU spatial data repository -  I am using the ‘2014 New York City Neighborhood Names’ dataset hosted by NYU’s Spatial Data Repository as the basis for the neighborhood names and associated location centroids . This data will give us details on neighborhoods and there latitude and longitude which will be used to retrieve data from foursquare api. 

b)Foursquare -‘Places API’: I will be using Foursquare’s ‘Places API’ to acquire data related to ‘venues’ (as defined by Foursquare) categorized to be somehow associated with nightlife.Each Foursquare ‘venue’ is assigned a ‘category’ and each ‘category’ is associated with a particular ‘categoryID’.

### Detailed Usage
from NYU spatial data we get list of neighborhoods and boroughs along with there latitude and longitude. this is used to create a dataframe where our columns are neighborhoods, boroughs  latitude and longitude. not that we we have neighborhoods and there positional coordinateswe can use this to leverage foursquare api.

With foursquare api we get list of venues in a specific radius , we take radius of 1km  and limit the data returned to 50. the foursquare api returns number of paramenters regarding venues in 1km radius of latitudes and longitudes of neighborhoods identified with NYU spatial data . these paramenters include, venue city , venue state, venue category , venue postal code and many more.since we are interested on in nighlife category we filter the data to keep only categories relevant to nightlife
