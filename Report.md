Covid-19 awareness data analysis
================
Fatih KIYIKÇI

Quiz and data gathering
-----------------------

I tried to make the quiz not too hard, but at the same time hard to get a 100 or 90 points, selected some of the questions and options to acquire both the knowledge and common sense of people. There was only one person that did not answered a question. Non-demographic Questions and response rates are:

Corona virüsün ölümcüllük seviyesi nedir? 37/37
Koronavirüs'ün en yaygın belirtileri nelerdir? 37/37
koronavirüs tanısı konulmuş biriyle temastan sonra ne yapılmalıdır? 37/37
Koronavirüs belirtisi gösterenler ne yapmalı? 37/37
Virüsten hijyenik olarak korunmak için hangileri yapılmalıdır? 37/37
Koronavirüsten en ciddi etkilenen gruplar hangileridir? 37/37
Hangileri koronavirüse karşı alınacak önlemler arasındadır? 37/37
Covid-19 hastalığını tedavi edebilecek aşı, ilaç veya bir tedavi mevcut olarak bulunmakta mıdır? 36/37
Hangisi koronavirüse karşı daha etkili bir yöntemdir? 37/37
Covid-19 Hastalığını oluşturan virüsün adı nedir? 37/37

Data Visualization
------------------

### Distribution of the scores according to the quiz taker's age

![](fatih_kıyıkçı_hwfinal_files/figure-markdown_github/yaş-score-1.png)

As seen in the visualization, the young adult and adult groups are very close in terms of their score, there are 2 age groups that stands out, which are children (&lt;18) and older adults (&gt;55). Children group has the lowest score in all four groups, which is expected. Older adults have the highest score of all four groups. Which is not much surprising since the virus is particularly dangerous for older people, but this is not much accountable, since there are only 2 samples from the older adult age group.

### Distribution of the Total.scores

![](fatih_kıyıkçı_hwfinal_files/figure-markdown_github/score_count-1.png)

From the graph it can be clearly seen that the scores distribution follows the normal distribution. Most people get a score of 60 or 70, which is a mediocre level of knowledge about the virus and effects.

### Distribution of scores according to the quiz taker's education level

![](fatih_kıyıkçı_hwfinal_files/figure-markdown_github/eğitim_score-1.png)

Unsurprisingly, we can see the samples with the lowest education level, which is 'primary school' doesn't have as much success in the test as the people with higher education, But there seems to be not much difference between the 'Highscool' and 'University' education levels, other than the variation.

### Distribution of the scores with respect to the smoker/non-smoker property

![](fatih_kıyıkçı_hwfinal_files/figure-markdown_github/smoking_score-1.png)

Interestingly, people who smoke has clearly more success at the test, It can be associated with some of the questions, we can further investigate the reason.

Confidence Intervals
--------------------

### Confidence interval and confidence interval plot, with respect to the gender of the quiz taker.

    ##          lower    upper
    ## Erkek 51.83954 76.39576
    ## Kadın 57.86187 73.13813

![](fatih_kıyıkçı_hwfinal_files/figure-markdown_github/cidgender-1.png)

Looking at the confidence intervals, We can be %95 confident that the true mean for the male population is between 51.83954 and 76.39576.

We can be %95 confident that the true mean for the female population is between 57.86187 and 73.13813

We can see there is not much difference on the means for the genders, and the confidence interval for males is wider, this can be caused by the lack of information (as sample size) for males.

### Confidence interval and confidence interval plot, with respect to the education level of the quiz taker.

    ##               lower    upper
    ## Üniversite 57.99329 76.78932
    ## Lise       57.36055 82.63945
    ## İlkokul    39.40606 63.45108

![](fatih_kıyıkçı_hwfinal_files/figure-markdown_github/cidEğitim-1.png)

We can be %95 confident that the true mean for the population that has education level of primary school is between 57.99329 and 76.78932

We can be %95 confident that the true mean for the population that has education level of High school is between 57.36055 and 82.63945

We can be %95 confident that the true mean for the population that has education level of University is between 39.40606 and 63.45108

We can see the mean total scores of the three education levels, the mean total.scores of the samples that has education level of primary school is the lowest.

