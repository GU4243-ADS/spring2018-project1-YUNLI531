# Spring2018
# Project 1: SPOOKY Data Analysis -- whether are they appropriate for children to read?

----


### [Project Description](doc/)
This is the first and only *individual* (as opposed to *team*) this semester. 

**Term: Spring 2018**

+ **Project title: SPOOKY Data Analysis -- whether are they appropriate for children to read?**
+ **This project is conducted by Yun, Li**
+ **Project summary:**

    This project is an analysis of the horror fiction. The initial purpose was to establish a book classification system similar to the Motion Picture Association of America (MPAA) film rating system. We analyzed texts from Edgar Allan Poe, Mary Shelley, and HP Lovecraft with the goal to find out whether they are appropriate for children to read. In this project, we did word frequency analysis, sentiment analysis and topic modeling analysis. In word frequency part, we focused on the word frequency of each author's work and the correlation between them.
    
    + In sentiment analysis part, we compared the results from NRC lexicon and Bing lexicon. We also did a further step about negativity analysis and violent word analysis.
    
    + In topic modeling part, we chose 6 topics and tried to find the difference in probabilities between the topics.  

    Unfortunately, I didn't find a way to set up a standard to justify whether there is too much violent mood in their works. I would like to explore more in this area and hope in the future, we will have a baseline, for example, when these violent terms make up about 20% or more of the entire article, children need to read such books under the guidance of their parents. 


# When you hear the horror fiction, what is the first picture that appears in your head？

EAP

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/wordcloud_EAP.jpeg)

HPL

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/wordcloud_HPL.jpeg)

MWS

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/wordcloud_MWS.jpeg)

They are just the first expression of these three authors. Then, we will analyze the word frequency in each author's work.  


![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/word_frequency_of_each_author) 

We can already see that some words are almost equally frequent for all authors, such as “time”. In contrast, “love” is clearly more used by Shelley than by Lovecraft. The word “half” is only found in Poe and Lovecraft, but not in Shelley’s work at a notable frequency.

Let's go a step futher. Lets start to plot the word frequencies (log scale) comparing two authors at a time and see how words distribute on the plane. Words that are close to the line (y = x) have similar frequencies in both sets of texts. While words that are far from the line are words that are found more in one set of texts than another.  

As we can see in the plots below, there are some words close to the line but most of the words are around the line showing a difference between the frequencies. 

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/word_frequency_EAPvsHPL)

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/word_frequency_EAPvsMWS)

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/word_frequency_HPLvsMWS)

Then, we use Pearson for linearity method to calculate a correlation between the authors. In this way, we can verify the similarity or differences these sets of word frequencies by author. 
picture.

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/word_frequency_correlation)

There is a correlation of around 0.48 to 0.5 between the different authors.  

# Are they appropriate for children to read?

The Motion Picture Association of America (MPAA) film rating system is used in the United States and its territories to rate a film's suitability for certain audiences based on its content. The MPAA rating system is one of various motion picture rating systems that are used to help parents decide what films are appropriate for their children.

We would like to apply the idea of movie rating to book classification to help parents and children choose age-appropriate books.  To reach to the final goal, we did analysis in three aspects: sentiment analysis and topic modeling.  

# 1. Use NRC lexicon

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/NRC_all_bar)

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/NRC_author)

From above plot, we found that not much of a positive mood in HPL's works. MWS used positive words almost as much as negative ones. There’s much “trust” and “joy” to counteract all the “sadness”, “fear”, and “anger” in the world.  
 
# a)EAP  

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/NRC_EAP)

It is interesting that his most-used negative words are "words" and "doubt" - pointing to a different kind of horror of the imagination. His most-uesd positive word is "found".This made me much more interested in his works. I can't help wondering what I can find in his work.  

# b)HPL  

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/NRC_HPL)  

  
We found that not much of a positive mood in HPL's works. Similarly to EAP, the most-uesd positive word is "found". We also found that there were more words related to color than other two authors. HPL used "black" represents something negative while "white" and "green" are used for positive. In my opinion, "white" could be related to clean and honest and "green" is probably a color with full of hope and love.  

# c)MWS 
 
![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/NRC_MWS)  

We found that Mary Shelley used positive words almost as much as negative ones. She used "love" a lot as a positive word. "Death” is clearly her most common negative word. 
 

We have a question now. Will the result be different if we use other lexicons?  

Let's change from "nrc" to "bing" to get more information about sentiment analysis.  

# Use Bing Lexicon  

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/bing_all_bar)  

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/bing_author)

