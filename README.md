# Quest for the Best: **Airbnb Listings in Venice, Italy** 🤌 🇮🇹 🍝 ⛲ 🛶 🏛️
## [Click Here for Slide Deck](https://docs.google.com/presentation/d/e/2PACX-1vQ1zlgoOKrjT7WA9JADbwnQoKsWkNsYrl2obzKNQJK3O7DTgfS7UDGtYUuVnT9qhw1_M2eDqP1i76nK/pub?start=false&loop=true&delayms=10000) | [ by Chrissy Taylor](https://www.linkedin.com/in/chrissytaylor2023/) 

## Where to find the best Airbnb experience for tourists booking a visit to Venice, Italy?
This 3-day Python project completed spring 2023 investigates AirBnB listing data from December 2022 using Jupyter Notebook in combination with Pandas, Numpy, Seaborn, and Matplotlib to learn about the location, review score, and price trends of available listings.

#### Dataset
Data is from [InsideAirbnb](http://insideairbnb.com/get-the-data/#:~:text=Venice%2C%20Veneto%2C%20Italy,(Explore)) 
 which includes over 7,000+ rows and 70+ columns of data, dated December 2022.

![Slide1](https://github.com/chrissy-taylor/Venice_Italy_AirBnB/assets/125925417/2566f69f-4a60-42ef-9a25-9b64093d5d3c) 

<h3 align="left">Tools</h3>
Python was used for data cleaning, data exploration, and for data visualization. 
The preliminary visualizations used Pandas, Numpy, Matplotlib, and Plotly to investigate and illustrate findings. 

![Top10maxListings](https://github.com/chrissy-taylor/Venice_Italy_AirBnB/assets/125925417/ae33533b-a70b-4958-ae1d-f1d1c66fe9fc)

![PriceMap](https://github.com/chrissy-taylor/Venice_Italy_AirBnB/assets/125925417/60db7ed2-75c6-47f3-a6d9-41828412de9e)

<h3 align="left">Process</h3>
To start, Python was used to extract the necessary rows and columns, and clean the resultant dataframe of special characters, duplicate, null, and miscast values. Here's one demonstration of decision-making in that process:


![Cleaning](https://github.com/chrissy-taylor/Venice_Italy_AirBnB/assets/125925417/a91e8731-1df4-4941-9a51-0dda01e9e66c)


Next, the investigation's direction was focused by **heatmapping the correlation** between review scores and contributing elements of each score to assess **which score factors mattered most** to Airbnb customers. 


![Heatmap of Corr code](https://github.com/chrissy-taylor/Venice_Italy_AirBnB/assets/125925417/db7eb60b-f53c-41e1-aa7d-87fcbc9b68f2)

#### **Value** (a nuanced blend of price and customer satisfaction) is most highly-correlated with overall review score, so we will focus on pricing and review scores to optimize "Bang for Buck".

Interestingly **Location** correlated the least with overall rating, but *Accuracy* scored very high. 

![Neighborhood Map python code](https://github.com/chrissy-taylor/Venice_Italy_AirBnB/assets/125925417/2c5d18a5-f840-4e69-9915-67eb6c089660)

The various locales could possibly attract different tourists with different priorities - for example, one of the most remote islands had very high-scoring reviews, but very few reviews. So despite staying in a remote location, the guests that did choose it apparently loved it. 

As long as a listing's **Location** is *Accurately* reflected online before booking - so guests know what they are getting into while planning - perhaps most Airbnb guests in this city are happy almost anywhere they choose to stay, just so long as they're waking up in Venice. 

![locationreviews](https://github.com/chrissy-taylor/Venice_Italy_AirBnB/assets/125925417/d7617b3f-76b4-4a52-bd18-80ac25fdfc33)

In a stunning city like Venice, perhaps everyone visiting is just happy to be there
and therefore don't typically score **Location** lower than 4.5 out of 5. 
                                           
<h3 align="left">Findings</h3>
Searching for patterns in price was stalled by the discovery of numerous outliers, some priced as low as $0 per night and some exceding $22,000 per night. 

![OutlierMAX](https://github.com/chrissy-taylor/Venice_Italy_AirBnB/assets/125925417/025ce1e4-85a4-4beb-bad3-660e73542aab)
![OutlierMIN](https://github.com/chrissy-taylor/Venice_Italy_AirBnB/assets/125925417/0c4e75d2-90c0-4e1e-87ee-3bd64aa4de96)

These extremely-priced outliers were discovered to be presumably due to webscraping errors found after further investigation of the initial URLs provided in each listing. 

After deciding to use an interquartile range to limit dataset to listings priced between 25th and 75th percentile, another complication was discovered:

![Slide7](https://github.com/chrissy-taylor/Venice_Italy_AirBnB/assets/125925417/a1c9e2d2-ac52-472a-8170-9a60327576de)

In the Venice marketplace of Airbnb, listings are located either on the Mainland *(Terraferma)* or on Islands *(Isole)*. This key difference divides the available Airbnbs into **two distinct groups of housing serving two different sets of customer needs & priorities.** The NYC equivalent might be a hotel room in Time Square vs a spare bedroom in New Jersey.

![IslePivot Code plus Txt](https://github.com/chrissy-taylor/Venice_Italy_AirBnB/assets/125925417/4aeee1b7-884a-4116-b33c-47089ecfc680)

The group located on Islands (Isole) have the most Airbnb listings by far, as well as a distinct range of listing prices. 
Due to the major differences between the two, both populations had to be identified and separated before analysis could continue. An interquartile range was then used to limit the dataset to the middle 50% for both populations, and normalized distribution of both populations was attained:

![Screen Shot 2023-06-08 at 12 18 40 PM](https://github.com/chrissy-taylor/Venice_Italy_AirBnB/assets/125925417/d8347aa0-1833-44f9-8173-086a84196bb6)

![Screen Shot 2023-06-08 at 12 33 26 PM](https://github.com/chrissy-taylor/Venice_Italy_AirBnB/assets/125925417/4f2565a7-6fa7-4952-bca0-b4ef2fdad8a0)

Then found neighbourhoods on Island *(Isole)* with low pricing trends, high review trends, and created a custom metric to sift through resultant rank of "Best Value" neighborhoods for the best selection of Airbnb listings to recommend.

![Custom Metric](https://github.com/chrissy-taylor/Venice_Italy_AirBnB/assets/125925417/48712a3e-b909-4d0c-bde9-034bbc11913e)
![pre-URLlist](https://github.com/chrissy-taylor/Venice_Italy_AirBnB/assets/125925417/477cfc80-5e84-42bc-92b6-d1b0d23ed01b)

### 18 listings from the Sant'Elena neighborhood curated along with the associated URLs for interested tourists to utilize in booking their personal travel dates.

![Screen Shot 2023-06-08 at 12 02 55 PM](https://github.com/chrissy-taylor/Venice_Italy_AirBnB/assets/125925417/3be3a4d8-f442-47b9-97c8-e6e7b1f2e1ba)

![ClosingSlide](https://github.com/chrissy-taylor/Venice_Italy_AirBnB/assets/125925417/a36ac7e9-2edf-4023-991e-a16a0a4e5aa8)
