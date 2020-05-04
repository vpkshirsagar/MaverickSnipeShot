## Welcome to New York City Parking Tickets Data Analysis and Conclusions

You can use the [editor on GitHub](https://github.com/vpkshirsagar/MaverickSnipeShot/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

# 1.	Motivation:
500$ parking ticket issued...!! 🥵. If you’ve ever driven a car in New York City, you probably know the drill: The city’s free on-street parking gives a small, temporary benefit to a few lucky drivers. People tend to violate the parking rules creating big problems for everyone else. This unique dataset enlightens the causes and most frequent areas of parking breaches. If we care about cities and urban mobility, we really need to pay some attention to parking. If people are not parking correctly like taking place of two parking places for just one car, park in the handicapped reserved place. Without rationing, parking fills up due to illegal parking, double parking leading to traffic caused by parking search. Hence, parking has to be managed strictly by enforcing laws to prevent such problems. The outcome of the project will help the government plan for proper investment of resources and improve focus on regions where rate of parking violations is more and also concentrate on frequently occurring categories of violations. Also, we can ensure the Parking policy success from the analyzing the dataset further.
1)Where the rate of traffic rule violation is more i.e. more need of strict actions need to be taken by the traffic police?
	2)Which place is ideal in case of parking violations and no need of much attention as people are likely to follow all the rules? 
3)What is the rate of rule violations of the society and is the vehicle expired?
If you read further, you can get to know about the interesting things that can be analyzed from the dataset like what kind of parking violations would cost you more or less? Also, you can identify the regions where you should be more careful while violating the rules even for a couple of minutes. 
Apart from just these things we can further analyze to get the answers to following questions

# 2.	About the Data
Kaggle has so much interesting datasets to work on. I was searching for a large and interesting dataset so that I can put in my knowledge and skills acquired from the course to analyze by querying the Bigdata and visualizing the same. Here you can see the [data](https://www.kaggle.com/new-york-city/nyc-parking-tickets). The NYC Department of Finance collects data on every parking ticket issued in NYC (~10M per year!). This data is made publicly available to aid in ticket resolution and to guide policymakers.

Here is what the data looks like before filtering
 
There are four .CSV files, covering Aug 2013-June 2017. The files are roughly organized by fiscal year (July 1 - June 30) with the exception of the initial dataset. I have considered the following features from the dataset.

![Image](DataTable.PNG)

See the dataset descriptions for exact details. Columns include information about the vehicle ticketed, the ticket issued, location and time.

![Image](DataSample.png)


# 3.	Obtaining the Data & Preprocessing

I directly downloaded the files from the Kaggle and stored in the local machine first.

Feature selection and uploading to GCS
Each file is of 2 GB approx. Some of the columns are not necessary for the analysis, so ran the python script to extract the useful features only from all the raw data before uploading it to Google cloud storage.

All the four csv files of size 4.0 GB in total are uploaded on the GCS by running the following google command line instruction: 

```markdown
<p class="hey">gsutil -o GSUtil:parallel_composite_upload_threshold=150M -m cp -r FOLDERNAME/FILENAME gs://BUCKET_PATH</p>
```

References for the commands to upload to GCS can be found here.

# 4.	BigQuery

With help of Big Query “Loading data from cloud storage” feature I have created the table in Big Query with auto schema detection option.
There are multiple options for uploading like
-	Uploading from Local Storage (Guide).
-	Uploading from GCS (Guide).
-	There are multiple other options you can get here.

Loading the data to BigQuery directly from Web UI has some constraints like:
1) Data should be less than 10 MB.
2) Total number of rows of data should be less than 16000.
For my case the data is about 4 GB so, I uploaded the data to GCS first and then moved it to BigQuery from GCS Bucket. If your datasets satisfy the first two conditions then you can directly load the data to BigQuery from WebUI. You can find different options for uploading the data to BigQuery here.

Here are some of the snapshots how the dataset is seen on the BigQuery WebUI.

Data types of the columns

![Image](TableStructure.PNG)

Data samples in BigQuery Web UI

![Image](DataSampleinBQ.PNG)

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
