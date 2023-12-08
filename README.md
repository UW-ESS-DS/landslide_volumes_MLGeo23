# Landslide Volumes 

**Project leads:**
* [Daniel Acosta, dacost2@uw.edu, https://github.com/dacost2]
* [Andrea Mattson, andrej23@uw.edu, https://github.com/andreamattson ]

**Project collaborators:**
* [Caleb Lykken, Lykken@uw.edu, https://github.com/Caleb-Lykken]
* [Cody Cruz, openonic@uw.edu, https://github.com/GHOpenonic]

**Project advisor:**
* [Morgan Sanger, sangermd@uw.edu, https://github.com/sangermd]:

**Project GitHub:** 
 https://github.com/UW-ESS-DS/landslide_volumes_MLGeo23

## Scientific Motivation

Landslides pose significant threats to communities and the environment worldwide, causing significant economic losses and numerous annual fatalities (Froude and Petley, 2018; Pollock and Wartman, 2020). They are primarily triggered by precipitation or seismic activity (Wieczorek 2001) and, additionally, in urbanized areas, by anthropogenic alterations to the landscape (Davis et al. 2022). The variation in landslide volumes significantly impacts the magnitude of their destructive potential (Massey et al., 2020). Traditional methods for estimating landslide volumes often rely on manual measurements, which can be time-consuming and less accurate. Our goal is to leverage the potential of machine learning techniques to predict landslide volumes, given a landslide inventory and some environmental variables. We apply our analyses to this project's study area, King County, Washington. 
Data 
We use geospatial data to estimate landslide volumes in King County, Washington. These data include a landslide inventory with different attributes and geological and environmental parameters, such as slope, precipitation, groundwater table, and vegetation coverage, to predict the volume of landslides based on those parameters. Generally, this data was collected by Washington State’s Department of Natural Resources (DNR) and the United States Geological Survey (USGS). For some data, we use in-code-pulling data from the internet that can run on any machine. The entire dataset can be found using the following link:
https://drive.google.com/drive/folders/1GjJyjEVX8_yuP3Zb6uOsLBxQbe0L7Ed3

## Landslide inventory
**Description:**

 DNR provides a map of past landslides. The details for each landslide are polygon shapes indicating the area of displaced and deposited material and the volume of material moved by the landslide.
Data format: Original format in MXD. It was then exported to Shapefile.
Curation process: First assessed in ArcMap to identify all features. Then, we selected “scarp” and “deposits” and exported them as shapefiles. These feature data frames with area and volume information.

* Elevation and Topography:
Slope characteristics indicate the terrain's steepness and help to identify areas prone to landslides based on their incline.

Future analysis could include: 
* Precipitation:
Records of historical precipitation patterns, offering information on rainfall intensity and distribution in the region. Understanding rainfall patterns is crucial, as excessive rainfall often triggers landslides.
* Groundwater table:
Information about the groundwater levels within the area highlights the potential influence of water saturation in soil, a significant factor contributing to landslide susceptibility.
* Vegetation coverage:
Vegetation plays an essential role in stabilizing soil and can impact landslide occurrences; this dataset aids in assessing that relationship.
## ML Method
Our study revolves around leveraging regression models to predict landslide volumes of specific geographical locations to landslides. Our dataset is current only based on topography, though such features as precipitation, groundwater table, and vegetation could be used in the future to bolster our analysis. Our approach to supervised learning involves the deployment of linear regression, lasso regression (employing the L1 norm), and logistic regression (utilizing the L2 norm) as our chosen hyperparameters. A critical consideration in our methodology is the prudent selection of features to mitigate the risk of overfitting. By incorporating only essential features and rigorously cleaning the dataset, we aim to strike a balance that avoids the model memorizing the training data while still maintaining predictive accuracy. This strategic curation of features is fundamental in preventing both underfitting and overfitting, ensuring a robust and reliable model. In our pursuit of optimizing model performance, we turn to grid search methodology. This systematic exploration of hyperparameter combinations allows us to identify the most effective configuration for our models. By systematically fine-tuning these parameters, we seek to enhance the reliability and accuracy of our susceptibility assessments, providing a nuanced understanding of landslide occurrences at the specified locations. Through this comprehensive and strategic approach, we aim to contribute valuable insights to the field of landslide susceptibility assessment.

Model training
Before we begin training our model, data visualization will be used to express the variability of our data to show if there are any outliers. This will also reveal whether there is a trend to our data before it is manipulated. Next, cross-validation will determine the best model to use as our machine learning model. The model that shows accurate measures of landslide volumes, such as where landslides have already occurred, will be used as our machine learning model. Next, hyperparameter tuning is required to prevent overfitting or underfitting our model. We will test several hyperparameters that make sense with the goal of finding an optimal balance that neither overfits or underfits. Our model will efficiently predict our test data but remain generalizable to datasets beyond those of our test and training. Because many parameters are involved, a random search will be implemented by randomly selecting a combination of values.

Results
Classification: We predict that slope and geology will be the most highly correlated of our parameters for landslide susceptibility in King Count. Our resultant landslide susceptibility map for King County will likely be greatly correlated with maps of slope, and geology. With the greatest landslide risk locations associated with the spatial intersection of these two parameters. Susceptibility will be measured on a scale of 1 to 5 and we predict low-susceptibility scores of 1-2 in locations where one or more of these parameters lack traits conducive to landslide initiation. 

Regression: We predict that slope and precipitation will be the most highly correlated of our parameters for landslide volumes in King County. Our resultant landslide volume map for King County will likely be greatly correlated with maps of slope and geology. With the greatest landslide volume output locations associated with the spatial intersection of these two parameters. We predict low-volume outputs in locations where one or more of these parameters lack traits conducive to landslide initiation. 

## Conclusion
We will combine Washington’s DNR landslide maps with other geospatial data such as slope, precipitation, groundwater table, and vegetation coverage. With this the intention is to create either a landslide susceptibility map by using a classification model, or predict landslide volumes using a regression model, for King County, Washington. 

Before manipulating any data or training our model, the raw data will be visually represented to reveal trends and outliers if they exist. Cross validation will imply which model will be the best to use and hyper parameter tuning will prevent under or over-fitting data for training the model. To keep this study accessible and reproducible, we intend to  use in-code-pulling data from the internet that can run on any machine.
Ultimately, we expect to see landslide volume and susceptibility to correlate the most with slope and geology. Our goal for this project is to let it be used for Washington’s DNR data on predicted landslides. 
