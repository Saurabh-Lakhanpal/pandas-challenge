# pandas-challenge

Helping a school board and mayor make strategic decisions regarding future school budgets and priorities.

The first task, is to analyze the district-wide standardized test results. Given are every student's math and reading scores, as well as various information on the schools they attend. The task is to aggregate the data to showcase obvious trends in school performance.

### Solution 
- [DataAnalysisReport](https://github.com/Saurabh-Lakhanpal/pandas-challenge/blob/main/PyCitySchools/Report.md)
- [PyCitySchoolsJupyterNotebook](https://github.com/Saurabh-Lakhanpal/pandas-challenge/blob/main/PyCitySchools/PyCitySchools_solution.ipynb)
- [RawData_schools_complete](https://github.com/Saurabh-Lakhanpal/pandas-challenge/blob/main/PyCitySchools/Resources/schools_complete.csv), [RawData_students_complete](https://github.com/Saurabh-Lakhanpal/pandas-challenge/blob/main/PyCitySchools/Resources/students_complete.csv)

## District Summary

Perform the necessary calculations and then create a high-level snapshot of the district's key metrics in a DataFrame.

Include the following:

- Total number of unique schools.</br>
- Total students.</br>
- Total budget.</br>
- Average math score.</br>
- Average reading score.</br>
- % passing math (the percentage of students who passed math).</br>
- % passing reading (the percentage of students who passed reading).</br>
- % overall passing (the percentage of students who passed math AND reading).</br>


## School Summary
Perform the necessary calculations and then create a DataFrame that summarizes key metrics about each school.

Include the following:

- School name.</br>
- School type.</br>
- Total students.</br>
- Total school budget.</br>
- Per student budget.</br>
- Average math score.</br>
- Average reading score.</br>
- % passing math (the percentage of students who passed math).</br>
- % passing reading (the percentage of students who passed reading).</br>
- % overall passing (the percentage of students who passed math AND reading).</br>

## Highest-Performing Schools (by % Overall Passing)
Sort the schools by ```% Overall Passing``` in descending order and display the top 5 rows.

## Save the results in a DataFrame called "top_schools".

## Lowest-Performing Schools (by % Overall Passing)
Sort the schools by ```% Overall Passing``` in ascending order and display the top 5 rows.

Save the results in a DataFrame called "bottom_schools".

## Math Scores by Grade
Perform the necessary calculations to create a DataFrame that lists the average math score for students of each grade level (9th, 10th, 11th, 12th) at each school.

## Reading Scores by Grade
Create a DataFrame that lists the average reading score for students of each grade level (9th, 10th, 11th, 12th) at each school.

## Scores by School Spending
Create a table that breaks down school performance based on average spending ranges (per student).

Use the code provided below to create four bins with reasonable cutoff values to group school spending.

	spending_bins = [0, 585, 630, 645, 680]
	labels = ["<$585", "$585-630", "$630-645", "$645-680"]

Use ```pd.cut``` to categorize spending based on the bins.

Use the following code to then calculate mean scores per spending range.

	spending_math_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"])["Average Math Score"].mean()
	spending_reading_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"])["Average Reading Score"].mean()
	spending_passing_math = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Passing Math"].mean()
	spending_passing_reading = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Passing Reading"].mean()
	overall_passing_spending = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Overall Passing"].mean()

Use the scores above to create a DataFrame called ```spending_summary```.

Include the following metrics in the table:

- Average math score.</br>
- Average reading score.</br>
- % passing math (the percentage of students who passed math).</br>
- % passing reading (the percentage of students who passed reading).</br>
- % overall passing (the percentage of students who passed math AND reading).</br>

## Scores by School Size
Use the following code to create three bins with reasonable cutoff values to group school size.

	size_bins = [0, 1000, 2000, 5000]
	labels = ["Small (<1000)", "Medium (1000-2000)", "Large (2000-5000)"]

Use ```pd.cut``` to categorize school size based on the bins.

Use the following code to then calculate mean scores per size range.

	size_math_scores = school_size_df.groupby(["School Size"])["Average Math Score"].mean()
	size_reading_scores = school_size_df.groupby(["School Size"])["Average Reading Score"].mean()
	size_passing_math = school_size_df.groupby(["School Size"])["% Passing Math"].mean()
	size_passing_reading = school_size_df.groupby(["School Size"])["% Passing Reading"].mean()
	size_overall_passing = school_size_df.groupby(["School Size"])["% Overall Passing"].mean()
 
Create a DataFrame called ```size_summary``` that breaks down school performance based on school size (small, medium, or large).

## Scores by School Type
Use the ```per_school_summary``` DataFrame to create a new DataFrame called ```type_summary```.

This new DataFrame should show school performance based on the "School Type".