### Confidence intervals and confidence interval plots, with respect to the Faculty of the quiz taker.

    ##                               lower     upper
    ## Ziraat                     18.60013  74.73320
    ## Mühendislik                53.82629  84.35553
    ##                            49.61292  70.38708
    ## Tıp                              NA        NA
    ## Sağlık bilimleri                 NA        NA
    ## Eğitim                           NA        NA
    ## İktisadi ve İdari Bilimler 41.95369 108.04631
    ## Mimarlık                         NA        NA
    ## Edebiyat                         NA        NA
    ## İletişim                         NA        NA
    ## Spor Bilimleri                   NA        NA

![](fatih_kıyıkçı_hwfinal_files/figure-markdown_github/cidFakülte-1.png)

In the samples where the faculty of the quiz taker is; 'Edebiyat', 'Eğitim', 'İletişim', 'Mimarlık', 'Sağlık Bilimleri' and 'Tıp', there are only 1 samples each. Thus there are no confidence interval for those samples. The first bar, without the name is the samples for samples without the education level 'University'.

Hypothesis Testing
==================

Testing mean scores based on gender
-----------------------------------

### Normality testing

is the data normally distributed?
Ho: data is normally distributed
Ha: data is not normally distributed

    ## [1] "length of male samples: 17"

    ## [1] "length of female samples: 20"

    ## 
    ##  Shapiro-Wilk normality test
    ## 
    ## data:  Total.scores[Cinsiyet == "Erkek"]
    ## W = 0.96246, p-value = 0.6781

    ## 
    ##  Shapiro-Wilk normality test
    ## 
    ## data:  Total.scores[Cinsiyet == "Kadın"]
    ## W = 0.94833, p-value = 0.3424

p-value 0.6781, 0.3424 &gt; 0.05, fail to reject the null hyphotesis,
We assume both dataframes are normal

### Variance test

are variances the same for both sets?
Ho: varMale == varFemale
Ha: varMale != varFemale

    ## 
    ##  F test to compare two variances
    ## 
    ## data:  Total.scores[Cinsiyet == "Erkek"] and Total.scores[Cinsiyet == "Kadın"]
    ## F = 2.147, num df = 16, denom df = 19, p-value = 0.1137
    ## alternative hypothesis: true ratio of variances is not equal to 1
    ## 95 percent confidence interval:
    ##  0.8287488 5.7926705
    ## sample estimates:
    ## ratio of variances 
    ##           2.147001

confidence interval for variances equality includes 1 \[0.8287488, 5.7926705\]
p-value = 0.1137 &gt; 0.05
Fail to Reject Null
We assume variances are equal.

### Testing a Hyphotesis

Let's create a null hypothesis,
Ho: mean scores of both male and female are the same muFemale = muMale
An alternative hypothesis,
Ha: mean scores of males and females are not the same. muFemale != muMale

    ## 
    ##  Two Sample t-test
    ## 
    ## data:  Total.scores[Cinsiyet == "Erkek"] and Total.scores[Cinsiyet == "Kadın"]
    ## t = -0.20726, df = 35, p-value = 0.837
    ## alternative hypothesis: true difference in means is not equal to 0
    ## 95 percent confidence interval:
    ##  -14.92231  12.15760
    ## sample estimates:
    ## mean of x mean of y 
    ##  64.11765  65.50000

p-value = 0.837 &gt; 0.05
confidence interval includes mu=0. \[-14.92231, 12.15760\]
t(o) (0.20726) &lt; t(t) ~2
Fail to reject Null
There is no evidence that the true mean values for males and females is different.

![](fatih_kıyıkçı_hwfinal_files/figure-markdown_github/genderp-1.png)

Testing the answer to a specific question as smoker/non smoker
--------------------------------------------------------------

In the visualizations, an interesting result caught my attention; The smokers tend to have clearly better scores than non-smokers. This might be associated with the question; 'Koronavirüsten en ciddi etkilenen gruplar hangileridir?', which smoking is an answer option.

Since every question is worth of 10 points, i thought i could test an alternative hyphotesis: 'The mean difference of Total.scores between smokers and non smokers is greater than 10'

### Normality test

