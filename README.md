# Prosper Loans Exploration
## by Jennifer Romana


## Dataset

The original dataset consists of 113,937 Prosper loans with 81 variables each.  The variables include: 
- data about the loan, from the basics such as amount, term, origination date to more in depth such as service fees and principal losses , 
- data about the borrower, including credit rating (Agency and in-house), location, occupation and income
- some information about investor such as Lender Yield and Number of investors 

After gathering information about the company, the dataset was updated to exclude pre-July 2009 data in order to focus the analysis on the current business model and rating system, which came into effect at the relaunch in 2009 

This updated dataset consists of 84,984 Prosper Loans and 81 variables for time period July 2009 to March 2014.



## Summary of Findings

In this exploration I observed a risk-return tradeoff, in that higher risk loans had a higher yield. 

Returns were proxied by Lender Yield, which displays a normal, right skewed distribution between 4-34%, centres about a mean of 18% and has a spike at 31%

The risk aspect was explored by first defining risk:
- Non-performing Loans(Chargeoff, Default of 30+ days past due)  
- losses (Net Principal Loss)  

Common risk predictors and their relation to risk and the Prosper Rating was then explored 

**Credit Risk** 
Credit risk displays a normal distribution with a peak in 650-700 range. 

It is consistent with expectations about risk in terms of non-performing loans and the Prosper Risk Ratings

**Inquiries in Last 6 Months**
Skewed right, with highest frequency at 0 inquiries.  It is interesting that there are instances of 6+ inquiries given the minimum requirement for Prosper Loan is less than 5.  

Consistent with expectations about risk in terms of non-performing loans and separates the mid-to-low risk Prosper Rating from the high risk  

**Debt-to-Income Ratio**
Normally distributed, skewed to the right and centering around 22%.  

It is interesting to see datapoints greater than 50% when the minimum requirement is a ratio less than 50%.  This is an indication that Prosper Loans allows special consideration cases and may need to be watched as it's an indication of how rigoroous the Prosper screening process is.  

Optimal ratio sits at around 20% in terms of non- to performing loans.  

The ratio appears to be an important determinant of Prosper Rating for the low risk ratings AA, A, B and not such an dominant influence for the higher risk C to HR ratings.  

**Income**
Income is self reported and not neccessarily verified.  Income range is frequently reported between $25k and $75k.  

In terms of Prosper Rating, Income range does not appear to be a useful input

**Occupation and Loan Purpose**
Didn't provide meaningful results as the vast majority of occupation selected was 'Other' and loan purpose selected was 'Debt Consolidation'

**Loan Amounts and distribution of Loans**
Loan amount distribution gave insight to how Prosper Rating affects the loan options for a given borrower.  High risk borrowers are limited to $4k loans.  The mode at $4k of the loan amount distribution suggests Prosper Loans attracts higher risk borrowers, or those that cannot get financing from traditional lending institutions.  However trends are in favour of the mid-to-low risk borrowers with rapid growth in number of loans, as opposed to low and negative growth for the high risk borrowers.   



Given the correlation between common risk predictors and Prosper Rating, the analysis continues on the risk vs return concept, with Prosper Rating frequently proxying risk along with non-performing loans.

**Risk vs Return**
The visualization of Lender Yield vs Non Performing Loans strengthens the concept of Risk being compensated with Returns.

We see the interaction between how returns (Lender Yield) increases for risk taken, as proxied by the Prosper Rating and determined at the outset of a loan.

The visualizations also shows that within each Prosper Rating bucket, risk is still being compensated as shown by higher median yield for non-performing loans compared to performing loans.  This risk only becomes apparent during the loan term

**Non-performing Loans over Time**
This visualzation confirms the success in Prosper's business model.  It shows that the business model is achieving growth, as shown by increased number of loans over time, and that the model is minimizing and decreasing risks as shown by the low level and decreasing trends in Non-Performing Loans.  This analysis does not however take into account how returns for investors has trended over time.

**Prosper Rating as a valid risk predictor**
The Term visualization and Ability to Pay off Loan visualization confirms Prosper Rating as a valid risk predictor as the frequency of non-performing loans is shown to be heightened for the higher risk D-HR Ratings compared to the mid to-lower risk C to AA Ratings

**Ability to Pay off Loan**
These visualizations were surprising as they highlighted that non-performing loans more frequently coincided with lower monthly payments.  I would have expected a higher frequency on Non-performing loans at the higher monthly payments.  Across the Ratings, especially the mid-to-low risk C-A ratings where there is a larger set of higher monthly payments, the non-performing loans clustered around monthly payments $500 and below.  

Consideration must however be taken that:
- The bulk of data for all loans is in the lower left section, so a high level of non-performing loans should also be expected
- Higher monthly loan payments would generally mean higher loan amounts, again generally taken up by less risky borrowers.  
- Stated monthly income is self reported


## Key Insights for Presentation

For the presentation I focus on the risk vs return aspect from the point of view of an investor.

The introductory slides focus on introducing Prosper Loans as a growing marketplace, and invesment offerings in terms of loan amount and length of loans.

The presentation then focuses on Prosper Loans as a viable investment, looking at distribution of returns (Lender Yield) and of risks, being the distribution of non-performing loans and distribution of net principal loss.

The following slides then explores common risk predictors, credit score, number of inquiries, debt-to-income ratio and income range to highlight how the distribution of non-performing loans would compare to performing loans for commonly accepted ideas of risk.

The Prosper Rating is then introduced as a catch-all risk predictor that captures similar information as the common risk predictors by first comparing the distribution of non-performing to performing loans and then adding in Lender Yield in a boxplot to show an appropriate relationship between risk (Prosper Rating) and return (Lender Yield), that is higher risk has higher returns.

Finally a simple investment strategy is explored mainly using Prosper Rating.  First Loan Term options segemented by Prosper Rating is explored to help choose an appropriate Time Horizon.  Followed by Risk Tolerance in the form of determing the amount of money that the investor can stand to lose.  A heatmap that shows the Average Loss per Loan highlights the Prosper Rating and Lender Yield that result in higher losses (greater than 18c per dollar invested.  The average lender yield is around 18%) and directs the investor to an appropriate risk level (Prosper Rating) and return (Lender Yield) based on the loss amount tolerance.  The Average Loss per Loan is the sum of Net Principal Loss divided by the sum of Loan Amounts.


## References
- [Prosper website](https://www.prosper.com/)
- [Prosper Wikipedia](https://en.wikipedia.org/wiki/Prosper_Marketplace)
- [Propser Dataset](https://s3.amazonaws.com/udacity-hosted-downloads/ud651/prosperLoanData.csv.)
- [Prosper Variable Dictionary](https://docs.google.com/spreadsheets/d/1gDyi_L4UvIrLTEC6Wri5nbaMmkGmLQBk-Yx3z0XDEtI/edit#gid=0)