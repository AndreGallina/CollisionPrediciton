# Predicting Risk of Injury from Traffic Collisions
### Abstract
With traffic congestion costing the United States in excess of a hundred billion dollars a year and pollution levels rising by eight percent over the course of the past five years, cities need to adapt fast. Moreover, improving traffic safety and decreasing the number of people killed and injured is essential.

Key to addressing the above is understanding the reason behind vehicle collisions in big cities. This could help increase safety, diminish traffic jams and save money. Moreover, identifying where these accidents happen, when they are likely to happen and what shared common characteristics of these accidents is essential to achieve that goal.
The main objective of this project is to answer two essential questions:
    - Predict whether or not someone is injured in a collision;
    - Predict  the number of people injured in a collision  given a geographic location.

### Data Source
The NYPD Motor Vehicle Collisions dataset is a record of all motor vehicle collisions in NYC. It captures the location, incidence of injury or fatality, vehicle type involved and contributing factors in a collision. Weather data has also been included in order to enhance the solution.

### Exploratory Analysis
As a first step to answering these questions, an exploratory analysis was performed. Understanding which dimensions are important, recognizing trends, and possible problems with data becomes necessary. For that, some graphs were plotted:

<p align="center">
  <img src="/results/inju_seaso.png" align="center" width="450" height="600">
</p>

<p align="center">
  <img src="/results/injuries_hour.png" align="center" width="800" height="400">
</p>

<p align="center">
  <img src="/results/coll_fact.png" align="center" width="800" height="300">
</p>

<p align="center">
  <img src="/results/vehc_typ.png" align="center" width="800" height="300">
</p>
<p align="center">
  <img src="/results/inju_seas_typ.png" align="center" width="600" height="300">
</p>


### Data Cleaning
After a quick exploratory analysis, the dataset required cleaning, formatting, and the elimination of redundant dimensions and useless data.
The first measure in the data cleaning was to delimit the geographic area of the analysis. As the predictions were executed in NYC, longitudes and latitudes outside the city limits were removed.
Another measure taken was the grouping of categorical data poorly represented (less than 5% of the total). These were grouped into a new subfield called 'others'.
Due to the fact that the deaths in accidents in the case studied are totally random, the number of deceased was added to the number of people injured, thus creating a new column called "TOTAL".

### Preprocess phase

After the preprocess phase, the dataset needs to undergo a feature engineering process. To encode the categorical data it dummy variables were used which increased the number of dimensions to more than 1600.
Furthermore, because the analysis is extremely unbalanced it was necessary to sample the number of accidents with injured people in the training set.





### Analyses


The first part of the solution represented a classification problem, as a result we used the Random Forest model.  Random Forest is an ensemble learning method for classification which operates by constructing a multitude of decision trees at training time and outputting the class that is the mode of the classes of the individual tree.

<p align="center">
  <img src="/results/randofore.jpg" align="center" width="600" height="300">
</p>


For the second part, a Neural Network was used combined with a layer using Radial Basis function to deal with geographic data and fully connected layers (dense) to handle the rest of the data.

<p align="center">
  <img src="/results/nn.jpg" align="center" width="400" height="300">
</p>



### Results
As a result of the first question "Predict whether or not someone is injured in a collision", two graphs were created, one of the ROC curve and another of confusion matrix.

<p align="center">
  <img src="/results/confmatrix.png" align="center" width="400" height="300">
</p>

<p align="center">
  <img src="/results/roc.png" align="center" width="400" height="300">
</p>



The prediction of the number of people injured in an accident was plotted as a layer in the Google Maps API as a heat map.

![Sat map](/results/gpsmap.jpg)






![Sat map](/results/satmap.jpg)






