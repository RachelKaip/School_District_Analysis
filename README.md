# School District Analysis
## Overview 
This week, we helped Maria, the Chief Data Scientist of a city's school district, clean, analyze, and report on standardized testing data and trends at the high schools within the district.  We started our analysis by creating performance summaries of each school- taking into account the school size, individual grade level performance, school type (Charter or Distrcit), and it's total budget including the allotted spending per student.  These metrics were then added together to create an overall distric summary, that displays the entire distric's performance at a glance.       

However, after completing the first analysis, we got word of possible academic dishonesty in reporting Thomas High School's (THS) 9th grade test rest results.  So, we voided THS' 9th graders' scores from the script and re-ran the analysis to only include the grades of THS' 10th-12th graders.

Below, we compared the the two results- the original (with THS' 9th grade test scores) and the new findings (sans THS' 9th grade test scores)- side by side to showcase how each analysis was affected.  

## Results 
1. **District Summary**
    - Original District Summary Data Frame

    - New District Summary Data Frame

    Based on the tables above, you'll see that having the 9th graders at THS still included in the Total Students count, but their test scores voided to NaN, has a slightly negative impact on the test scores on all but one category.  Average Math Score, % Passing Math, % Passing Reading and % Overall Passing all decrease ever so slightly by ~0.2.  

2. **School Summary**
 Once we re-calculated the the average math and reading scores and %s passing to be taken from a new student count, omitting the 9th graders, we see a similar effect as we do above when we drill down the district's summary to showcase each school's overall summary. 

   - Original School Summary

   - New School Summary 
    
    THS's scores and and percentages passing trend downwards ever so slightly again while the other schools' performacne remains unchanged.  This confirms that we can attribute the change in the district's performance to the changes made with THS.  

3. **THS' Academic Performance**
   Looking at it more closely, we can see that omitting THS' 9th grade scores does not impact the school's % Overall Passing enough to waiver their ranking as the second highest performing school within the district.  Below, you'll see the tables show THS in the second position even though this metric changes ~.3%.  
   - Original Top 5 Schools 

   - New top 5 Schools 

4. **How Math and Reading Scores were affected by:**
   - **Grade Level**
     Out of the 4 metrics we measure here (scores by grade level, by spending budgets, size, and school type), the omition of THS' 9th grade scores were most noticeable when we looked at the district's scores by grade level.  
     - Original Scores by Grade

     - New Scores by Grade
     
     As you can see above, where THS' 9th graders' average scores of 86.6 and 86.7 used to be, now displays NaN, as in not a number, beacsue we voided their scores to not contaminate the data with potential academic fruad.  

However, the average scores categorized by each school's spending budget, size, and type reamin unchanged.  See side by side comparisons below:  
   - **School Spending and Budget**
    *THS is in the $630-649 category*
     - Original School Budget per Student 

     - New School Budget per Student 

   - **School Size**
      *THS is in the Medium Size category*
     - Original School Size

     - New School Size

   - **School Type**
    *THS is in the Charter category*
     - Original School Type

     - New School Type  

## Summary 
In the end, while omitting 461 students from our data didn't have an incredibly significant impact on our findings, there are a few changes we can see when looking at our summary data frames.  Four of these changes are listed below: 
1. After we used the .loc[] method to void THS' 9th graders' socres, their scores will show as NaN in the student_data_df.  
2. For the per_school_summary_df, we are making our calculations based on a new student count that only includes the 10th, 11th, and 12th graders as THS.
3. Beacsue of the new calculations, THS' Average Math, Reading % Passing scores have trended downwards between ~0.1-0.3%.  You can see this in both the disctrict_summary_df and the per_school_summary_df.  
4. In the Math/Reading Scores by Grade data frames, THS's 9th's grade column will show "Nan" as opposed to a 0 or their original score.  