is the data normally distributed?
Ho: data is normally distributed
Ha: data is not normally distributed

    ## [1] "length of smoking samples: 12"

    ## [1] "length of non-smoking samples: 25"

    ## 
    ##  Shapiro-Wilk normality test
    ## 
    ## data:  Total.scores[Sigara.kullanıyor.musunuz. == "Evet"]
    ## W = 0.89647, p-value = 0.1428

    ## 
    ##  Shapiro-Wilk normality test
    ## 
    ## data:  Total.scores[Sigara.kullanıyor.musunuz. == "Hayır"]
    ## W = 0.9511, p-value = 0.2654

p-value 0.1428, 0.2654 &gt; 0.05 Fail to reject the null hyphotesis,
We assume both dataframes are normal

### Variance test

are variances the same for both sets?
Ho: varMale == varFemale
Ha: varMale != varFemale

    ## 
    ##  F test to compare two variances
    ## 
    ## data:  Total.scores[Sigara.kullanıyor.musunuz. == "Evet"] and Total.scores[Sigara.kullanıyor.musunuz. == "Hayır"]
    ## F = 0.66297, num df = 11, denom df = 24, p-value = 0.4837
    ## alternative hypothesis: true ratio of variances is not equal to 1
    ## 95 percent confidence interval:
    ##  0.2563206 2.1032885
    ## sample estimates:
    ## ratio of variances 
    ##          0.6629712

confidence interval for variances equality includes 1 \[0.2563206, 2.1032885\]
p-value = 0.4837 &gt; 0.05
Fail to Reject Null
We assume variances are equal.

### Testing a Hyphotesis

Let's create a null hypothesis,
Ho: difference in mean scores for smokers and non smokers is less than 10 muNonSmokers &gt;= muSmokers-10 An alternative hypothesis,
Ha: difference in mean scores for smokers and non smokers is greater or equal than 10

    ## 
    ##  Two Sample t-test
    ## 
    ## data:  Total.scores by Sigara.kullanıyor.musunuz.
    ## t = 1.8193, df = 35, p-value = 0.03872
    ## alternative hypothesis: true difference in means is greater than 10
    ## 95 percent confidence interval:
    ##  10.79602      Inf
    ## sample estimates:
    ##  mean in group Evet mean in group Hayır 
    ##            79.16667            58.00000

p-value = 0.03872 &lt; 0.05
confidence interval does not include mu=10. \[10.79602, Inf\]
t(o) (1.8193) &lt; t(t) ~2
Reject Null
There is no evidence that mean difference of Total.scores for smokers and non-smokers is less than 10, with %95 confidence.

Let's look at a plot to see the answers for that particular question ('Koronavirüsten en ciddi etkilenen gruplar hangileridir?') described by the question; ('Sigara kullanıyor musunuz?')

![](fatih_kıyıkçı_hwfinal_files/figure-markdown_github/q7-1.png)

    ## [1] 5.833333 2.000000

As seen in the plot 9/25 non-smokers' answers included the smokers and wrong.
The mean score for the question, answered by the smokers is 5.83, same for non-smokers is 2.0.

This partially explains why non-smokers get lesser grades than smokers.

Testing the total.score by age groups
-------------------------------------

![](fatih_kıyıkçı_hwfinal_files/figure-markdown_github/25yaşplot-1.png)

is the data normally distributed?
Ho: data is normally distributed
Ha: data is not normally distributed

    ## [1] "length of samples that are older than 25: 15"

    ## [1] "length of samples that are younger than 25: 22"

    ## 
    ##  Shapiro-Wilk normality test
    ## 
    ## data:  Total.scores[Yaş > 25]
    ## W = 0.96009, p-value = 0.6939

    ## 
    ##  Shapiro-Wilk normality test
    ## 
    ## data:  Total.scores[Yaş < 25]
    ## W = 0.96191, p-value = 0.5289

p-value 0.6939, 0.5289 &gt; 0.05, Fail to reject the null hyphotesis,
We assume both dataframes are normal

are variances the same for both sets?
Ho: varMale == varFemale
Ha: varMale != varFemale

    ## 
    ##  F test to compare two variances
    ## 
    ## data:  Total.scores[Yaş > 25] and Total.scores[Yaş < 25]
    ## F = 0.70139, num df = 14, denom df = 21, p-value = 0.5005
    ## alternative hypothesis: true ratio of variances is not equal to 1
    ## 95 percent confidence interval:
    ##  0.2735777 1.9836332
    ## sample estimates:
    ## ratio of variances 
    ##          0.7013861

