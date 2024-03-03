# Wikipedia-Neutrality

Since its creation, the goal of Wikipedia was to behave as something closer to an encyclopedia rather than a typical modern webpage. In 2001, Wikipedia solidified this stance by introducing the “Neutral Point of View” (NPOV) policy which asserts that all articles must be written without editorial bias. Yet, given that there are over 6 million articles currently hosted by Wikipedia, it is not guaranteed that all will uphold the promise of neutrality. But if Wikipedia is automatically seen as a trusted source, then maintaining unbiasedness is possibly more important than for sources that do not guarantee this absence of personal opinions. This study therefore aims to understand how well Wikipedia maintains neutrality through use of sentiment analysis.

## Requirements

```
!pip install wikipedia
!pip install vaderSentiment
!pip install nltk
```

## Methods
To study the difference in sentiment of featured and non-featured articles, a set of 75 articles from each category was obtained. For featured articles, the Wikipedia API was used to obtain a list of article names within the featured articles category. 75 random titles were then chosen from this list. For non-featured articles, the random function of the Wikipedia API was used to obtain an additional 75 articles. For each of the 125 total articles, the total content of the article was obtained as well as the page summary. The VADER sentiment analyzer was then used to calculate the neutral sentiment score for both the total content and summary. T-tests were then run to determine if the difference between the two groups of sentiments was significant.

Exploratory analysis showed non-featured pages’ content was much shorter on average than featured posts (265 words vs. 2,796 words). It was subsequently decided to analyze a new group of non-featured pages that had more similar lengths to the featured posts since studies have shown that sentiment can vary greatly by length. To obtain this subset, the minimum length of the featured posts (759 words) was calculated and used as a threshold when retrieving random non-featured pages. The process of conducting sentiment analysis and running a t-test was also done for a random subset of non-featured pages that had similar lengths to the featured articles.

## Results
Table 1 displays the results for the t-test comparing neutral sentiment scores for the articles’ total content. These results include a difference in means of -0.06, and a t-statistic of -4.23 which leads to a statistically significant p-value of 0.00. Featured pages have an average neutral sentiment of 0.815, and non-featured pages have an average neutral sentiment of 0.871.

$$
\begin{aligned}
& \text {Table 1. T-test results of comparing compound sentiment scores for total content.}\\
&\begin{array}{ccccc}
\hline \text {  } & \text { T-Stat } & \text { DoF } & \text { P-Value } & \text { Difference in Means }\\
\hline \text { Average compound sentiment score } & -4.23 & 74 & 0.00 & -0.06 \\
\hline
\end{array}
\end{aligned}
$$

Table 2 displays the results for the t-test comparing neutral sentiment scores for the articles’ summaries. These results again include a difference in means of -0.06, and a t-statistic of -6.30 which leads to a statistically significant p-value of 0.00. Featured pages' summaries have an average neutral sentiment of 0.870, and non-featured pages' summaries have an average neutral sentiment of 0.934.

$$
\begin{aligned}
& \text {Table 2. T-test results of comparing compound sentiment scores for summaries.}\\
&\begin{array}{ccccc}
\hline \text {  } & \text { T-Stat } & \text { DoF } & \text { P-Value } & \text { Difference in Means }\\
\hline \text { Average compound sentiment score } & -6.30 & 74 & 0.00 & -0.06 \\
\hline
\end{array}
\end{aligned}
$$

Table 3 displays the results for the t-test comparing neutral sentiment scores for the articles’ content where non-featured articles were chosen by length requirement. These results include a difference in means of -0.01, and a t-statistic of -0.86 which again leads to a non-statistically significant p-value of 0.39. Featured pages have an average neutral sentiment of 0.815, and non-featured pages have an average neutral sentiment of 0.825.

$$
\begin{aligned}
& \text {Table 3. T-test results of comparing compound sentiment scores for articles chosen by length.}\\
&\begin{array}{ccccc}
\hline \text {  } & \text { T-Stat } & \text { DoF } & \text { P-Value } & \text { Difference in Means }\\
\hline \text { Average compound sentiment score } & -0.86 & 74 & 0.39 & -0.01 \\
\hline
\end{array}
\end{aligned}
$$

## Analysis
For both total content and summaries of featured and non-featured Wikipedia pages, we can see that there is a difference in the amount of neutrality between the two groups. Although the t-test cannot directly say which group is more neutral than the other, the difference in means of -0.05 indicates that the featured pages are less neutral than the non-featured pages.

Looking at figure 1, this becomes apparent since the neutral sentiment of the non-featured pages is much more clearly skewed towards 1.0 (this highest possible neutral sentiment score). 
![Distributions of featured and non-featured sentiment scores](images/output_54_0.png.png)

Figures 2 and 3, however, show that this trend is possibly associated with length of text since the non-featured pages are typically shorter than featured pages. 
![](images/output_55_0.png.png)
![](images/output_56_0.png.png)

When considering non-featured posts chosen by length, however, the difference between the groups (-0.01) is no longer statistically significant, meaning that there is no evidence for a difference in the sentiment by group when length is more of a factor. Figure 4 displays these results and shows that the neutral sentiments are similarly varied around 0.810.
![](images/output_58_0.png.png)

## Conclusion
Findings from this study show that non-featured pages are potentially more neutral than featured posts or at the very least are as neutral as featured posts when length is a factor, suggesting that featured pages perhaps do not totally provide the neutrality promised by Wikipedia’s NPOV policy. More work would need to be done to determine if this is due to differences in length, age, or the sample of pages chosen. This work, however, supports prior research on sentiment analysis on online information platforms and offers insights into how individuals should regard the supposed unbiasedness of this type of content.