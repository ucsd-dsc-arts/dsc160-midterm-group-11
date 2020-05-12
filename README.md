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

  The dataset we are using is from the Kaggle dataset Movie Genre from its Poster generated from IMDB which had movie titles, IMDB scores, genres, and a link to the image of each movie’s poster. This dataset was created in 2017 and updated in 2018. From this dataset, we selected 6 genres of interest and for each respective genre, we downloaded the movie poster images from the given link which became our images dataset. The movie poster images are digital native posters created by digital artists in collaboration with the movie studio in order to promote or advertise the movie. They were created around the time of release and promotion of each movie. 

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

  The analysis of the pixels/colors is relevant to how colors are perceived in different cultures. For American movies (which are the origin of the movie posters), we found that the colors clustered with black were the predominant colors of horror movie posters. Dark colors/shades are often associated as "bad" or "dangerous", which is why horror movies tend to be set during the night. It makes sense that the horror movie posters are predominantly composed of black pixels, since that would emphasize the "horror" or "danger" element of the actual film. The computational method of clustering is used in a unique way; typically, k-means clustering is an unsupervised method for classifying unlabeled items. For this analysis, clustering was used to reduce the number of colors we would have to analyze; each poster can have anywhere from 4000 to 10000 unique colors (defined by RGB channels) and clustering can help reduce the amount by grouping similar colors into predefined clusters (typical colors like black, white, red, green, blue). That is, rather than evaluating every possible shade of blue, we cluster all shades with the base color blue (RGB: (0, 0, 255)). In a sense, this is a supervised clustering because we use pre-defined clusters and find the distances of other colors (RGB channels) to the clusters. Designers of movie posters (or really, any art) may use this analysis to determine their choices for colors for a particular emotion they want to incite. For example, an artist who wants to create something that emphasizes love may want to use more reds, pinks and whites, while an artist who wants emphasis on danger might want to use more darker shades like black, gray, and brown. However, it may not necessarily change any practices, but rather, reinforce the current practices.
  
  Our group decided to explore one of the most timeless, art pieces movies. Growing up, we all had a favourite type of movie. With the rise of large multi-million dollar summer blockbusters, movies have risen to become large and significant cultural phenomenons. In order to appeal to their target audience and come up with a better way to showcase what their movie would be about, coming up with a movie poster that accurately describes a movie, is now a big deal for the industry. Movie posters are artistic visualizations similar to other forms of art such as paintings on a canvas. One could argue that the most common type of artwork seen by the general public most often are movie posters or advertisements like it on billboards and bus stops. Since movie producers spend so much time capturing their theme through a poster, we thought it wise to try and analyse if movies that fit the same genre have similar elements behind them. We decided to explore 6 genres and conduct image analysis on the types of posters relating to these genres as well as try and find out if these characteristics could form the basis of a clustering algorithm. For certain comparisons between genres such as horror and romance, it was very evident that the two categories of posters had a different underlying theme to it. This was evident through the mean hsv values as well as the edge and entropy analysis as can be seen from discussion in the notebook. The backdrop to our analysis and what we wish to hold constant in moving forward is the fact that, similar genres rely on similar colour features to represent the genre. However this proved to be really hard as we only achieved a 27% accuracy when we tested the model. However this opens up a really broad scope of ways this can be achieved. Our design was very rudimentary and was meant for exploration whereas we can actually focus on building a CNN to do this for us.
  
  Our computation approach towards analyzing these posters differs from the traditional approach in analyzing historical art in several ways. Some aspects of traditional art historical analysis involve features that can be perceived with the human eye such as lines, box shapes, and objects. It also involves composition of the piece and how the subjects are arranged throughout as well as format and viewpoints. If analyzing physical paintings, aspects like the medium and technique can also be observed. From describing these visual qualities, conclusions can be subjectively drawn about the feelings that the art invokes such as strength or intimacy. Our computation approach was more focused on objective features of the art such as the color composition and clusters of colors that often appeared together. We also analyzed features such as mean hue, mean value, mean saturation, energy and edges of the poster which would be much more difficult to do non computationally. 
  
  In many ways, this type of analysis is not entirely new to the movie industry and current designers of movie posters. According to Tomasz Opasinski, a designer who has co-designed posters for over 300 movies in his 15 years working in Hollywood, movie poster design is largely already a very data driven process. The design of a poster is backed by empirical research rather than the intuition of the designer. Movie studios perform analysis on designs that have worked well in similar past movies as well as A/B testing of different potential designs with various focus groups. With this data, they are able to come up with the ideal proportions of the poster that should be allocated towards aspects of the movie such as imagery or the movie’s leading actor. However, the artistic element of the design is not entirely lost because as Opasinski says, “The designs may be driven by data, but they’re still my artistic interpretation of that data”. The analysis we performed could be similarly used by the studio to determine aspects of a poster that can be indicative of genres. By knowing the designs that appeal best to fans of certain genres, they can better instruct designers to create similar styled posters. 
  
  However, while this data driven approach may lead to the most lucrative box office numbers which is the main goal of the movie studios, it is also slowly causing a trend towards boring uniformity among movie posters of recent years. The companies and financial backers for movies are incentivized towards appealing to the largest number of general public and are therefore averse to any poster designs that may appear risky or controversial. As Scot Bendall, creative director at La Boca puts it, “Once a film grosses well with a particular style of poster, you are likely to see that style replicated over the genre as it was deemed a successful design”. The results of our research seem to agree, showing not very many truly distinctive features between movies of the varied genres we studied ranging from documentary to romance. The lack of distinctiveness we see in movie posters today lends itself towards being forgettable, a stark contrast from posters of the past like those of Pulp Fiction or Back to the Future, some of which still adorn the walls of college dorm rooms today. 
  
  Currently, we have worked with a KNN based classification model to predict movie genres based on the movies’ respective poster. Moving forward, it is entirely possible to manipulate classification models to see which models would perform the best. In addition, we could work with an expanded dataset that incorporates movie posters from different time periods and regions of the world. We predict that there may be more variables and features extractions needed in order to take into account a more diverse set of training data. Aside from expanding upon what we have done, a future direction to take this endeavor is to create generative art potentially using machine learning algorithms to create movie posters based on certain inputs.



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

- https://github.com/davideiacobs/-Movie-Genres-Classification-from-their-Poster-Image-using-CNNs
- https://towardsdatascience.com/unsupervised-classification-project-building-a-movie-recommender-with-clustering-analysis-and-4bab0738efe6
- https://www.analyticsvidhya.com/blog/2019/04/predicting-movie-genres-nlp-multi-label-classification/
- https://www.gnomon.edu/blog/15-things-you-need-to-know-to-design-posters-for-hollywood-movies
- https://www.theguardian.com/film/2016/jan/28/why-modern-movie-posters-are-so-dreadful
- https://stackoverflow.com/questions/48973768/calculating-dual-energy-gradient-using-numpy/48974892#48974892
