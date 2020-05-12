# Project Title

DSC160 Data Science and the Arts - Midterm Project Repository - Spring 2020

Project Team Members: 

  - Yuxi Luo, yul884@ucsd.edu
  - Emily Kwan, ekwan@ucsd.edu
  - Ittoop Shinu Shibu, ishibu@ucsd.edu
  - Pratyush Juneja, pjuneja@ucsd.edu
  - Eric Yu, ery010@ucsd.edu 

## Abstract

  Group 11 plans to build a classifier and perform analysis for a unique art form: movie posters. Our goal is to be able to predict a movie’s respective genre based on its movie poster. The reason that our group decided to focus on this particular subject is because while movie making is highly regarded as an art form, we feel that the movie poster specifically is often overlooked. Like Rothko and many other artist’s work, we want to be able to shed some insight into this particular art form in a data-driven way and perhaps unveil some deeper meaning with our findings. In order to achieve this, we will compare the classified movies using K-means clustering to analyze how far apart or close each respective movie is grouped together. The data set we are going to analyze is from IMDB and contains the movie name, genre, IMDB score. We shall calculate basic image features from these posters and add it to the above Data Frame. We propose that specific movie genres will use different features and elements in their movie posters, making it possible to classify on these differences. Some features that we will use to address our question are movie rating score, entropy of image, energy of image, edge detection, facial data, and more. 
  
  The tools and techniques that we will be implementing to extract the necessary features to achieve our classification model will include using a convolutional neural network with Keras and TensorFlow or other machine learning algorithms such as Decision Trees, Random Forestation, etc. In addition, we will also try to use Bitmaps to analyse where each respective movie poster lies on a mean value versus mean hue scale. After performing our analysis, we expect that our results be displayed with multiple graphs to show the performance of our classifier (training vs. validation accuracy). We also plan to include a confusion matrix in order to show how accurately our classifier identifies a genre and compare between classifiers. One of our goals for this project is to continuously build off of what we had learned in class. To do so, we will use aspects of the Rothko classifier example, such as Bitmap generation and use beautiful soup to extract all movie posters. We will also be using sklearn packages such as skimage to help with the above analysis. What makes this project so interesting to us is coming up with a way to identify a potential genre without actually knowing anything about the movie. It’s a way of using machine learning to build a classifier solely based on image analysis. A lot of artwork and effort goes into making these posters that usually try and cover some sort of theme. For example a horror movie, would have a completely different poster to that of dumb and dumber which is a comedy movie. This information is easy for a person like us to judge but would also be impressive to be able to build a similar predictor to do that job for us. If time permits, we also feel looking at audio clips from the movie to classify it as the correct genre is something worth looking into. 

## Data

(10 points) 

This section will describe your data and its origins. Each item should contain a name of the data source, a link to the source, and any necessary background information such as:
- What is your cultural data source? 
- When was it made? 
- Who created the works? 
- Is it digital native, or is it some kind of scan, recording, photo, etc., of an analog form? 

## Code

(20 points)

This section will link to the various code for your project (stored within this repository). Your code should be executable on datahub, should we choose to replicate your result. This includes code for: 

- data acquisition/scraping
- cleaning
- analysis
- generating results. 

Link each of your notebooks or .py files within this section, and provide a brief explanation of what the code does. Reading this section we should have a sense of how to run your code.

