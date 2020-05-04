## Welcome to New York City Parking Tickets Data Analysis and Conclusions

You can use the [editor on GitHub](https://github.com/vpkshirsagar/MaverickSnipeShot/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for


Syntax highlighted code block

# 1.	Motivation:
500$ parking ticket issued...!! 🥵. If you’ve ever driven a car in New York City, you probably know the drill: The city’s free on-street parking gives a small, temporary benefit to a few lucky drivers. People tend to violate the parking rules creating big problems for everyone else. This unique dataset enlightens the causes and most frequent areas of parking breaches. If we care about cities and urban mobility, we really need to pay some attention to parking. If people are not parking correctly like taking place of two parking places for just one car, park in the handicapped reserved place. Without rationing, parking fills up due to illegal parking, double parking leading to traffic caused by parking search. Hence, parking has to be managed strictly by enforcing laws to prevent such problems. The outcome of the project will help the government plan for proper investment of resources and improve focus on regions where rate of parking violations is more and also concentrate on frequently occurring categories of violations. Also, we can ensure the Parking policy success from the analyzing the dataset further.
1)Where the rate of traffic rule violation is more i.e. more need of strict actions need to be taken by the traffic police?
	2)Which place is ideal in case of parking violations and no need of much attention as people are likely to follow all the rules? 
3)What is the rate of rule violations of the society and is the vehicle expired?
If you read further, you can get to know about the interesting things that can be analyzed from the dataset like what kind of parking violations would cost you more or less? Also, you can identify the regions where you should be more careful while violating the rules even for a couple of minutes. 
Apart from just these things we can further analyze to get the answers to following questions

# 2.	About the Data
Kaggle has so much interesting datasets to work on. I was searching for a large and interesting dataset so that I can put in my knowledge and skills acquired from the course to analyze by querying the Bigdata and visualizing the same. Here you can see the data. The NYC Department of Finance collects data on every parking ticket issued in NYC (~10M per year!). This data is made publicly available to aid in ticket resolution and to guide policymakers.
 
There are four .CSV files, covering Aug 2013-June 2017. The files are roughly organized by fiscal year (July 1 - June 30) with the exception of the initial dataset. I have considered the following features from the dataset.

![Image](DataTable.PNG)

See the dataset descriptions for exact details. Columns include information about the vehicle ticketed, the ticket issued, location and time.

![Image](DataTable.PNG)


# 3.	Obtaining the Data & Preprocessing

I directly downloaded the files from the Kaggle and stored in the local machine first.

Feature selection and uploading to GCS
Each file is of 2 GB approx. Some of the columns are not necessary for the analysis, so ran the python script to extract the useful features only from all the raw data before uploading it to Google cloud storage.

All the four csv files of size 4.0 GB in total are uploaded on the GCS by running the following google command line instruction: 

```markdown
<p class="hey">gsutil -o GSUtil:parallel_composite_upload_threshold=150M -m cp -r FOLDERNAME/FILENAME gs://BUCKET_PATH</p>
```

References for the commands to upload to GCS can be found here.

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](DataTable.PNG)


For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/vpkshirsagar/MaverickSnipeShot/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
