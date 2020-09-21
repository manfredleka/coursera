# coursera IBM datascience specialization


The business goal of this project is to determine the best area in Montreal where to open a new fashion boutique depending on the existing venues in each area and socio economic data of their population. Any person looking to open a new fashion shop in Montreal could be interested.

The analytic question to be answered is, can we effectively cluster neighborhoods within montreal based on the main venues of each neighborhood, and census data on revenues per neighborhood ?

Methodology
  * Data description :
    *Socio economic data to determine if the surrounding population woud be a good target for the boutique sales (http://www1.journaldemontreal.com/2017/09/salaires/), found on journal de Montreal, giving access to Statistics Canada data I did not find directly there.
    *Google Geocoding data from the google geocoding API to get each neighborhood's coordinates to then feed the foursquare API
    *The geographical data from foursquare to learn about each neighborhood in Montreal, to determine already saturated areas where the competition would be high and the desert ones where it may be better to settle in or to avoid if it's really too desert i don't know yet
+Data collection and cleaning:
++I first cleaned the revenue data, leaving neighborhoods outside of the island of Montreal out
++I used a google API to collect coordinates of each neighborhood listed in the revenue data on the island of Montreal
++I collected venue data from foursquare on each neighborhood using these coordinated to get the 100 top venues
+Data preprocessing:
++I got the number of each type of venue per category per neighborhood, isolated the top 10 for each neighborhood and computed a frequency of appearence of this type of venue within this neighborhood based on the total in Montreal
++I added the number of venue in the neighborhood / number of total venues in Montreal so the later classification gets a sense of how many venues there are in each neighborhood compared to the other
++The revenue data was ok already
+Methodology 1 & Results:I tried clustering the data using kmeans as pre-processed, using the venue categorization of Foursquare, and the elbow method to determine the best number of clusters for the data. I didn't find an elbow
+Methodology 2 & Results : What I did next is I used a macro categorization of the foursquare venue categories to get fewer categories to cluster using k means, and hopefully get an elbow and thus the optimal number of clusters. but it didn't work.
+Discussion: Next step would be to check the venue data, make sure no venue is listed several times as part of different neighborhoods. If not, I would look for alternative clustering methods or just work with: the total number of venue per neighborhood to get a sense of how dynamic it is, the total number of venue related to fashion in the neighborhood, the revenue data of neighboring neighborhoods+neighborhoods, and cluster this to find most dynamic and rich area to open shop
Conclusions: The study is inconclusive regarding the business problem. Regarding the analytical one, it seems k means is not a good fit for this job
