<div class="lead">
    <div class="col-md-9 col-md-offset-1">
    <h1 >The Nutritional Peril:</h1>

      <p class="lead">Every year, millions of individuals across the globe suffer from non-communicable diseases. Non-communicable disease are not contagious, rather they develop through your lifestyle choices including dietary intake. There has been past contradictory research on nutrition. According to the <a href="http://www.nytimes.com/2016/08/11/upshot/were-so-confused-the-problems-with-food-and-exercise-studies.html"> New York Times</a>, the same ingredient could be interpreted as starving away cancer or aiding its onset, depending on who you ask. Only two facts are known: holding all exogenous variables constant, consuming more calories will cause weight gain while exercising will produce weight loss. For this project, we chose to apply a data science approach to the former, nutrition, to ask if with enough information, can we can identify trends between food consumption and disease onset rates?  </p>

    </div>
  </div>

  <div class="row">
    <div class="col-md-9 col-md-offset-1">
      <h3 class="page-header">Project Goal </h3>
    </div>
  </div>


  <div class="col-md-9 col-md-offset-1">
    <div>
      <p>We want to better understand the impact of select food groups and their correlation to the mortality rates of cancer, diabetes, and cardiovascular disease. Our goal is to apply machine learning techniques to read into the datasets and generate predictions of mortality rate.  </p>
    </div>
  </div>

  <div class="row">
    <div class="col-md-9 col-md-offset-1">
      <h3 class="page-header">Data Sources</h3>
    </div>
  </div>

  <div class="row">
    <div class="col-md-9 col-md-offset-1">
          <img src="http://i.imgur.com/Uppy7Hi.png" width = 300>
      <p>Food Data stems from FAOSTAT, the Food and Agriculture Organization of the UN. There are <a href="http://www.fao.org/faostat/en/#data/CC">74 crop predictors</a> and <a href="http://www.fao.org/faostat/en/#data/CL">27 livestock predictors</a>. Food data was measured in kg/capita/year to standardize measurements across different country populations and average over annual time frames. Disease data was obtained from the <a href="http://apps.who.int/gho/data/node.main.A859?lang=en">WHO</a>, World Health Organization. We tested three non-communicable diseases: cancer, diabetes, and cardiovascular disease. The obtain datasets stored values in terms of mortality rates per 100,000, again controlling for country size to isolate the impact of nutrition as a predictor across the globe. </p>
    </div>
  </div>

  <div class="row">
    <div class="col-md-9 col-md-offset-1">
      <h3 class="page-header">Data Exploration</h3>
    </div>
  </div>

  <div class="row">
    <div class="col-md-9 col-md-offset-1">
      <p>Data exploration was first performed on the dataset to understand general trends between the predictors and disease mortality rates. The predictors were sorted by R squared values to find the most informative food predictors. From the graph below, we observe that wheats and products appear to have the strongest correlation to cancer mortality rate, with an individual R squared of around 0.18. While these individual R squared values are low, when dozens of predictors are combined in a multivariate model, their impact can compound to provide more accurate predictions. The data exploration and analysis chapter will explore these predictors in further detail and across all three disease categories. 
      <br><img src="http://i.imgur.com/TNHHgx3.png" width=400px>
      </p>
    </div>
  </div>

  <div class="row">
    <div class="col-md-9 col-md-offset-1">
      <h3 class="page-header">Data Cleaning</h3>
    </div>
  </div>

  <div class="row">
    <div class="col-md-9 col-md-offset-1">
      <p>One of the most significant difficulties was cleaning the data for analysis. Almost 25% of the values were missing as shown in the below visualization for the top 45 most incomplete livestock and crop data where a white bar indicates missing data and a black bar indicates the presence of a value. Extensive code was written to populate missing values with a regional average. For example, missing values for Cuba were filled with the average of all Central America countries. We hypothesize that averaging over geographically nearby countries would be the most accurate because certain foods may be more prevalant across a region. </p>
    <img src="http://i.imgur.com/tnKZpuj.png">
    </div>
  </div>

  <div class="row">
    <div class="col-md-9 col-md-offset-1">
      <h3 class="page-header">Data Science Models</h3>
    </div>
  </div>

  <div class="row">
    <div class="col-md-9 col-md-offset-1">
      <p>Four different models were tested:      </p>
      <ol>
          <li> Naive Linear Regression Model</li>
          <li> Linear Regression with LASSO for Variable Selection </li>
          <li> Linear Regression with Ridge for Variable Selection </li>
          <li> Regression Tree for Advanced Analysis </li>
       </ol>
    </div>
  </div>

  <div class="row">
    <div class="col-md-9 col-md-offset-1">
      <h3 class="page-header">Predictor Impact</h3>
    </div>
  </div>

  <div class="row">
    <div class="col-md-9 col-md-offset-1">
      <p>To visualize the impact of certain food predictors, a bubble chart was generated with the radius of the circle porportional to the size of the coefficient used in the linear regression prediction model. The red and blue colors correspond respectively to positive and negative coefficients.  From the data below for diabetes mortality rates, there is a strong mix of predictors that influence disease mortality in both directions. 
      <img src="http://i.imgur.com/NzeMTU5.png" width="300">
      </p>
    </div>
  </div>

  <div class="row">
    <div class="col-md-9 col-md-offset-1">
      <h3 class="page-header">Predicted Cancer Rates</h3>
    </div>
  </div>

  <div class="row">
    <div class="col-md-9 col-md-offset-1">
      <p>The predicted disease mortality rates from our model were then visualized in a world map format to examine for geographic trends. The above graph shows estimated cardiovascular disease mortality per 100,000 individuals while the below map shows the actual cardiovascular disease mortality rates. A dark blue indicates a higher mortality rate while a lighter blue indicates that the disease is not as prevelant in the country. There are clear similiaries between the models, supporting the validity of our approaches. However there are also noticeable differences that suggest that the nuances of the country were oversimplified in the model. </p>
      <img src="http://i.imgur.com/4qmNdje.png">
      <img src="http://i.imgur.com/tzGEHNZ.png">
      </div>
    </div>

  <div class="row">
    <div class="col-md-9 col-md-offset-1">
      <h3 class="page-header">Conclusion</h3>
    </div>
  </div>

  <div class="row">
    <div class="col-md-9 col-md-offset-1">
      <p>The goal of this project was to better understand the impact certain food predictors have. While we understand that health is a hollistic outcome dependent on many variables in addition to diet such as exercise, a country's GDP, healthcare access, the consumption of certain food groups appears to be more strongly correlated than others. In particular, starches including potatoes, rice, and wheat should be limited as they are positively linked with cancer, diabetes, and cardiovascular disease incidence rates across the world. The goal of this project was to be informative and utilize a machine learning approach to understanding global health. We hope that you find our full report informative and successful in completing this goal. </p>
    </div>
  </div>
