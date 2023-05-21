## **Project 03 - Big Data Technologies - Prakhar Jain**

This project involves the provisioning of a Lambda function to generate real-time finance data records for interactive querying. The main objective is to create a data pipeline that facilitates the analysis and visualization of finance data. The project focuses on consuming "real-time" data, processing it, and storing it in a format that enables efficient querying and further analysis. The goal is to handle rapidly changing data at sub-hour and sub-minute intervals.

We will be collecting the stock data with Yahoo Finance library of Python.

**Technologies used in the project include:**

- Amazon Kinesis
- Amazon Lambda
- Amazon Glue
- Amazon Glue
- Jupyter Notebook

**Steps in the Project:**

Step 1: Create Amazon Kinesis Data Stream and Kinesis Delivery Stream to store the data.

Step 2: Develop a Lambda function (DataTransformer) to collect and push the data to the Kinesis Delivery Stream. And complete the configuration needed.

Notes: AWS Lambda does have very limited libraries of Python. Therefore, first we need to create a layer in our Lambda function. In that layer, we will input the Python libraries including **yfinance (Yahoo Finance).**

Step 3: Run the lambda function with python code to store the data into the S3 bucket via kinesis delivery stream.

Step 4: Setting up AWS Athena to enable interactive querying of the data stored in the S3 bucket.

Step 5: Configure AWS Glue to connect with the S3 bucket created by the DataCollector. And Using the Glue Crawler to read the data from the S3 bucket in which we have the stock data.

Step 6: Use AWS Athena to write and execute queries on the collected data. Query that can give us the required results for data analysis. And download the results in the CSV file.

Step 7: Import the CSV file in Jupyter Notebook for data visualization of line chart and grouped bar chart, as mentioned in the project requirements.

Step 8: Answer the questions, based on the graphs.

## **Questions Asked:**

**Question 1:** Graph the maximum volatility trend per company (A single Line Chart: Each line refers to a company)

Which company is the most volatile?

**Answer:** Costco Wholesale Corporation (COST) is the most volatile company according to the line chart.

**Question 2:** Graph the daily average volatility per company (A Grouped Bar Chart: Each group refers to a company and the bars refer to the daily highest volatility)

Do the findings from this graph support your conclusion from the first graph?

**Answer:** Yes, with this graph also, we can see that the Costco Wholesale Corporation (COST) has the highest volatility among all the company. It was highest volatile on '2023-04-11' and had the highest volatility of more than 4.0 throughout the day.

### **Extras:**

I created a new file with results in which I included the highest high and lowest low of the day for each company. The result file is available in the Athena Folder and the screenshot is available in the Assets folder.

With that data, I created a box plot and one line graph.

**Question 3:** Which is lowest Volatile Company?

**Answer:** From the Box Plot, we can say that EBAY is lowest volatile company. The central line in the box indicates the median average volatility for each company, and the central line for Ebay is closest to the bottom of the box. The height of the box for EBAY stock is also very less comparing to others. The range of data is also less than every stock, except KR. However, the outlier of EBAY is very close of the range for EBAY, but little more far for KR.

**Question 4:** On which day, the Costco (COST) share was the lowest volatile?

**Answer:** On the date 2023-04-18, the stock price of Costco (COST) was the lowest volatile. As the range between highest high and lowest low is smallest.
