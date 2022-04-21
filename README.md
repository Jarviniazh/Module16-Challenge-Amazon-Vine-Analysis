# Amazon Vine Analysis

## Overview

### Purpose
This project helps the SellBy a company that is about to release a large catalog of products on Amazon, to analyze Amazon video game reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Since the SellBy need to pay a small fee to Amazon and gives out free products to select Vine reviewers. Our target is extracting thousands of reviews, transforming based on requested and loading transformed data into pgAdmin. Then analyze those data to figure out if  it’s worth the cost for the SellBy to opt in the program.

## Resources
- Data Source: 
[Amazon US Video Games Reviews](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Video_Games_v1_00.tsv.gz)
- Software: Google Colab Notebook, Jupyter Notebook, PostgreSQL 11.15

## Results
Firstly, we loaded the review data provided by Amazon and cleaned it for future analysis. Then connected to an AWS RDS instance and populated the data into the appropriate tables in pgAdmin as required. All data were successfully loaded into their respective tables in pgAdmin. [Click to check the screenshots of each table in pgAdmin](https://github.com/Jarviniazh/Module16-Challenge-Amazon-Vine-Analysis/tree/main/Resources/PgAdmin_Screenshots)

To make the results more reliable we only retrieve the reviews which received greater than to equal to 20 feedback votes from other customers. In addition, we take the helpful rate of a review as well. Filter and extract reviews with no less than 50% helpful vote rates to get ready for the later analysis. 

<p align="center">
 <img src="https://github.com/Jarviniazh/Module16-Challenge-Amazon-Vine-Analysis/blob/main/Resources/Basic_summary.png?raw=true" alt="Basic Summary"/>
</p> 

After data cleaning, the final dataset contains 40,565 total reviews. It can be seen that majority 40,471 (99.77%) reviews of video games in US are provided from regular customers with only 94 (0.23%) are from Amazon Vine program members.

<p align="center">
 <img src="https://github.com/Jarviniazh/Module16-Challenge-Amazon-Vine-Analysis/blob/main/Resources/Overall_summary.png?raw=true" alt="Overall Summary"/>
</p> 

With further investigation on star rating, there is no doubt that over half (48) of vine members tended to give 5-star reviews. And the unpaid 5-star reviews are 15,663 in total still occupy the most. However, only 38.7% the regular customers would like to share their opinions of the products they bought. Meanwhile, this large group lowers the percent of total 5-star reviews to 38.73%.    

<p align="center">
 <img src="https://github.com/Jarviniazh/Module16-Challenge-Amazon-Vine-Analysis/blob/main/Resources/Star_summary.png?raw=true" alt="Star Rating Summary"/>
</p> 

Then look into each star rating with two group of reviews. The Amazon Vine program members are willing to give higher rating and only 1 1-star review was collected. On the other hand, the regular customers would like to leave a review either they are super satisfied with a 5-star (38.7%) or disappointed with a 1-star (25.4%). 

## Summary
#### Conclusion
<p align="center">
 <img src="https://github.com/Jarviniazh/Module16-Challenge-Amazon-Vine-Analysis/blob/main/Resources/Bias_summary.png?raw=true" alt="Bias Analysis"/>
</p> 

Based on our analysis, there appears to be a positivity bias among Video Games reviews in the Amazon Vine program. While only 38.7% of regular reviews give 5-star, 51.06% of Vine reviews give 5-star. 

And besides 5-star, the overall star-rating percentages of each rating stage from the Vine program members are in a descending order. In other words, over 90 percent Vine members would like to comment at least with a 3-star. However, though many regular customers share their positive feedbacks of a product, to a certain extent, they might also give a negative review. Therefore, it is worth for SellBy to pay a small fee to Amazon and gives out free products to select Vine reviewers if the company want to receive a higher rating scores of their products.      


#### Recommendation
Considering out of the 40,565 total reviews analyzed, only 0.23% are from Vine program. This small number of reviews is not significant enough to sway the overall rating of products listed for sale on Amazon. The future analysis may focus on star-rating and product category. There is a wide range of categories under Video Games department, such as PlayStation 5 and PC. Research the potential relationship of each category and their rating would help SellBy classify which product category has a higher return.   
