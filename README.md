# Carbon-Emission-Analysis

### Project Overview
This presentation looks into the lives of 10000 individuals and analyzes how their daily lives contribute to carbon emissions.

### Data Source
This data was obtained from [Kaggle](https://www.kaggle.com/datasets/dumanmesut/individual-carbon-footprint-calculation)

### Data Cleaning
Removing Duplicates

![1](https://github.com/user-attachments/assets/565a42d3-7521-4e91-9dfc-fa2110977e27)         ![2](https://github.com/user-attachments/assets/d4a3eed0-5df0-47d2-9eba-f117ac98d545)


Checking for Blank Cells  
- Blanks were seen in columns like “Vehicle Type”, “Recycling” and “Cooking with”

![3](https://github.com/user-attachments/assets/f217ff13-d94c-4a47-a96a-74d264817b8d)              ![4](https://github.com/user-attachments/assets/2e718ed8-23fa-4586-b943-f7638817000d)

Removing Blanks
- Blanks were replaced with “NA” with “Find and Replace” (CTRL + H). 
I verified in each column that the blanks being replaced with NA would not degrade the dataset.

![5](https://github.com/user-attachments/assets/6cda1e4e-4bd6-4c46-bf48-c1e743a9a69e)

### Preparing the Data
Creating a Unique Identifier Column (ID)
- I created the “ID” field to keep track of distinct rows I would soon be splitting. I used the Row() function.

![6](https://github.com/user-attachments/assets/e22a7744-755c-4747-bd42-6865c02c819a)

Splitting and Transposing Columns
- I split columns with cells that had multiple values into multiple columns with “Text-to-Columns”

![7](https://github.com/user-attachments/assets/02a093ac-ed2d-41b4-91ae-b05e0ba669af)        ![8](https://github.com/user-attachments/assets/abdc0ee9-0cc8-45a5-9be4-4a69122537ca)

I transposed the columns into one column in Power Query. This duplicated rows that I could now track with the ID column

![9](https://github.com/user-attachments/assets/e1150868-c0cd-4dc6-b721-b171a00fdf97)  ![10](https://github.com/user-attachments/assets/2dbee909-b3c5-4845-9d8c-c469d35333e3)

Identifying Distinct Rows
- Using this syntax:
(=IF(COUNTIFS($A$2:A2,A2, $C$2:C2,C2)=1, C2,"Duplicate"), I was able to link the unique identifier (ID) to relevant columns (columns that need distinct values for analysis) to create fields with distinct values. The syntax accepts the first instance of a unique row and associated column and recognizes the remaining rows as “duplicates”.

![11](https://github.com/user-attachments/assets/16524c0f-c793-400c-9971-19956a6adc56)

### Power BI Analysis
The data was imported into Power BI for further formatting, analysis and dashboarding.

Creating a List
Before I began visualization, I created a list for a “continuous numeric field” making it a discrete field. I grouped its values into three categories. This field would be used for later visualization.

![12](https://github.com/user-attachments/assets/c2fcbc4e-842d-400f-9645-931872b1a573)

Dashboard

![13](https://github.com/user-attachments/assets/6d0ce435-aa3c-43a3-9626-168a9c9233e6)

### Insights
- Heavy TV/PC users generate more emissions than Regular and Casual TV/PC Users generate combined.
- Users of petrol-powered cars produce more carbon emissions. Electric car users produce the least amount of emissions.
- By about a difference of 1 million kg C02e, males generate more emissions than females.
- All diets seem to generate a similar level of emission. The Vegetarian and Vegan diet seems to generate a bit less. Males on each diet produce more emissions than females.

### Limitation
- The sample size from the data is too small to generate significant insight into carbon emissions for an average country or city




