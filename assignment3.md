# DC Crime data
**The question**: What are the most common crime types reported within one mile of AU's campus, and during which shift (day, evening, or midnight) do they occur most frequently?

**Newsworthiness**: The data is for the area within one mile of the campus, directly impacting students, faculty, and staff who live, work, or commute in the surrounding neighborhoods.
 Safety is a big concern for any university community. Revealing the specific crime types and the times of day they are most common provides useful information. 
 It helps the audience assess their personal risk and take precautions.

 **Steps to answer the question**: 
 
  . Rows (Index): offense-text (Crime Type)

. Columns: SHIFT (Day, Evening, Midnight)

. Values/Aggregation: A count of the reports (COUNT in Excel's Pivot Table Field List).

. This grouped all crime reports by both the crime type and the time of day, counting the number of occurrences for each combination.

. A Total count was calculated across all shifts for each crime type, equivalent to adding a "Grand Total" column for the rows in Excel.

. The entire table was then sorted in descending order by this Total count to identify the most frequent crime types overall.

**Answer to the question**

. Theft/Other (e.g., shoplifting, bicycle theft, stolen property) is by far the most common crime, accounting for 212 of the total reports.
It occurs most frequently in the Evening (123 reports).

. Theft F/Auto (80 reports) and Motor Vehicle Theft (15 reports) are the next most common crimes. 
Both of these vehicle-related offenses occur most frequently during the Day shift.

