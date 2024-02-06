# solution-file
Schuster is a multinational retail company dealing in sports goods and 
accessories. They are facing problems with vendors respect credit terms and 
some of them tend to make payments late. Schuster would wants try to 
understand its customers’ payment behaviour and predict the likelihood of 
late payments against open invoices.
Objective:
• Analyse the customer transactions data to find different payment patten
• Segregate the customers based on their previous payment patterns
• Predict the likelihood of delayed payment against open invoices from the 
customers
• Insights from the Developed Model
Approach:
1. Reading the Data and cleaning the data.
a. Feature RECEIPT_DOC_NO had about 0.03% of null values. They were 
dropped.
2. Derived the target variable ‘INTIME’ from the difference between 
'DUE_DATE’ and RECEIPT_DATE’.
3. Since feature ‘PAYMENT_TERM’ was in string format, we derived this 
feature from the difference between 'DUE_DATE' and 
'INVOICE_CREATION_DATE’
4. We saw that the ‘Received_Payments_Data’ had 65% of the data points 
as delayed and the rest of the transactions were done Ontime.
5. Performed EDA to derive insights from the features. The highlights of 
our analysis are described in the Business Insights section.
6. We performed clustering using Kmeans
7. The output of the KMeans clustering was used as an input to the Logistic 
Regression performed in the following steps.
a. Sum of Squared Distances was used to determine cluster size.
b. Silhoutte analysis was performed to determine the cluster size.
8. Logistic Regression was performed to derive the probabilities
a. MinMaxScaler was use to scale the data
b. Correlation matirix was created to visualize correlations between features.
c. RFE was used to for feature selection.
d. Statsmodels summary and VIF were used to eliminate the insignificant 
features.
9. We trained the model on 70% of the data and calculate the 
a. Accuracy score was calculated ~75% on the train data.
b. Confusion matrix was created.
c. Precision recall curve was created to arrive at an optimal probability cutoff. 
~0.42
10. Prediction was done on the test set and below metrics were seen
1.Accuracy Score : 0.76
2.Precision : 0.65
3.RECALL : 0.34
11. The Open_Invoice data was used to 
predict the probabilities of the late 
payment. We have made 
recommendations for Shuster at the 
end of this presentation.

Business Insights
Inferences from Univariate analysis:
1. RECEIPT_METHOD : We can see that 'WIRE' transfer followed by 'AP/AR Netting' is the highest receipt 
method
2. CURRENCY_CODE : We can see that 'AED' followed by 'SAR' and 'USD' is the most frequently used 
currency
3. INVOICE_CLASS : We can see the 'INV' (Invoice) followed by (CM) Credit Memo or Credit Note and then 
by (DM) Debit Memo or Debit Note 
4. INVOICE_TYPE : Goods are the most invoiced type over Non Goods.
5. INTIME: 34.35 % of the payment happen on time and more than 65.65 % of payments that are delayed
Customer Data in terms of Dollar Amount.
