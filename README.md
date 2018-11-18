# CaBi-Mapbox-Jupyter
 
## **Business Objective**: 
With the trained time series model of Capital Bikeshare capacity predictions, one can predict the capacity of a given station with some help visualization of current and historic station capacity. The notebooks are avaiable [here.](https://nbviewer.jupyter.org/github/davidpofo/CaBi-Mapbox-Jupyter/blob/master/Notebooks%20and%20Html/mapbox-jupyter.ipynb)
## **Data Ingestion**:
The historic station status data was manually downloaded from capital bikeshare's [data bucket](https://s3.amazonaws.com/capitalbikeshare-data/index.html). From there it was read into and concatenated into one pandas dataframe(343.4+ MB). For the snapshot of bike station statuses I used urllib.request to download and parse the xml into a pandas dataframe. From their the two dataframes were seperatly transformed before combining. Lastly, outage data was downloaded from the Capital bikeshare [outage webpage](http://cabitracker.com/outage_history.php) to later refine the combined dataframe for a time series analysis.
Finally, in the **mapbox-jupyter** notebook I read in the processed data from the analysis notebook and changed the data to geojson for mapping.
## **Visualization**:
1) In the **Bikeshare Status Analysis** notebook I have standard visualizations of station capacity preceeding the various time series plots.
* Percent capcity histogram
* Percent capacity Boxplots
2) While in the **mapbox-jupyter** notebook I have maps of Graduated Circle map of the current bike number avaiable at a station noted by a dot thats radius reflect the total capacity of that station. Additionally, I have a heat map that reflects the average duration of bike trips starting at that station by increasing radius.
## **List of Libraries & Modules**
### **Data Ingestion**:
* os, pandas, numpy,
* urllib, shutil, xml,
* matplotlib, dateutil, statsmodels,
* datetime, sklearn, warnings
### **Visualizations**:
* Matplotlib, Seaborn, Mapbox
