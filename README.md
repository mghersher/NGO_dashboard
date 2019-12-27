# NGO_dashboard
This repo contains a dashboard that is designed to monitor incoming surveying results from an education NGO's door-to-door survey (D2D) and compare them to machine learning predictions to help them maximize impact. The NGO finds and renrolls out of school girls (OOSGs) across northern India and is looking to expand their program into 2500 new villages across Madhya Pradesh and Uttar Pradesh. From historic expansion we know that 95% of out of school girls typically live in 50% of villages, but without doing time intensive surveying in every village in northern India it has historically not been possible to identify and target these high priority regions.

To help reach more out of school girls, we have designed a series of machine learning algorithms that predict which villages will have the most OOSG and identifies the optimal clustering of villages for expansion, taking into account the NGO's operational constraints. By targeting the regional hotspots of low school enrollment, the NGO is able to reach 50% more OOSGs without increasing program costs. 

This dashboard is designed to monitor the latest round of expansion in the 2500 villages which we've recommended. Due to limitations in our machine learning training data (ex. administrative data in India from the census is from 2011, our outcome variable excluded ages 5-6, etc.), we expect some predictions to be off and want to closely monitor the incoming results. The purpose of this dashboard is to monitor survey progress and the assumptions/extrapolations we had to make in our predictions and triage which trends are unlikely to improve with more surveying and which are not. We will use this to dentify areas where early adjustments to expansion recommendations could save the NGO time and resources.

The colors used across the dashbaoard are consistent and designed to be intuitive - <font color='green' size = '3'>green</font> highlights positive trends that will help the NGO exceed their 44 OOSG/village target and <font color='red' size = '3'>red</font> highlights concerning trends that could make them fall short.

## Prerequisites
This dashboard was written using the following version of python:
```
python --version
python 3.6.8
```
It has the following dependencies:
```
pandas
geopandas
numpy
math
sqalchemy
datetime
matplotlib
webcolors
maplotlib
webcolors
gmaps
ipywidgets

```
All packages are downloadable on the command line using either conda or pip:
```
conda install package_name
pip install package_name
```

## Functionality
The dashboard is designed to pull in live survey data from a SQL remote database and merge this with locally saved machine learning predctions. It performs a comprehensive set of analyses comparing ground truthed results to predictions, and visualizes the results in a set of intuitive graphs and interactive maps. The dashboard is generated by running the Dashboard.ipynb file. At the very end of this notebook the dashboard is exported to a stable html file (Dashboard.html) with all interactive maps and figures plotted inline. The .html file is openable by all users regardless of whether they have python installed on their computers, making it easy to share with non-technical teams.

To open the dashboard without python installed simply download the .html file and double click on the file to open it in your browser. The interactive maps only open in chrome due to a widget issue. If the .html file does not open, this is likely due to the security settings of the browser.
