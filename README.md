## Problem Statement

One of the questions an experienced ACT and SAT tutor has fielded a lot is whether a student should focus on the ACT or the SAT. Colleges say they treat the two tests equally, but is that true?

This project aims to explore whether or not college-level data supports the idea that college treats the ACT and the SAT equally. If not, is there an across-the-board bias, or is there a school-by-school bias that an applicant might be able to exploit to their advantage?

Similarly, are there any state-by-state biases in the strength of the ACT versus the SAT? As students are being compared to other students from their geographic region, this would suggest that an applicant might benefit from doing comparably well on the _less competitive_ test in their state.

## Data Dictionary for ACT and SAT Scores by State, 2019

|Feature|Type|Dataset|Description|
|---|---|---|---|
|state_or_territory|object|act_2019 and sat_2019 from prepscholar.com|The name of the state or territory|
|sat_participation_rate|float|sat_2019 from prepscholar.com|The SAT participation rate for eligible students in state or territory|
|sat_total|int|sat_2019 from prepscholar.com|The average SAT total score (EBRW + Math) in state or territory, rounded to nearest 10|
|act_participation_rate|float|act_2019 from prepscholar.com|The ACT participation rate for eligible students in state or territory|
|act_composite|int|act_2019 from prepscholar.com|The average ACT composite in state/territory, rounded to nearest integer|
|sat_equiv_of_act_composite|int|2018 ACT/SAT Concordance Tables|The equivalent SAT total score (EBRW + Math) for the state or territory's average ACT composite score|
|mean_sat_minus_sat_equiv_mean_act|int|calculated from sat_total and act_composite|The difference between the mean SAT total and the SAT total equivalent to the mean ACT composite for the state| 

## Data Dictionary for ACT/SAT Scores by College

|Feature|Type|Dataset|Description|
|---|---|---|---|
|school|object|sat_act_by_college from Compass Prep|College name|
|test_optional_or_no|object|sat_act_by_college from Compass Prep|Describes whether or not the college is test optional|
|applies_to_class_year_s|object|sat_act_by_college from Compass Prep|Class year or years for which test optional is available|
|policy_details|object|sat_act_by_college from Compass Prep|Description of the test optional policy, where applicable|
|number_of_applicants|int|sat_act_by_college from Compass Prep|The number of applicants to the college|
|accept_rate|float|sat_act_by_college from Compass Prep|The rate of acceptance for applicants|
|sat_tot_25th_percentile|int|sat_act_by_college from Compass Prep|The 25th percentile SAT total score (EBRW + Math) for accepted students|
|sat_tot_75th_percentile|int|sat_act_by_college from Compass Prep|The 75th percentile SAT total score (EBRW + Math) for accepted students|
|act_composite_25th_percentile|int|sat_act_by_college from Compass Prep| The 25th percentile ACT composite for accepted students|
|act_composite_75th_percentile|int|sat_act_by_college from Compass Prep| The 75th percentile ACT composite for accepted students|
|sat_equiv_of_act_25th|int|2018 ACT/SAT Concordance Tables|The equivalent SAT total score (EBRW + Math) for the college's 25th percentile ACT composite score|
|sat_equiv_of_act_75th|int|2018 ACT/SAT Concordance Tables|The equivalent SAT total score (EBRW + Math) for the college's 75th percentile ACT composite score|
|sat_minus_sat_equiv_25th_perc|int|calculated from sat_tot_25th_percentile and sat_equiv_of_act_25th|This is calculated from the 25th percentile SAT score for the college minus the SAT score equivalent for the 25th percentile ACT score for the college. A positive value indicates the 25th percentile SAT score is higher than its 25th percentile ACT counterpart. A negative value indicates that the 25th percentile ACT score is higher than its 25th percentile SAT counterpart|
|sat_minus_sat_equiv_75th_perc|int|calculated from sat_tot_75th_percentile and sat_equiv_of_act_75th|This is calculated from the 75th percentile SAT score for the college minus the SAT score equivalent for the 75th percentile ACT score for the college. A positive value indicates the 75th percentile SAT score is higher than its 75th percentile ACT counterpart. A negative value indicates that the 75th percentile ACT score is higher than its 75th percentile SAT counterpart|

