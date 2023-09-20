# ufo_sightings
Analysis of Global UFO Sightings

## Introduction
This project is to clean, analyse, and present findings on UFO Sightings around the world.

## Data
The initial dataset was UFO Sightings from the [2019 Tidy Tuesday Collection](https://github.com/rfordatascience/tidytuesday/blob/master/data/2019/2019-06-25/ufo_sightings.csv). The original
dataset had information about UFO sightings from 1906 to 2014. The features included: 
- Datetime
- City Area
- State
- Country
- UFO Shape
- Encounter Length
- Described Length
- Description of Encounter
- Date Documented
- Latitude
- Longitude<br>

Using Python/Jupyter Notebook I cleaned and carried out some data manipulation creating 
a new [dataset](https://raw.githubusercontent.com/21chubaka/ufo_sightings/main/cleaned_ufo_sightings_non_us_v2.csv).

## Data Manipulation
### Retrieved Countries that were null:
The original dataset had many countries that were null. I was able to retrieve almost all the 
null countries, as the City Area feature had the country also included.
Split Date Time to Month, Day, Year and Time Features:
This would make it easier to graph with these features as individual features.
### Dropped Null Countries/Ocean:
A few sightings were located in the middle of the ocean or in country-less areas, which did 
not easily fit into this specific analysis.
### Consolidated UFO Shapes:
Many of the shapes in the original dataset were extremely similar, resulting in 30 shapes. 
By consolidating the similar shapes, I was able to decrease the shapes to 10 shapes. This 
supported using Tableau10 palette which should be more distinguishable especially for 
those with colour-blindness.
### Excluded US Sightings:
The decision to exclude U.S. sightings had two purposes. The first was to look at sightings 
elsewhere in the world, as U.S. UFO sightings are extensively researched and documented. 
The second was U.S. sightings accounted for more than 70,000 rows, while the rest was 
around 10,000 rows. This made the data imbalanced. Also, the size of the dataset was 
making interactions significantly slow resulting in crashes and the U.S. was overplotted. 
Excluding these rows improved performance of the interactions greatly and avoiding using 
an imbalanced dataset.
### Excluded Countries with less than 10 sightings:
Over the years, countries that only had less than 10 sightings did not really make sense to 
keep. This was especially true as the number of sightings by country I used log to smooth 
out the data.