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

The [midterm_160_color_analysis.ipynb](https://github.com/ucsd-dsc-arts/dsc160-midterm-group-11/blob/master/code/midterm_160_color_analysis.ipynb) notebook provides the code for the color analysis of posters using clustering.

## Results

(30 points) 

This section will contain links to documentation of your results. This can include figures, sound files, videos, bitmaps, as appropriate to your domain of analysis. Each result should include a brief textual description, and all should be listed below: 

- image files (`.jpg`, `.png` or whatever else is appropriate)
- audio files (`.wav`, `.mp3`)
- written text as `.pdf`

Color analysis using clustering:
The color black (and colors clustered with black, according to Euclidean distance of RGB channels) appears to be common across all of the genres, but it dominates in the `horror` posters. This is actually very plausible and makes a lot of sense because horror movies are typically distinguished by very dark elements/sentiments; it is very reasonable that black is the predominant color in the posters. The `romance` barplot was surprising; specifically, we expected more colors in the red category (red and its shades are typically associated with romance). However, it is possible that the sample used simply did not contain that much red colors. The `fantasy`, `drama`, and `sci-fi` genres share a similar distribution of colors; we believe that this could be attributed to the possibility that fantasy, drama, and sci-fi films share common elements in terms of visuals and settings, which would lead to similar color choices for their posters. The `documentary` genre seems to exhibit ties between black, white, silver, and gray, sharing a similar distribution with `romance`.

The graphs below show the comparison between the color distributions for horror and romance movie posters.

**Horror**
![horror](https://github.com/ucsd-dsc-arts/dsc160-midterm-group-11/blob/master/results/color_analysis_plots/horror.PNG)

**Romance**
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

## Team Roles

Provide an account of individual members and their efforts/contributions to the specific tasks you accomplished.

Eric wrote the base function for scraping images and the code for the color-analysis using clustering.

## Technical Notes and Dependencies

Any implementation details or notes we need to repeat your work. 
- Additional libraries you are using for this project
- Does this code require other pip packages, software, etc?
- Does this code need to run on some other (non-datahub) platform? (CoLab, etc.)

## Reference

References to any papers, techniques, repositories you used:
- Papers
- Repositories
- Blog posts
