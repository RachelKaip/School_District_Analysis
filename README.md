# School District Analysis
## Overview 
This week, we helped Maria, the Chief Data Scientist of a city's school district, clean, analyze, and report on standardized testing data and trends at the high schools within the district.  We started our analysis by creating performance summaries of each school- taking into account the school size, individual grade level performance, school type (Charter or Distrcit), and it's total budget including the allotted spending per student.  These metrics were then added together to create an overall distric summary, that displays the entire distric's performance at a glance.       

However, after completing the first analysis, we got word of possible academic dishonesty in reporting Thomas High School's (THS) 9th grade test rest results.  So, we voided THS' 9th graders' scores from the script and re-ran the analysis to only include the grades of THS' 10th-12th graders.

Below, we compared the the two results- the original (with THS' 9th grade test scores) and the new findings (sans THS' 9th grade test scores)- side by side to showcase how each analysis was affected.  

## Results 
1. **District Summary**
    - Original District Summary Data Frame
      ![original_district_summary_df](https://user-images.githubusercontent.com/94569240/149582180-ad58a702-bd0a-47c3-9fc5-2ef916a8bb94.PNG)

    - New District Summary Data Frame
     ![new_district_summary_df](https://user-images.githubusercontent.com/94569240/149582189-6f8a8e63-d133-4649-87fe-c94172e6622f.PNG)

    Based on the tables above, you'll see that having the 9th graders at THS still included in the Total Students count, but their test scores voided to NaN, has a slightly negative impact on the test scores on all but one category.  Average Math Score, % Passing Math, % Passing Reading and % Overall Passing all decrease ever so slightly by ~0.2.  

2. **School Summary**
 Once we re-calculated the the average math and reading scores and %s passing to be taken from a new student count, omitting the 9th graders, we see a similar effect as we do above when we drill down the district's summary to showcase each school's overall summary. 

   - Original School Summary
    ![original_per_school_summary_df](https://user-images.githubusercontent.com/94569240/149582223-7e59226a-f52f-42a3-9a0d-46d4929c6059.PNG)

   - New School Summary 
    ![new_per_school_summary_df](https://user-images.githubusercontent.com/94569240/149582834-fcfdcc1b-48a0-433b-8920-be677af1b859.PNG)


    THS's scores and and percentages passing trend downwards ever so slightly again while the other schools' performacne remains unchanged.  This confirms that we can attribute the change in the district's performance to the changes made with THS.  

3. **THS' Academic Performance**
   Looking at it more closely, we can see that omitting THS' 9th grade scores does not impact the school's % Overall Passing enough to waiver their ranking as the second highest performing school within the district.  Below, you'll see the tables show THS in the second position even though this metric changes ~.3%.  
   - Original Top 5 Schools 
     ![original_top_5](https://user-images.githubusercontent.com/94569240/149582269-4d55ba75-f2ae-47a4-b5a7-e91fff5a9c3c.PNG)

   - New top 5 Schools 
     ![new_top_5](https://user-images.githubusercontent.com/94569240/149582294-3e761d45-6d1e-4f28-9ff6-6e2564637787.PNG)

4. **How Math and Reading Scores were affected by:**
   - **Grade Level**
     Out of the 4 metrics we measure here (scores by grade level, by spending budgets, size, and school type), the omition of THS' 9th grade scores were most noticeable when we looked at the district's scores by grade level.  
    - Original Scores by Grade
      ![original_math_scores_by_grade](https://user-images.githubusercontent.com/94569240/149582329-07220c57-29a4-486a-8c3a-080c16f80669.PNG)
      ![original_reading_scores_by_grade](https://user-images.githubusercontent.com/94569240/149582339-7cfa30ce-45cb-4201-ad5a-9961c7eb3ee7.PNG)

    - New Scores by Grade
     ![new_math_scores_by_grade](https://user-images.githubusercontent.com/94569240/149582359-b1ee5c05-b337-43e3-81ce-fdae273e6981.PNG)
     ![new_reading_scores_by_grade](https://user-images.githubusercontent.com/94569240/149582377-c2ac4bf5-52ee-494a-97ea-f869abc35863.PNG)

     As you can see above, where THS' 9th graders' average scores of 86.6 and 86.7 used to be, now displays NaN, as in not a number, beacsue we voided their scores to not contaminate the data with potential academic fruad.  

However, the average scores categorized by each school's spending budget, size, and type reamin unchanged.  See side by side comparisons below:  
   - **School Spending and Budget**
    *THS is in the $630-649 category*
     - Original School Budget per Student 
     ![original_spending](https://user-images.githubusercontent.com/94569240/149582404-8bbdabdf-6808-40b5-ac91-d4cbdee296ea.PNG)

     - New School Budget per Student 
     ![new_spending](https://user-images.githubusercontent.com/94569240/149582417-3159bbbf-3cea-498f-ae2a-ba1b66ca8eb2.PNG)

   - **School Size**
      *THS is in the Medium Size category*
     - Original School Size
     ![original_size](https://user-images.githubusercontent.com/94569240/149582501-f19b7339-73d1-436d-bc51-15d7d2e0bffc.PNG)

     - New School Size
     ![new_size](https://user-images.githubusercontent.com/94569240/149582514-2a7b8bd7-df29-4298-92f2-7fbf760bcc64.PNG)

   - **School Type**
    *THS is in the Charter category*
     - Original School Type
     ![original_type](https://user-images.githubusercontent.com/94569240/149582534-e1a10407-3850-4aa5-844a-7e88fd42dcca.PNG)

     - New School Type  
    ![new_type](https://user-images.githubusercontent.com/94569240/149582523-d2a222bd-b162-4414-8ba4-17b89bcd30ff.PNG)

## Summary 
In the end, while omitting 461 students from our data didn't have an incredibly significant impact on our findings, there are a few changes we can see when looking at our summary data frames.  Four of these changes are listed below: 
1. After we used the .loc[] method to void THS' 9th graders' socres, their scores will show as NaN in the student_data_df.  
2. For the per_school_summary_df, we are making our calculations based on a new student count that only includes the 10th, 11th, and 12th graders as THS.
3. Beacsue of the new calculations, THS' Average Math, Reading % Passing scores have trended downwards between ~0.1-0.3%.  You can see this in both the disctrict_summary_df and the per_school_summary_df.  
4. In the Math/Reading Scores by Grade data frames, THS's 9th's grade column will show "Nan" as opposed to a 0 or their original score.  
