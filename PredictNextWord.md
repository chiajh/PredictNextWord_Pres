Coursera Capstone Project- Predict Next Word
========================================================
author: JH Chia
date: 10 April 2016

This Reproducible Pitch Presentation is the final course project i.e. Capstone project for **Data Science Specialization** course, from Coursera in cooperation with [Swiftkey](http://swiftkey.com/).


Introduction
========================================================
The purpose of this capstone project is to built a Shiny application to predict the next word based on the last 1, 2 or 3 words entered by the user.

This project started off by getting the data from a corpus called [HC Corpora](www.corpora.heliohost.org) and the readme file is available [here](http://www.corpora.heliohost.org/aboutcorpus.html). The zipped raw dataset file for this project is available [here](http://d396qusza40orc.cloudfront.net/dsscapstone/dataset/Coursera-SwiftKey.zip).

The next steps are to create a sample corpus from 3 data sources i.e. Blogs, News and Twitter, clean the data (by removing all weird characters, profanity, URL, all punctuations, all numbers, stopwords such as "the", whitespace, converting to lower case, stem the words), exploratory analysis, creating n-gram files (biGram, triGram and quadGram) by tokenizing the cleaned sample corpus file.


The Prediction Algorithm
========================================================
The n-gram files with aggregated frequency then transformed to frequency dictionary data frames for each n-gram file. In these data frames, each word is represented by 1 column together with the frequency in descending order. E.g. for quadGram data frame, there are 4 columns for 4 words and another column for frequency.

Backoff algorithm will be used for the prediction where it will be recursively trying from the higher order of n-gram data frame to lower order of n-grams data frame until a reasonable probability is found. E.g. If the input is more than 3 words, compare the last 3 words of the input to the first 3 words of the quadGram data frame. If an appropriate match is **not found**, then compare the last 2 words of the input to the first 2 words of the triGram data frame.


Shiny Application
========================================================
The **Predict Next Word** Shiny application is avalilable at:
<https://chiajh.shinyapps.io/PredictNextWord>

To display the next predicted word(s), you need to enter word(s) at  **Please enter your text here:** input field and the result will be displayed on right panel.

You have the option to choose how many predicted words to be displayed by selecting **Number of predicted word to be displayed:** dropdown box.

Besides that, you can choose to display the entered text or vice versa by toggling **Display entered text** checkbox.

Please read the "Read Me" section in navigation bar for details.


Reference
========================================================
The source code for this **_R Presentation_** is available at:
<https://github.com/chiajh/PredictNextWord_Pres>

The **Predict Next Word** Shiny application is avalilable at:
<https://chiajh.shinyapps.io/PredictNextWord>

Source code for ui.R and server.R files are available on the GitHub:
<https://github.com/chiajh/PredictNextWord>

The zipped raw dataset file for this project is available at: <http://d396qusza40orc.cloudfront.net/dsscapstone/dataset/Coursera-SwiftKey.zip>.


Thank you.
