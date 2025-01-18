# PWC Power BI Virtual work experience- Call Centre Trends

An interactive Call Center dashboard using power bi to empower insight and KPIs to enhance performance and customer experience!

Possible KPIs include :

- Agent’s performance 
- Overall customer satisfaction
- Overall calls answered/abandoned
- Average speed of answer


## Contents :

- [Datasource](https://github.com/maiimamdooh/Call-Center-Dashboard/blob/main/01%20Call-Center-Dataset%20(1).xlsx)
- [Data prepration]()
- [Data Analysis]()
- [Dashboard]()
- [Insights]()

## Datasource :

Dataset used for this task was presented by [Pwc](https://www.pwc.ch/en/careers-with-pwc/students/virtual-case-experience.html) and call centre trends dataset:

Dataset: [Call Center Data](https://github.com/maiimamdooh/Call-Center-Dashboard/blob/main/01%20Call-Center-Dataset%20(1).xlsx)

## Data Preparation:

Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.

- `Call Center trends dataset` which has `10 columns and 5000 rows` of observation

Data Cleaning for the dataset was done in the power query editor as follows:

- Removed Unnecessary rowa and column
  
- Handling null value in some columns `Speed of answer`,`Talk duration` and `Satisfaction rate`
  replace with `0` as this rows are represented the unanswered calls
  
- Each of the columns in the table were validated to have the correct data type
  
## Data Analysis (DAX) :

 And then dataset was cleaned and transformed, it was ready to the analysis.
 We used dax function to do some measures to used in visualization such as :

- `Answered calls` = 
COUNTX(
    FILTER(
        'Call Center Dataset',
        'Call Center Dataset'[Answered (Y/N)] = "Y"
    ),
    'Call Center Dataset'[Answered (Y/N)]
)

- `Unanswered calls` = 
COUNTX(
    FILTER(
        'Call Center Dataset',
        'Call Center Dataset'[Answered (Y/N)] = "N"
    ),
    'Call Center Dataset'[Answered (Y/N)]
)

- `Resolved calls` = 
COUNTX(
    FILTER(
        'Call Center Dataset',
        'Call Center Dataset'[Resolved] = "Y"
    ),
    'Call Center Dataset'[Resolved]
)

- `Unresolved calls` = 
COUNTX(
    FILTER(
        'Call Center Dataset',
        'Call Center Dataset'[Answered (Y/N)] = "Y" &&
        'Call Center Dataset'[Resolved] = "N"
    ),
    'Call Center Dataset'[Resolved]
)
## Data Visualization (Dashboard) :

Data visualization for the data analysis was done in Microsoft Power BI Desktop:

Dashboard: [View Dashboard](https://github.com/maiimamdooh/Call-Center-Dashboard/blob/main/call%20center%20dashboard.pbix) 

| ----------- |
| ![Overview](https://github.com/user-attachments/assets/d1a9f462-8797-4ee8-bf14-0d2c02db95e6) |

| ![agent performance](https://github.com/user-attachments/assets/fbdb2ed3-7881-405c-9c79-373454214965) |

## Insights :

As shown by Data Visualization, It can be deduced that:

- Most of the satisfaction ratings from each call are 3 and 4.
- The average satisfaction rating has decreased over the span of three months. January brought the highest satisfaction rating and march the lowest.
- The percentage of issue resolved in January was the highest, with a dip in February. It increased again in march.
- The average speed of answer by `Joe` is the highest.
- The call resolution rate of `Jim` is the highest, even though the average speed of his answers is lower compared to those of Joe, Martha and Dan. The call answered by - him are also higher than the average number of calls answered.
- `Becky` speed of answer is the lowest among all, and her rate of calls resolved is higher. She is in the 5th position in the call resolution rate. 
- `Martha` has the highest  speed of answered in the sec