## Brief Summary of Analysis
By examining summary statistics and individual data points, as well as heatmaps, histograms, bar charts, and scatterplots, it became clear that there are biases in most US states and territories towards either the ACT or the SAT and, similarly, that the majority of colleges display some, and in some cases, quite a lot, of bias towards one test or the other.

The most helpful metric to this analysis was the "SAT Total minus SAT Equivalent of ACT Composite", measured at the mean for state scores and at the 25th and 75th percentiles for the colleges. The methodology was to:

1. determine an SAT equivalent to the relevant ACT Composite using the 2018 ACT/SAT Concordance Table.
2. subtract that SAT equivalent from the related (i.e. mean, 25th percentile, or 75th percentile) SAT Total score.

A positive difference indicates that the SAT score at the given percentile or mean is higher than the ACT score. On the other hand, a negative difference indicates that the SAT score is lower than the ACT score.

It would be reasonable to expect that admitted student with a 25th percentile ACT at any given school would have equivalent scores (via the concordance chart) to admitted students with 25th percentile SAT scores at the same school. It turns out, however, that this is very often not the case.

## Conclusions and Recommendations

### States and Schools Often Show a Clear Bias Towards One Test or the Other

The data collected here reveals that there are clear biases towards one test or the other depending on the state or territory an applicant is from on the one hand, and the college an applicant is applying to on the other.

### This Data Can Be Used to an Individual Applicant's Advantage

Because standardized test scores are part of a suite of data points admissions offices use to compare students, one to another, it follows that if an applicant has comparable scores on the ACT and the SAT, they can and should decide which score to use based on some combination of geography and the school they're applying to. In essence, students are admitted not only based on their appeal to the school, _but also on their relative strengths -- including test scores -- compared to other applicants._

An important caveat is that this data doesn't speak to how much of a benefit is necessary to change an admission decision for any individual application at any given school. It's possible, for instance, that the equivalent of 1 ACT composite point or 30 SAT total score points could shift the balance for one specific applicant at one specific school, but not make a difference for another at the same or another school.

However, there's no apparent downside to using this approach other than the resources necessary to prepare for and take both the ACT and the SAT. While this may be prohibitive for some applicants, the two tests share a lot of commonalities, and trying to use the right test at the right school seems to be a low-risk, potentially high-reward approach.

### More Data Is Needed to Make More Precise Recommendations

That said, more data is needed to sharpen the determination of which test to use under which circumstance. 

For instance, at what geographic level are colleges focused? Ideally, high school-level data would be helpful for an applicant to understand whether their particular high school shows a bias towards one test or another. This data is often available for students, anonymized, through the college counselor's office. 

In addition, narrower geographic regions than the state level might be more helpful than state-level data. Whether or not that's the case should ideally be determined, perhaps by surveying admissions offices.

At the level of the college-specific data, it would be helpful to have more detailed data about applicants, such as geographic data, ideally tied to individual scores. To use that example, it would be helpful to know to what extent geography plays into the biases towards one test or another. If so, and students are being compared to each other within regions, that factor might outweigh any mean bias across the college toward one test or another, for any given region. On the other hand, if applicants aren't being considered by geographic region, this factor wouldn't matter. Either determination could influence whether and/or how to balance geographic data (such as the state-level date) against the overall patterns at any given college.

It would also be interesting (and potentially important for the colleges) to uncover why given colleges show the biases they have, particularly as they vary across score levels. For instance, do these schools need to do a better job of comparing scores across test? Are they showing improper biases towards geographic regions? While there are plenty of potential good reasons for schools showing biases (for instance, a state school preferencing in-state applicants, leading to a bias towards that state's preferred test), the information gleaned from examining this question could be important to determining if unhelpful or unconcious factors are at play in any given school's admissions office.