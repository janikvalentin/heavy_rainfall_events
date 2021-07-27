### Project Motivation 

On July 14th 2021, the amount of precipitation exceeded 100 liters per m² in one day in parts of North Rhine-Westphalia and Rhineland-Palatinate. 
The consequences were more than 100 people losing their lives to the floods and billions of euros in material damage. This project seeks to explore if there is 
an increase in occurrence and intensity of heavy rainfall events in Germany. 

Data covering the recordings of 1,084 weather stations across Germany is gathered
from the German Meteorological Service. The result is a datasetset containing more than 16.5 million observations in the time period 1900-2020. 

<br/>

### Findings

Despite the high variance of annual events, there has been no significant increase in heavy rain events in Germany so far. 
While the average intensity has also remained constant over the last 100 years, 
there have been peaks in several years this century, and it remains to be seen whether 
this trend will continue.
The analysis of regional differences revealed Bavaria and Baden-Wuerttemberg as the states most often affected by heavy rain events, 
with weather stations in close proximity to mountain ranges showing higher than average counts. Most events occur in the summer months from June to August.

To give you an impression of the kind of visualizations used, here is the plot for the development of occurrences of heavy rain events in Germany:

![hr_by_year](https://user-images.githubusercontent.com/43187331/127239288-6ce04a1e-4742-4418-94c4-518be3736f92.jpg)
Data basis: Deutscher Wetterdienst, averaged over individual values


And here a graph that visualizes heavy rainfall events by weather station in Germany:

![hr_by_station](https://user-images.githubusercontent.com/43187331/127239317-8de9d6ae-3e00-4f76-b24b-225e60940fff.jpg)
Data basis: Deutscher Wetterdienst, averaged over individual values


I also wrote a blog post on Medium that covers the findings of this project. You can read it [here](https://medium.com/@janikvalentin1/are-heavy-rainfall-events-increasing-in-frequency-in-germany-2129b5d9d448).  

<br/>

### File Descriptions

``scraper.ipynb`` 

This python script is responsible for downloading the data from the German Meteorological Service and saving the files in the data/ folder. 
Note that the script will download all files that are included in the zip compressed folder. But only files in the format 'produkt_klima_tag_[date]_[date]_[weather_station_id].txt'
are required for this project. All other files were manually deleted. 

``Extreme_weather_phenomena.ipynb``

This is the main file of this project were the dataset is analysed and all statistics are calculated

``data/`` 

This folder contains all data for all German weather stations used for this project.

``geodata/`` 

This folder contains data about the location of each weather station as well as shapefiles for plotting with geopandas.

``plots/`` 

Created plots are saved in this folder

``requirements.txt``

This file lists all packages I have installed to run this project.

If you want to recreate this project in a new environment on your pc, you could run:

*conda create -n your_new_environment_name --file requirements.txt*

However, the only packages that are not part of the basic conda installation are geopandas and seaborn. If you have a conda installation, you could therfore also just run

*conda install geopandas, seaborn*

and should be good to go. 

<br/>

### Acknowledgements

This Project would not have been possible without the publicly available data from the German Meteorological Service (Deutscher Wetterdienst). You can check out all of their open datasets [here](https://cdc.dwd.de/portal/).