confidence interval for variances equality includes 1 \[0.2231244, 2.0315278\]
p-value = 0.5005 &gt; 0.05
Fail to Reject Null
We assume variances are equal.

Let's create a null hypothesis;

Ho: difference in mean total.scores of the age group &gt; 25 and age &lt; 25 is 0 An alternative hypothesis,
Ha: difference in mean total.scores for age group &gt; 25 and age &lt; 25 is not equal to 0

    ## 
    ##  Two Sample t-test
    ## 
    ## data:  Total.scores[Yaş > 25] and Total.scores[Yaş < 25]
    ## t = 1.4851, df = 35, p-value = 0.1465
    ## alternative hypothesis: true difference in means is not equal to 0
    ## 95 percent confidence interval:
    ##  -3.580581 23.095733
    ## sample estimates:
    ## mean of x mean of y 
    ##  70.66667  60.90909

p-value = 0.1465 &gt; 0.05
confidence interval includes mu=0. \[-3.580581, 23.095733\]
t(o) (0.75962) &lt; t(t) ~2
Fail to Reject Null
There is no evidence that mean difference of Total.scores for samples younger than 25 and samples older than 25 is not 0, with %95 confidence.

ANOVA test
----------

### Test the total.score value by education level (3 groups)

Ho: data is normally distributed Ha: data is not normally distributed

![](fatih_kıyıkçı_hwfinal_files/figure-markdown_github/ANOVA%20Eğitim-1.png)

    ## 
    ##  Shapiro-Wilk normality test
    ## 
    ## data:  Total.scores[Eğitim.durumu == "İlkokul"]
    ## W = 0.96664, p-value = 0.8733

    ## 
    ##  Shapiro-Wilk normality test
    ## 
    ## data:  Total.scores[Eğitim.durumu == "Lise"]
    ## W = 0.95244, p-value = 0.7518

    ## 
    ##  Shapiro-Wilk normality test
    ## 
    ## data:  Total.scores[Eğitim.durumu == "Üniversite"]
    ## W = 0.94304, p-value = 0.2088

p-value 0.4925, 0.7403, 0.2088 &gt; 0.05, Fail to reject the null hyphotesis,
We assume all three dataframes are normal

Variance homogenety H0:var1=var2=var3 Ha:At least one of them is different

    ## 
    ##  Bartlett test of homogeneity of variances
    ## 
    ## data:  Total.scores by Eğitim.durumu
    ## Bartlett's K-squared = 2.7418, df = 2, p-value = 0.2539

p-value 0.5361 &gt; 0.05 Fail reject the null. We assume variances are homogen

Analysis of variance
--------------------

H0:mu1=mu2=mu3=mu4 Ha:At least one is different

    ##             (Intercept)       Eğitim.durumuLise Eğitim.durumuÜniversite 
    ##                51.42857                18.57143                15.96273

    ##               Df Sum Sq Mean Sq F value Pr(>F)
    ## Eğitim.durumu  2   1595   797.6    2.13  0.134
    ## Residuals     34  12729   374.4

P-value 0.134 &gt; 0.05 Fail to reject null P-values suggest that there is no group with different variances, If there was, we could use Posthoc test to find out which one.

Posthoc test to find which one is different.
--------------------------------------------

    ##   Tukey multiple comparisons of means
    ##     95% family-wise confidence level
    ## 
    ## Fit: aov(formula = Total.scores ~ Eğitim.durumu)
    ## 
    ## $Eğitim.durumu
    ##                         diff        lwr      upr     p adj
    ## Lise-İlkokul       18.571429  -6.772284 43.91514 0.1862559
    ## Üniversite-İlkokul 15.962733  -4.504162 36.42963 0.1509843
    ## Üniversite-Lise    -2.608696 -23.075590 17.85820 0.9477298

### Anova model plots.

We have already tested the assumptions needed for the anova test, But the assumptions can also be tested using the plots.

![](fatih_kıyıkçı_hwfinal_files/figure-markdown_github/anovaplot-1.png)![](fatih_kıyıkçı_hwfinal_files/figure-markdown_github/anovaplot-2.png)![](fatih_kıyıkçı_hwfinal_files/figure-markdown_github/anovaplot-3.png)![](fatih_kıyıkçı_hwfinal_files/figure-markdown_github/anovaplot-4.png)
