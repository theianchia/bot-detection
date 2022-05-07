<div id="top"></div>

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <h2>Facebook Recruiting IV: Human or Robot?</h2>
  <p>Predict if an online bid is made by a machine or a human</p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

### File Description
* `train.csv` the training set from the bidder dataset
* `test.csv` the test set from the bidder dataset
* `sampleSubmission.csv` a sample submission file in the correct format
* `bids.csv` the bid dataset

<p align="right">(<a href="#top">back to top</a>)</p>

### Data Description
* There are two datasets in this competition. One is a bidder dataset that includes a list of bidder information, including their id, payment account, and address. The other is a bid dataset that includes 7.6 million bids on different auctions. The bids in this dataset are all made by mobile devices.
* The online auction platform has a fixed increment of dollar amount for each bid, so it doesn't include an amount for each bid. You are welcome to learn the bidding behavior from the time of the bids, the auction, or the device. 

<p align="right">(<a href="#top">back to top</a>)</p>

### Data Fields
For the bidder dataset
* `bidder_id` Unique identifier of a bidder.
* `payment_account` Payment account associated with a bidder. These are obfuscated to protect privacy. 
* `address` Mailing address of a bidder. These are obfuscated to protect privacy. 
* `outcome` Label of a bidder indicating whether or not it is a robot. Value 1.0 indicates a robot, where value 0.0 indicates human. 

For the bid dataset
* `bid_id` Unique id for this bid
* `bidder_id` Unique identifier of a bidder (same as the bidder_id used in train.csv and test.csv)
* `auction` Unique identifier of an auction
* `merchandise` The category of the auction site campaign, which means the bidder might come to this site by way of searching for "home goods" but ended up bidding for "sporting goods" - and that leads to this field being "home goods". This categorical field could be a search term, or online advertisement. 
* `device` Phone model of a visitor
* `time` Time that the bid is made (transformed to protect privacy).
* `country` The country that the IP belongs to
* `ip` IP address of a bidder (obfuscated to protect privacy).
* `url` URL where the bidder was referred from (obfuscated to protect privacy). 

<p align="right">(<a href="#top">back to top</a>)</p>

### Scoring
* Scored on AUC which is the area under an ROC (Receiver Operating Characteristics) curve; aggregates the performance of the model at all threshold values

<p align="right">(<a href="#top">back to top</a>)</p>

## Exploratory Data Analysis

### Correlation Matrix
* measure of the linear relationship between 2 or more variables

<p align="right">(<a href="#top">back to top</a>)</p>

### Fisher's Score
* find a subset of features, such that in the data space spanned by the selected features, the distances between data points in different classes are as large as possible, while the distances between data points in the same class are as small as possible

<p align="right">(<a href="#top">back to top</a>)</p>


## Model Development

### Models Used
Used an ensemble of 
* Random Forest Classifier
* CatBoost Classifier
* Gradient Boosting Classifier

Performed hyperparameter tuning using GridSearchCV, and model training using k-FoldCV

<p align="right">(<a href="#top">back to top</a>)</p>
