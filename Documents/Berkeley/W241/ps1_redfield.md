Problem Set 1
================
Alex, Daniel and Micah
8/27/2019

Potential Outcomes Notation
===========================

1.  Explain the notation *Y*<sub>*i*</sub>(1).

**The potential outcome of treatment on each individual observation i.**

1.  Explain the notation *Y*<sub>1</sub>(1).

**The potential outcome of treatment on a given individual.**

1.  Explain the notation *E*\[*Y*<sub>*i*</sub>(1)|*d*<sub>*i*</sub> = 0\].

**The average potential outcome of treatment given that an individual i did not receive treatment. The unrealized potential outcome of receiving treatment.**

1.  Explain the difference between the notation *E*\[*Y*<sub>*i*</sub>(1)\] and *E*\[*Y*<sub>*i*</sub>(1)|*d*<sub>*i*</sub> = 1\].

**The former is the average potential outcome of treatment whereas the other is the average observed outcome of treatment among the group receiving treatment.**

Potential Outcomes and Treatment Effects
========================================

1.  Use the values in the table below to illustrate that *E*\[*Y*<sub>*i*</sub>(1)\] − *E*\[*Y*<sub>*i*</sub>(0)\] = *E*\[*Y*<sub>*i*</sub>(1)−\[*Y*<sub>*i*</sub>(0)\].
2.  Is it possible to collect all necessary values and construct a table like the one below in real life? Explain why or why not.

**It is not possible. In reality, we would not be able be able to measure both the value of the control and the treatment. In order to observe the value of treatment for an individual, we would necessarily no longer be able to measure the value without treatment.**

``` r
kable(table)
```

|  subject|  y\_0|  y\_1|  tau|
|--------:|-----:|-----:|----:|
|        1|    10|    12|    2|
|        2|    12|    12|    0|
|        3|    15|    18|    3|
|        4|    11|    14|    3|
|        5|    10|    15|    5|
|        6|    17|    18|    1|
|        7|    16|    16|    0|

Visual Acuity
=============

Suppose we are interested in the hypothesis that children playing outside leads them to have better eyesight.

Consider the following population of ten representative children whose visual acuity we can measure. (Visual acuity is the decimal version of the fraction given as output in standard eye exams. Someone with 20/20 vision has acuity 1.0, while someone with 20/40 vision has acuity 0.5. Numbers greater than 1.0 are possible for people with better than ânormalâ visual acuity.)

``` r
kable(d)
```

|  child|  y\_0|  y\_1|
|------:|-----:|-----:|
|      1|   1.2|   1.2|
|      2|   0.1|   0.7|
|      3|   0.5|   0.5|
|      4|   0.8|   0.8|
|      5|   1.5|   0.6|
|      6|   2.0|   2.0|
|      7|   1.3|   1.3|
|      8|   0.7|   0.7|
|      9|   1.1|   1.1|
|     10|   1.4|   1.4|

``` r
kable(d_1)
```

|  child|  part\_1|
|------:|--------:|
|      1|      0.0|
|      2|      0.6|
|      3|      0.0|
|      4|      0.0|
|      5|     -0.9|
|      6|      0.0|
|      7|      0.0|
|      8|      0.0|
|      9|      0.0|
|     10|      0.0|

``` r
kable(d_4)
```

|  child|  y\_0|  y\_1|
|------:|-----:|-----:|
|      1|   1.2|   0.7|
|      2|   0.5|   0.8|
|      3|   1.5|   2.0|
|      4|   1.3|   0.7|
|      5|   1.1|   1.4|
|      6|   1.2|   0.7|
|      7|   0.5|   0.8|
|      8|   1.5|   2.0|
|      9|   1.3|   0.7|
|     10|   1.1|   1.4|

``` r
kable(d_7)
```

|  child|  y\_0|  y\_1|
|------:|-----:|-----:|
|      1|   2.0|   1.2|
|      2|   1.3|   0.7|
|      3|   0.7|   0.5|
|      4|   1.1|   0.8|
|      5|   1.4|   0.6|
|      6|   2.0|   1.2|
|      7|   1.3|   0.7|
|      8|   0.7|   0.5|
|      9|   1.1|   0.8|
|     10|   1.4|   0.6|

In this table, `y_1` means means the measured *visual acuity* if the child were to play outside at least 10 hours per week from ages 3 to 6. `y_0` means the measured *visual acuity* if the child were to play outside fewer than 10 hours per week from age 3 to age 6. Both of these potential outcomes *at the child level* would be measured at the same time, when the child is 6.

1.  Compute the individual treatment effect for each of the ten children.

2.  Tell a "story" that could explain this distribution of treatment effects. In particular, discuss what might cause some children to have different treatment effects than others.

**First, the child might have genetic advantage or disadvantage for visual acuity. They might have factors of preference that cause them to stay inside rather than play outside that could also be related to their genetic factors..**

1.  For this population, what is the true average treatment effect (ATE) of playing outside.

**-.03**

1.  Suppose we are able to do an experiment in which we can control the amount of time that these children play outside for three years. We happen to randomly assign the odd-numbered children to treatment and the even-numbered children to control. What is the estimate of the ATE you would reach under this assignment? (Please describe your work.)

**The mean is 2.220446e-16. This the mean of treatment minus the mean of control when the values are NULL for treatment and odd and NULL for control and even.**

1.  How different is the estimate from the truth? Intuitively, why is there a difference?

**The estimate is slightly positive but basically 0, while the reality is negative. There's a difference because we are measuring the effect of treatment as if it were happening to the same individuals, but in fact we are measuring across different people.**

1.  We just considered one way (odd-even) an experiment might split the children. How many different ways (every possible ways) are there to split the children into a treatment versus a control group (assuming at least one person is always in the treatment group and at least one person is always in the control group)?

2.  Suppose that we decide it is too hard to control the behavior of the children, so we do an observational study instead. Children 1-5 choose to play an average of more than 10 hours per week from age 3 to age 6, while Children 6-10 play less than 10 hours per week. Compute the difference in means from the resulting observational data.

**Now the difference in means is .54.**

1.  Compare your answer in (g) to the true ATE. Intuitively, what causes the difference?

**Because you have let the children choose their own play time, they are no longer randomly selected, but selecting into groups. This could be caused by a different factor that is also related to their visual acuity.**

Randomization and Experiments
=============================

1.  Assume that researcher takes a random sample of elementary school children and compare the grades of those who were previously enrolled in an early childhood education program with the grades of those who were not enrolled in such a program. Is this an experiment or an observational study? Explain!

**This is an observational study. The researcher did not cause an intervention, but instead "observed" the effect resulting from studends who selected into one group or the other.**

1.  Assume that the researcher works together with an organization that provides early childhood education and offer free programs to certain children. However, which children that received this offer was not randomly selected by the researcher but rather chosen by the local government. (Assume that the government did not use random assignment but instead gives the offer to students who are deemed to need it the most) The research follows up a couple of years later by comparing the elementary school grades of students offered free early childhood education to those who were not. Is this an experiment or an observational study? Explain!

**Although it is not randomized, it is still an expiriment. There was an intervention that did or did not cause an impact and the research will try to discern that impact. The key is that an intervention happened.**

1.  Does your answer to part (2) change if we instead assume that the government assigned students to treatment and control by "coin toss" for each student?

**Only in that now it will yield more statistically legitimate results. It is still an expiriment, but now it is a randomized expiriment.**

Moral Panic
===========

Suppose that a researcher finds that high school students who listen to death metal music at least once per week are more likely to perform badly on standardized test. As a consequence, the researcher writes an opinion piece in which she recommends parents to keep their kids away from "dangerous, satanic music". Let *Y*<sub>*i*</sub>(0) be each student's test score when listening to death metal at least one time per week. Let *Y*<sub>*i*</sub>(1) be the test score when listening to death metal less than one time per week.

1.  Explain the statement *E*\[*Y*<sub>*i*</sub>(0)|*D*<sub>*i*</sub> = 0\]=*E*\[*Y*<sub>*i*</sub>(0)|*D*<sub>*i*</sub> = 1\] in words. First, state the rote english language translation; but then, second, tell us the *meaning* of this statement.

**This says the average observed outcome of control given that an individual is in the control group is the same as the potential outcome of the control group given that they receive treatment. The former is the realized outcome and the latter is the unrealized potential outcome. It means that, in expectation and assuming true randomization, the realized and unrealied potential outcomes are the same.**

1.  Do you expect the above condition to hold in this case? Explain why or why not.

**Because the sample is not random in this case, we would not expect it to hold. The statement only applies to samples that are selected randomly. In this case, the treatment sample likely has other factors contributing to their performances on tests.**

MIDS Admission
==============

Suppose a researcher at UC Berkeley wants to test the effect of taking the MIDS program on future wages. The researcher convinces the School of Information to make admission into the MIDS program random among those who apply. The idea is that since admission is random, it is now possible to later obtain an unbiased estimate of the effect by comparing wages of those who where admitted to a random sample of people who did not take the MIDS program. Do you believe this experimental design would give you an unbiased estimate? Explain why or why not. Assume that everybody who gets offer takes it and that prospective students do not know admission is random.

**This experminental design would give you an unbiased estimate of the propensity of MIDS applicants to have higher wages. However, the population of people applying to MIDS is not random and this result can not generalize to the broader population. MIDS applicants probably apply because they are interested in statistics and computer programming, have higher incomes (because this thing costs 60k), and are willing to take on a Masters program in the first place.**
