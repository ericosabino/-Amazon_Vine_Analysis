# Amazon Vine Analysis

## Overview of the analysis

In this project, a dataset of product reviews will be used to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin.

This first part of the project can be found here: ![AWS Reviews ETL](https://github.com/ericosabino/Amazon_Vine_Analysis/blob/main/Amazon_Reviews_ETL.ipynb)


In the second part of the project, I'll use PySpark to determine if there is any bias toward favorable reviews from Vine members in the dataset.


## Resources

Technologies used:
* Spark
* Google Colab
* Amazon RDS
* Amazon S3
* PostgreSQL

Data used:
* ![Amazon Reviews, US Video Games](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Video_Games_v1_00.tsv.gz)


Mode datasets can be found here: ![Amazon Reviews Index](
https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt)


## Results

1. Recreating the Vine Table:

![](/Images/01_Vine_table.png)

2. Filtering results (total_votes count is great or equal than 20, helpful_votes divided by total_votes is equal to or greater than 50%)

![](/Images/02_Filter.png)

3. DataFrame with paid Wine Reviews:

![](/Images/03_Paid_reviews.png)

4. DataFrame with unpaid Wine Reviews:

![](/Images/03_Unpaid_reviews.png)


5. Bias Analises

![](/Images/04_bias.png)

Final results:

Paid reviews:
- Total # of 5-star paid reviews = 44
- Total # of paid reviews = 90
- Percentage of 5-star reviews on paid reviews = 48.88 (44/90)

Unpaid reviews:
- Total # of 5-star unpaid reviews = 14626
- Total # of unpaid reviews = 37385
- Percentage of 5-star reviews on unpaid reviews = 39.12 (14626/37385)


## Summary

There were approximately 49% of 5-star reviews on paid reviews, against 39% on unpaid reviews. This result indicates that there may be a bias in the data, meaning that Vine paid users may be more inclined to give more positive reviews than unpaid users.

Further analysis may be required though, as there is only 44 paid reviews in total, against 37385 of unpaid reviews.

Additional analysis can be done to support this statement and get more insights. As a next step, I would run this experiment on the same products to validate how different the volume of paid and non-paid reviws is and then create a box plot for each of these groups of users.