After applying "bing" lexicon, we found that overall, these three authors used more negative words than positive words.   

# a)EAP  

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/bing_EAP)

"doubt" and "death" became the most uesd negative words in EAP's works. While the word "word" which is the most used negative word in NRC lexicon analysis is no loner existing. The words in positive part are also different from NRC lexicon analysis.     

# b)HPL  

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/bing_HPL)

There is not much positive mood in HPL's works. The most uesd negative word and positive word are both different from NRC lexicon analysis. In this result, his most uesd negative word is "strange" which is somehow more reasonable than "ancient" in NRC.   

# c)MWS 

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/bing_MWS)

From above plot, we can find that she used "love" a lot as a positive word. "Death” is clearly her most common negative word.To my surprise, the most used negative and positive words are the same with the NRC lexicon analysis. She used positive words almost as much as negative ones.   

# 2. Comparing negativity  

First, we plot a frequency comparison of these "negative" words.   

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/Freq_negative)

Then, we go a step further and assign a “negativity fraction” to each sentence; defined in the same way as the other index: # negative / (# negative + # positive). We plot the distribution of these negativity indeces for the three authors:

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/Freq_negative_fraction)  

HPL's works are more negative than EAP and MWS. From the above plots, we know clearly when the fraction of negative words per sentence is between 0 and 0.5, the probability of negative words of MWS is lager than EAP and HPL.  

# 3. Vilence level analysis  

The Motion Picture Association of America (MPAA) film rating system has five components: Violence, Language, Substance abuse, Nudity and Sexual content. Considering the last 4 are more difficult to choose the standard for comparison, so here we only analyze the first one -- Violence.

We first built a dictionary contains all the common violent words. The violent words come from http://www.thesaurus.com. For example: crazy, cruel, fierce.

Then, we counted these words appeared in entire dataset and in each author's works.  

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/violent_word_all)   


![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/violent_word_author)

We found that these violent terms are indeed distributed among the three authors' works. Due to the lack of further information, we can not set a standard to justify whether there is too much violent mood in their works. Maybe in the future, we will have a baseline, for example, when these violent terms make up about 20% or more of the entire article, children need to read such books under the guidance of their parents. 

# 4. Topic Modeling  

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/topic_modeling.jpg) 

In the above, we found several words appear in many topics. For instance, topic 1,4,5,6 all contain the word "time". "found" is also a word contained by topic 2,3 and 6. At this point, I seem a bit understated why "found" is a negative term. When "found" appears together with other words related to people's body part like "eyes","head","heart" in a topic, it really makes people feel creepy. What's more, there are also some words that described time, such as "night", "dark" and also "time" itself which made me feel even more frightening.

Also, we see that these 6 topics are quite similar. I can hardly tell the difference between these topics. The only thing I can be sure of is that these words remind me of all the horror stories I might think of in my life.

Therefore, let's study terms that have the greatest difference in probabilities between the topics, ignoring the words that are shared with similar frequency between topics. We choose only the first 3 topics as example and visualise the differences by plotting log ratios: $log_{10}(\beta \text{ of topic x }/ \beta \text{ of topic y})$. So if a word is 10 times more frequent in topic x the log ratio will be 1, whereas it will be -1 if the word is 10 times more frequent in topic y.   

![](https://github.com/GU4243-ADS/spring2018-project1-YUNLI531/blob/master/figs/topic_modeling123.jpg)

In the above, I guess topic 1 may occur in the wild because this topic contains words like "moon", "sky" and "air" which are more popular than other two. Topic 2 may happen at a late night party. The story may have taken place in a study room full of books, all of them standing together.   

Therefore, let's study terms that have the greatest difference in probabilities between the topics, ignoring the words that are shared with similar frequency between topics. We choose only the first 3 topics as example and visualise the differences by plotting log ratios: $log_{10}(\beta \text{ of topic x }/ \beta \text{ of topic y})$. So if a word is 10 times more frequent in topic x the log ratio will be 1, whereas it will be -1 if the word is 10 times more frequent in topic y.    

# Think further

Due to the lack of appropriate judgments of children, the film classification system has largely avoided the children's exposure to violence, drugs and other works that are likely to have adverse effects on them. Similarly, in the literary world, similar hierarchies are needed to help children grow healthily.   

In this project, I didn't find a way to set up a standard to justify whether there is too much violent mood in their works. I would like to explore more in this area and hope in the future, we will have a baseline, for example, when these violent terms make up about 20% or more of the entire article, children need to read such books under the guidance of their parents. 




