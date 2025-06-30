# Google Data Analytics Capstone: Cyclistic Bike-Share Analysis Case Study

- [Welcome](#welcome)
- [Scenario](#scenario)
- [Characters and Teams](#characters-and-teams)
- [About the Company](#about-the-company)
- [Ask](#ask)
- [Prepare](#prepare)
- [Exploratory Analysis](#exploratory-analysis)
- [Data Cleaning Process](#data-cleaning-process)
- [Analyze](#analyze)
- [Share & Act](#share--act)

## Welcome
Welcome to the Cyclistic bike-share analysis case study! In this case study, you work for a fictional company, Cyclistic, along with some key team members. In order to answer the business questions, follow the steps of the data analysis process: Ask, Prepare, Process, Analyze, Share, and Act. Along the way, the Case Study Roadmap tables — including guiding questions and key tasks — will help you stay on the right path.

## Scenario
You are a junior data analyst working on the marketing analyst team at Cyclistic, a bike-share company in Chicago. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, your team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, your team will design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve your recommendations, so they must be backed up with compelling data insights and professional data visualizations.

## Characters and Teams
- **Cyclistic**: A bike-share program that features more than 5,800 bicycles and 600 docking stations. Cyclistic sets itself apart by also offering reclining bikes, hand tricycles, and cargo bikes, making bike-share more inclusive to people with disabilities and riders who can’t use a standard two-wheeled bike. The majority of riders opt for traditional bikes; about 8% of riders use the assistive options. Cyclistic users are more likely to ride for leisure, but about 30% use the bikes to commute to work each day.
- **Lily Moreno**: The director of marketing and your manager. Moreno is responsible for the development of campaigns and initiatives to promote the bike-share program. These may include email, social media, and other channels.
- **Cyclistic marketing analytics team**: A team of data analysts who are responsible for collecting, analyzing, and reporting data that helps guide Cyclistic marketing strategy. You joined this team six months ago and have been busy learning about Cyclistic’s mission and business goals—as well as how you, as a junior data analyst, can help Cyclistic achieve them.
- **Cyclistic executive team**: The notoriously detail-oriented executive team will decide whether to approve the recommended marketing program.

## About the Company
In 2016, Cyclistic launched a successful bike-share offering. Since then, the program has grown to a fleet of 5,824 bicycles that are geotracked and locked into a network of 692 stations across Chicago. The bikes can be unlocked from one station and returned to any other station in the system anytime.

Until now, Cyclistic’s marketing strategy relied on building general awareness and appealing to broad consumer segments. One approach that helped make these things possible was the flexibility of its pricing plans: single-ride passes, full-day passes, and annual memberships. Customers who purchase single-ride or full-day passes are referred to as casual riders. Customers who purchase annual memberships are Cyclistic members.

Cyclistic’s finance analysts have concluded that annual members are much more profitable than casual riders. Although the pricing flexibility helps Cyclistic attract more customers, Moreno believes that maximizing the number of annual members will be key to future growth. Rather than creating a marketing campaign that targets all-new customers, Moreno believes there is a solid opportunity to convert casual riders into members. She notes that casual riders are already aware of the Cyclistic program and have chosen Cyclistic for their mobility needs.

Moreno has set a clear goal: Design marketing strategies aimed at converting casual riders into annual members. In order to do that, however, the team needs to better understand how annual members and casual riders differ, why casual riders would buy a membership, and how digital media could affect their marketing tactics. Moreno and her team are interested in analyzing the Cyclistic historical bike trip data to identify trends.

## Ask

Three questions will guide the future marketing program:  
1. How do annual members and casual riders use Cyclistic bikes differently?  
2. Why would casual riders buy Cyclistic annual memberships?  
3. How can Cyclistic use digital media to influence casual riders to become members?  

Moreno has assigned you the first question to answer: **How do annual members and casual riders use Cyclistic bikes differently?**

### Guiding Questions
- How do annual members and casual riders use Cyclistic bikes differently?

### Stakeholders
- **Lily Moreno**: Director of Marketing  
- **Marketing Analytics Team**  
- **Cyclistic Executive Team**

### Business Task
Analyze data to show the differences of how annual members and casual riders use Cyclistic bikes.

## Prepare
Are there issues with bias or credibility in this data? Does your data ROCCC?
- **Reliable**: Data comes from a reputable source (Motivate International Inc.).
- **Original**: This is primary data directly from Cylistic’s operations, not from a third party.
- **Comprehensive**: It covers full features for providing a complete picture of usage patterns.
- **Current**: The 4 quarterly datasets from 2019 may be enough to reflect relevant trends.
- **Cited**: The data is publicly available under a license from Motivate International Inc.
- **Bias Concern**: The data may underrepresent certain groups, such as cash versus digital payments or variations across geographic regions.

## Exploratory Analysis  

You can find the datasets I used and the full notebook [here](https://www.kaggle.com/code/khanglminhh/cyclistic-case-study).  

For this analysis, I used Python to explore the data.  

### Dataset Overview  
All 4 quarterly datasets consists of **3,818,004 rows** and covers trips recorded from **January 1, 2019, to December 31, 2019**. It includes **12 columns** with details about each trip:  

- **trip_id**: Unique identifier for each trip  
- **start_time**: Date and time when the trip started  
- **end_time**: Date and time when the trip ended  
- **bikeid**: Unique identifier for the bike used  
- **tripduration**: Total duration of the trip  
- **from_station_id**: ID of the station where the trip started  
- **from_station_name**: Name of the station where the trip started  
- **to_station_id**: ID of the station where the trip ended  
- **to_station_name**: Name of the station where the trip ended  
- **usertype**: User type (Subscriber or Customer)  
- **gender**: User's gender (if available)  
- **birthyear**: User's birth year (if available)

## Data Cleaning Process  
Again, you can find the datasets I used and the full notebook [here](https://www.kaggle.com/code/khanglminhh/cyclistic-case-study).  

1. **Rename Columns** – Make column names consistent across all datasets.  

2. **Convert Data Types** – Remove commas and convert **tripduration** to numbers.  

3. **Fill Missing Values**  
   - **Gender**: Fill missing values based on the male-to-female ratio.  
   - **Birth Year**: Fill missing values using the median based on user type and quarter.  

4. **Add New Columns**  
   - **Age**: Calculate by subtracting birth year from 20202020.  
   - **day_of_week**: Extract from **start_time** to show the day of the week (1=sunday, 7=saturday).  
   - **Age Group**: Categorize users into age groups.  

5. **Merge Data** – Combine all four quarterly datasets into one.  

## Analyze  

### **Trip Duration & Ride Count by Usertype (Quarterly)**  
- **Graph 1**: Total trip duration by user type per quarter.
![image](https://github.com/user-attachments/assets/f4a4113a-2cd6-4018-a8ae-f8328294ac96)

- **Graph 2**: Total ride count by user type per quarter.
![image](https://github.com/user-attachments/assets/b818f83b-8d04-4343-9d35-3cd8f472a2c1)
 

**Analysis:**  
- Customers generally had equal or longer trip durations than subscribers. In **Q3**, customer trip duration was significantly higher.  
- Subscribers took far more trips than customers in every quarter.  
- **Possible Explanation:**  
  - **Subscribers**: Likely use bikes for commuting, leading to frequent but shorter trips.  
  - **Customers**: More likely use bikes for leisure or exercise, resulting in longer trips but fewer in number.  

### **Trip Duration & Ride Count by Usertype (Weekdays vs. Weekends)**
- **Graph 3**: Total ride count per weekday (Customer vs. Subscriber).
![image](https://github.com/user-attachments/assets/2d7937ba-a09c-41e0-aa1f-c447b86886d3)

- **Graph 4**: Total trip duration per weekday (Customer vs. Subscriber).
![image](https://github.com/user-attachments/assets/df4706e5-9819-4e77-8e2b-ac4f82a59c55)

**Analysis:**  
- Subscribers ride more from **Monday to Friday** but drop significantly on weekends, indicating primary use for commuting.  
- Customers ride more on **weekends**, suggesting they use bikes mainly for leisure or exercise.  
- Subscribers have **shorter weekend trip durations**, while customers maintain **longer durations throughout the week**, supporting the idea that they use bikes for exercise.  

### **Gender Distribution by Usertype**  
- **Graph 5**: Pie charts showing gender distribution for subscribers and customers.  
![image](https://github.com/user-attachments/assets/6017c369-5fef-4155-bb9d-9595f4b6e53a)

**Analysis:**  
- The proportion of **female subscribers** is **7% lower** than that of female customers.  

### **Age Distribution of Riders**  
- **Graph 6**: Pie chart showing age distribution of customers and subscribers.
![image](https://github.com/user-attachments/assets/ce4673fe-48cb-4caa-a9e7-644b8fea9e0c)

**Analysis:**  
- The **26-35 age group** has the most subscribers. However, **81% of customers** fall into this category, compared to only **50.5% of subscribers**.  
- Riders aged **36+** are more likely to subscribe than be customers.

### **Comparison of Customers vs. Subscribers**  

| **Category**             | **Customers**                                      | **Subscribers**                                      |
|--------------------------|---------------------------------------------------|----------------------------------------------------|
| **Trip Duration**        | Longer trips, especially in **Q3**                | Shorter trips overall                              |
| **Ride Count**          | Fewer trips compared to subscribers               | Significantly more trips in every quarter        |
| **Weekday vs. Weekend**  | Ride **more on weekends** for leisure/exercise    | Ride **mostly on weekdays** for commuting        |
| **Trip Duration Pattern** | **Longer trips throughout the week** (exercise)  | **Shorter trips on weekends**                     |
| **Gender Distribution**  | Low female proportion (24.9%)                         | **7% fewer female riders** than customers       |
| **Age Distribution**     | **81% are 26-35 years old**                        | **50.5% are 26-35 years old**, more 36+ subscribers |
  

## Share & Act
I used Tableau to recreate graphs and made a short representation [here](https://docs.google.com/presentation/d/1I0eYG8BllsmwhvomrTvpzf6fqF0H2Pew/edit#slide=id.p1)

### Recommendations 

#### Annual Plan for Weekday Commuters  
- A yearly subscription for those who bike to work or school five days a week. This makes commuting easier and more affordable, attracting more workers.  

- **Problem Solved:** Most subscribers ride more on weekdays than weekends. This plan encourages regular commuters to commit to a subscription instead of relying on single rides.  

#### Annual Plan for Regular Exercisers  
- A special plan for frequent riders who use bikes for exercise.  

- **Problem Solved:** Many customers ride for exercise but don’t subscribe. This plan could turn them into long-term users.  

#### Discounts for Women on Special Days  
- Offer special discounts on days like International Women’s Day to attract more female subscribers and encourage them to ride.  

- **Problem Solved:** The percentage of female subscribers is lower than female customers. This helps close that gap.  

#### Rewards for Frequent Riders  
- Provide benefits like free rides or discounts for loyal users.

- **Problem Solved:** Older age groups tend to subscribe more, but there is a big gap in the 36-45 age group. This incentive could encourage more sign-ups.  




