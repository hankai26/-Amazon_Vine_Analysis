# Amazon_Vine_Analysis

# Overview
Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review. This project is to analyze Amazon reviews for toys written by members of the paid and unpaid Amazon Vine program. PySpark was used to to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, we used PySpark to determine if there is any positive bias toward favorable reviews from Vine members in the dataset. Besides, further analysis was performed to examine if negative bias also for the Vine program.


# Results
We create an AWS RDS database (amazonreviewsetl) with tables in pgAdmin. The toy dataset is selected and extracted into a DataFrame. We transform the DataFrame into four separate DataFrames, customers_table, products_table, review_id_table and vine_table. Then transformed data and tables are uploaded. 

We first filter the Vine_table to extract all review information with 20 or more votes and 50% or more helpful votes among them. Based on the Vine review data in the transformed Vine_table, we have those results as followings.

The samples of summary table for Vine reviews and non-Vine reviews are listed as below.
![complete_vine](https://github.com/hankai26/Amazon_Vine_Analysis/blob/main/images/complete_vine.png)
![complete_nonVine](https://github.com/hankai26/Amazon_Vine_Analysis/blob/main/images/complete_nonVine.png)

- Total Vine reviews and non-Vine reviews
![total_vine](https://github.com/hankai26/Amazon_Vine_Analysis/blob/main/images/total_vine.png)
![total_nonVine](https://github.com/hankai26/Amazon_Vine_Analysis/blob/main/images/total_nonVine.png)

- Five-Star Vine reviews and non-Vine reviews
There're 432 5-star Vine reviews and 29,982 5-star non-Vine reviews.
![5star_Vine](https://github.com/hankai26/Amazon_Vine_Analysis/blob/main/images/5-star_vine.png)
![5star_nonVine](https://github.com/hankai26/Amazon_Vine_Analysis/blob/main/images/5-star_nonVine.png)

- Five-Star review percentage in Vine and non-Vine reviews
The results show that 34.1% and 48.3% of total reviews are rated as 5-star in Vine and non-Vine reviews, respectively.

- One-Star review percentage in Vine and non-Vine reviews
Compare to 5-star reviews, we also examined the 1-star review for both Vine and non-Vine reviews to determine if there's negative bias for Vine program. The numbers of 1-star reviews in Vine and non-Vine reviews are 36 and 11,014.

![1star_Vine](https://github.com/hankai26/Amazon_Vine_Analysis/blob/main/images/1-star_vine.png)
![1star_nonVine](https://github.com/hankai26/Amazon_Vine_Analysis/blob/main/images/1-star_nonVine.png)

# Summary
The analyzed ratios for 5-star are 34.1% and 48.3% for Vine and non-Vine reviews, which don't show much difference. There's no positive bias for Vine program when companies paid on the reviews. However, the further analysis on 1-star reviews indicts that there're 36 and 11,014 1-star vine reviews and non-Vine reviews, respectively. The significantly small number of 1-star Vine reviews indicates two posibilities. One is that people would rather not give a 1-star review involving the Vine program, which is a negative bias. Or it's also possible that companies who would like to pay for reviews always provide toys with higher quality.


