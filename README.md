# Amazon_Vine_Analysis

## Overview of the analysis: Explain the purpose of this analysis.

The purpose of the analysis is to perform ETL (Extract, Transform, and Load) on Amazon review dataset by using pgAdmin as table and relationship creating rool, and using Google Colab as dataframe creating and data manipulating tool. Amazon review set (https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Video_Games_v1_00.tsv.gz) is the source to use for product review. After extracting and transforming the data into readable dataframes, the number of reviews are then analyzed to compare for 5 star reviews in either vine or unpaid reviews to observe for any positivity bias.

## Results: Using bulleted lists and images of DataFrames as support, address the following questions:

- How many Vine reviews and non-Vine reviews were there?

Out of 40565 total reviews (filtered out unhelpful votes), 94 of them are vine reviews and 40471 are unmpaid reviews. 

- How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

There are 48 vine reviews that were 5 stars, and there were 15663 non-Vine reviews that were 5 stars.
- What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

51.1% of vine reviews were 5 stars (48 5-star reviews out of 96 total vine reviews) 38.7% of non-Vine reviews were 5 stars (15663 5-star reviews out of 40471 total non-Vine reviews).

See screenshot below for data summary using Google Colab.

![Review Calculation](https://github.com/jhuang2801/Amazon_Vine_Analysis/blob/main/Resources/Review_Calculation.png)

### Summary: In your summary, state if there is any positivity bias for reviews in the Vine program. Use the results of your analysis to support your statement. Then, provide one additional analysis that you could do with the dataset to support your statement.

Vine 5-star reviews are 12.4% more than non-Vine 5 star reviews (51.1% of 5-star vine review vs 38.7% of 5-star non-vine reviews). Interestingly, looking at the first 20 rows in both data sets, vine reviews are showing overwhelmingly "N" for verified purchase, and unpaid reviews were showing a fairly even mix of both verified and non-verified purchases.

Vine reviews: 
![Vine votes df](https://github.com/jhuang2801/Amazon_Vine_Analysis/blob/main/Resources/vine_votes_df.png)

Unpaid reviews: 
![unpaid votes df](https://github.com/jhuang2801/Amazon_Vine_Analysis/blob/main/Resources/unpaid_vote_df.png)

To understand the general consensus of a specific product, we can dive deeper into the distribution of reviews for one specific product ID, grouping by paid and unpaid reviews. Positivity bias could occur for products that have mostly 5-star paid reviews and 1-star unpaid reviews. A bar graph can then be used to plot the distribution of all reviews (0-5 stars) for both paid and unpaid.