The [midterm_160_color_analysis.ipynb](https://github.com/ucsd-dsc-arts/dsc160-midterm-group-11/blob/master/code/midterm_160_color_analysis.ipynb) notebook provides the code for the color analysis of posters using clustering. The notebook consists of functions for scraping/retrieving and processing images from urls, a custom implementation of k-means clustering based on Euclidean distance, and graphical displays of the results.

## Results

(30 points) 

This section will contain links to documentation of your results. This can include figures, sound files, videos, bitmaps, as appropriate to your domain of analysis. Each result should include a brief textual description, and all should be listed below: 

- image files (`.jpg`, `.png` or whatever else is appropriate)
- audio files (`.wav`, `.mp3`)
- written text as `.pdf`


`**INSERT HERE**`

**Color analysis using clustering:**

The color black (and colors clustered with black, according to Euclidean distance of RGB channels) appears to be common across all of the genres, but it dominates in the `horror` posters. This is actually very plausible and makes a lot of sense because horror movies are typically distinguished by very dark elements/sentiments; it is very reasonable that black is the predominant color in the posters. The `romance` barplot was surprising; specifically, we expected more colors in the red category (red and its shades are typically associated with romance). However, it is possible that the sample used simply did not contain that much red colors. The `fantasy`, `drama`, and `sci-fi` genres share a similar distribution of colors; we believe that this could be attributed to the possibility that fantasy, drama, and sci-fi films share common elements in terms of visuals and settings, which would lead to similar color choices for their posters. The `documentary` genre seems to exhibit ties between black, white, silver, and gray, sharing a similar distribution with `romance`.

The graphs below show the comparison between the color distributions for horror and romance movie posters. These two genres were the most distinct among the six genres analyzed.

**Horror Colors**

![horror](https://github.com/ucsd-dsc-arts/dsc160-midterm-group-11/blob/master/results/color_analysis_plots/horror.PNG)

**Romance Colors**

![romance](https://github.com/ucsd-dsc-arts/dsc160-midterm-group-11/blob/master/results/color_analysis_plots/romance.PNG)

## Discussion

(30 points, three to five paragraphs)

The first paragraph should be a short summary describing your results.

The subsequent paragraphs could address questions including:
- Why is this culturally relevant?
- How does your computational approach differ from the traditional art historical, musicological, manuel/subjective approach to analyzing your cultural subject? 
- How do you think the original artists/musicians would respond to this type of analysis? Would it change/inform their practice in some way?
- How do your results relate to broader social, cultural, economic political, etc., issues? 
- In what future directions could you expand this work?


`**INSERT HERE**`

The analysis of the pixels/colors is relevant to how colors are perceieved in different cultures. For American movies (which are the origin of the movie posters), we found that the colors clustered with black were the predominant colors of horror posters. Dark colors/shades are often associated as "bad" or "dangerous", which is why horror movies tend to be set during the night. It makes sense that the horror movie posters are predominantly composed of black pixels, since that would emphasize the "horror" or "danger" element of the actual film. The computational method of clustering is used in a unique way; typically, k-means clustering is an unsupervised method for classifying unlabeled items. For this analysis, clustering was used to reduce the number of colors we would have to analyze; each poster can have anywhere from 4000 to 10000 unique colors (defined by RGB channels) and clustering can help reduce the amount by grouping similar colors into pre-defined clusters (typical colors like black, white, red, green, blue). That is, rather than evaluating every possible shade of blue, we cluster all shades with the base color blue (RGB: (0, 0, 255)). In a sense, this is a supervised clustering because we use pre-defined clusters and find the distances of other colors (RGB channels) to the clusters. Designers of movie posters (or really, any art) may use this analysis to determine their choices for colors for a particular emotion they want to incite. For example, an artist who wants to create something that emphasizes love may want to use more reds, pinks and whites, while an artist who wants emphasis on danger might want to use more darker shades like black, gray, and brown. However, it may not necessarily change any practices, but rather, reinforce the current practices.


## Team Roles

Yuxi - performed EDA on ‘Documentary’ and ‘Sci-Fi’ genres (generated histograms, bitmaps, and other visualizations). Worked on cleaning and aggregating datasets for KNN classification implementation.

Eric -  wrote the base function for scraping images and the code / data cleaning for the color-analysis using clustering.

Emily - contributed to the description of data and discussion of results. worked on data cleaning and replicating movie genre classification based on movie ratings and other features. 

Pratyush - Performed EDA on ‘Romance’ and ‘Horror’ genres. Worked on preprocessing and creating a KNN model to try and classify different movies based on their image stats and features

Shinu - Performed EDA on ‘Fantasy’ and ‘Drama’ genres. Worked on cleaning and preprocessing dataset for the KNN classification model.


## Technical Notes and Dependencies

- Additional libraries you are using for this project
  All our libraries are included in the notebooks.
  
- Does this code require other pip packages, software, etc?
  No, all the packages we used are included in the notebooks

- Does this code need to run on some other (non-datahub) platform? (CoLab, etc.)
  All of our code was run on DataHub. A potential note to be aware of is the differences in each ‘.ipynb’ file. Each respective member was able to execute their own respective part in separate notebooks. In the end, we were all able to collaborate and bring together everything we worked on, however, there may be issues stringing all the notebooks together.

## Reference

https://github.com/davideiacobs/-Movie-Genres-Classification-from-their-Poster-Image-using-CNNs
https://towardsdatascience.com/unsupervised-classification-project-building-a-movie-recommender-with-clustering-analysis-and-4bab0738efe6
https://www.analyticsvidhya.com/blog/2019/04/predicting-movie-genres-nlp-multi-label-classification/
https://www.gnomon.edu/blog/15-things-you-need-to-know-to-design-posters-for-hollywood-movies
https://www.theguardian.com/film/2016/jan/28/why-modern-movie-posters-are-so-dreadful
https://stackoverflow.com/questions/48973768/calculating-dual-energy-gradient-using-numpy/48974892#48974892
