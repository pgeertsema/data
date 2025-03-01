# data
A repo that contains small datasets for example code

## ret_train.zip and ret_valid_template.zip

Both datasets are derived from the data made available at the [Open Source Asset Pricing](https://www.openassetpricing.com/) website. That data is based on the paper "Open Source Cross-Sectional Asset Pricing" by Chen and Zimmerman (2021),  published in Critical Finance Review. [Preprint version](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3604626) [Published version](http://dx.doi.org/10.1561/104.00000112)

We construct a target variable "target_ret" by moving the variable "mom12m" (12 month momementum, or the average return from month t-12 to t-1 inclusive) forward by 13 months, so that it now represents future returns from month t+1 to t+12 inclusive. (However, this means that the first year of return observations for each firm is lost.)

In order to obtain a more manageable dataset size, we retain only the last month in each year (December), only retain continuous predictors, only retain observations for which "target_ret" are not missing, drop all predictors with less than 50% coverage in the data, and drop all observations before 1992. 

Finally, we align the variable "year" with the year of stock returns in "target_ret". That means that the features themselves are those that would have been available for prediction (in principle) at the end of the prior year. 

"firmid" identifies individual firms and "year" identifies the year of stock returns for that firm. "target_ret" is the target to be predicted and all the remaining variables ("am" to "zerotrade6m") are available as predictive features.

For details regarding the meaning of specific features, please refer to [this link](https://drive.google.com/file/d/1Sev9s6cPFUGgxp1pFiej0lGzpsMqJCI2/view?usp=drive_link)
