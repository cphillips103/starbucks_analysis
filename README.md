![WIP Image](https://github.com/cphillips103/starbucks_analysis/blob/main/images/WIP.png)
# Udacity Starbucks Project

# Udacity Data Science Nanodegree

## Starbucks
<img src="https://github.com/cphillips103/starbucks_analysis/blob/main/images/Starbucks-Logo.jpg" width="240" height="194">


The dataset provided in this portfolio exercise was originally used as a take-home assignment provided by Starbucks for their job candidates. The data for this exercise consists of about 120,000 data points split in a 2:1 ratio among training and test files.

In the experiment simulated by the data, an advertising promotion was tested to see if it would bring more customers to purchase a specific product priced at $10. Since it costs the company 0.15 to send out each promotion, it would be best to limit that promotion only to those that are most receptive to the promotion.

Each data point includes one column indicating whether or not an individual was sent a promotion for the product, and one column indicating whether or not that individual eventually purchased that product. Each individual also has seven additional features associated with them, which are provided abstractly as V1-V7.

The task is to use the training data to understand what patterns in V1-V7 to indicate that a promotion should be provided to a user. Specifically, your goal is to maximize the following metrics:

**Incremental Response Rate (IRR)**

IRR depicts how many more customers purchased the product with the promotion, as compared to if they didn't receive the promotion. Mathematically, it's the ratio of the number of purchasers in the promotion group to the total number of customers in the purchasers group (_treatment_) minus the ratio of the number of purchasers in the non-promotional group to the total number of customers in the non-promotional group (_control_).

![IRR Image](https://github.com/cphillips103/starbucks_analysis/blob/main/irr_formula.png)

**Net Incremental Revenue (NIR)**

NIR depicts how much is made (or lost) by sending out the promotion. Mathematically, this is 10 times the total number of purchasers that received the promotion minus 0.15 times the number of promotions sent out, minus 10 times the number of purchasers who were not given the promotion.

![IRR Image](https://github.com/cphillips103/starbucks_analysis/blob/main/nir_formula.png)



EDA and Model considerations:

![Training Data](https://github.com/cphillips103/starbucks_analysis/blob/main/images/training_table.png)

Training Data shows layout of the data frame and the features V1 through V7

![Promotion Split](https://github.com/cphillips103/starbucks_analysis/blob/main/images/promotion_split.png)

The promotion split chart shows that the training data is evenly divided between customers that are promoted to or not promoted to.

![Purcashe Split](https://github.com/cphillips103/starbucks_analysis/blob/main/images/promotion_split.png)

However, when we look at the proportions of Non-purchasers and Purchasers, we see that the data is not very balanaced since there is only a very small number of purchasers regardless of promotion or non-promotion.

This small number of purchsers and model prediction based on customer features is closer to modeling with SPAM or Fraud detection since those models need to look for unusual activity in large data sets.

Such being the case, the modeling process for the Starbucks data needs to take into account that there are only a small number of positive purchase cases in a large data set.

An illustration of the variance between Purchasers and Non-Purchasers:


![Purchase Split](https://github.com/cphillips103/starbucks_analysis/blob/main/images/purchase_histograms.png)
 

 The histograms of the customer attributes shows that there are only slight variations between those that purchase and those that don't.

 The split between Promoted and Non-Promoted purchasers finally shows some variation in the attributes, but again, the total purchasers is a small signal in the data set.

 ![Purchase Split](https://github.com/cphillips103/starbucks_analysis/blob/main/images/purchase_promo_nopromo_histos.png)

 With such small numbers, the modeling process will need careful attention to boost the small signal in the data so that the model will be able to predict future purchasers based on promotion campaigns.
 