# DeepAudit (Group 6)
A machine learning approach to automating the audit of financial statements

**Model Description and Instructions**

This Jupyter Notebook file contains the code for running a data model to automatically detect &#39;anomalous&#39; reporting periods using a company&#39;s financial statements. The meaning of &#39;anomalous&#39; in this context means that there a statistically significant probability that the company engaged in fraudulent or suspicious reporting activities. The model is essentially an implementation of the &quot;Beneish M-Score&quot; regression model, with the additional benefit that the data processing and model calculations are automatically performed and the results are simply provided to the end user.

**How does it work?**

The model reads in the financial statements for a company across several time periods. A number of financial ratios are calculated for each period using these statements, which are fed into a regression model. The output of this model is called the Beneish M-Score, and is an indicator as to whether a particular period of a company&#39;s financial statements is considered anomalous, and can be decomposed to identify which financial factors were particularly anomalous.

The M-Score is technically a binary output; scores below -1.78 are not anomalous, and scores above -1.78 are anomalous. However, the size of the M-Score can subjectively be interpreted as an indicator of the degree of certainty in the model&#39;s output. For example, an M-Score of 10 is more anomalous than an M-Score of 1.

The ground-truth dataset which these outputs are compared against during testing is a collection of dates for each company which correspond with the date of fraudulent activity that the company committed, as identified in an ASIC penalty notice.

**How do I use it?**

You can first test out the model using the existing datasets that are provided, which each have a penalty notice associated with them.

The very last cell in the Notebook file contains the &quot;get\_result&quot; function. Simply enter the ticker of the company you want to get the summarized results for into the function and run the cell to see the model outputs, as shown below.


![1](https://user-images.githubusercontent.com/53421402/143258380-2848912f-e03b-41b7-a6bb-2a31ad4c551b.png)


**Adding a new company**

To add a new company, it&#39;s recommended to go through Morningstar&#39;s DatAnalysis Premium service to download the financial statements. Here we&#39;re using Adairs Limited as an example. Download BOTH the annual and interim datasets (one at a time) as indicated below. Save the files to the /datasets/ folder in the format &quot;TICKER\_PERIOD&quot;, i.e., ADH\_FY and ADH\_HY for the annual and interim datasets respectively.

![2](https://user-images.githubusercontent.com/53421402/143258449-a3a7a7a8-9bee-4410-b99d-861d8a8c8d66.png)

In the Jupyer Notebook file, after adding a new company&#39;s data uncomment this line and run the notebook, and the file will be converted into a .xml file then a .xlsx file that can be interpreted by the Pandas library.

![3](https://user-images.githubusercontent.com/53421402/143258469-ed4bc973-bf54-4618-8f84-3a1ce1b7df68.png)
