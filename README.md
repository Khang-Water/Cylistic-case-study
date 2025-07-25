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

You can find the datasets I used and the full notebook [here](https://colab.research.google.com/drive/1JKzRUx4oiitu7CzhLbvKFuf2B2G4EDA9?usp=sharing).  

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
Again, you can find the full notebook [here](https://colab.research.google.com/drive/1JKzRUx4oiitu7CzhLbvKFuf2B2G4EDA9?usp=sharing).  

1. **Rename Columns** – Make column names consistent across all datasets.  

2. **Convert Data Types** – Remove commas and convert **tripduration** to numbers.  

3. **Fill Missing Values**  
   - **Gender**: Fill missing values based on the male-to-female ratio.  
   - **Birth Year**: Fill missing values using the median based on user type and quarter.  

4. **Add New Columns**  
   - **Age**: Calculate by subtracting birth year from 2020.  
   - **day_of_week**: Extract from **start_time** to show the day of the week (1=sunday, 7=saturday).  
   - **Age Group**: Categorize users into age groups.  

5. **Merge Data** – Combine all four quarterly datasets into one.  

## Analyze

In this section, we analyze how annual members (subscribers) and casual riders (customers) use the bike-share service differently. By examining quarterly trends, station usage patterns, demographic distributions, and key differences, we aim to provide actionable insights for designing targeted marketing strategies.

### Quarterly Trends in Trip Duration and Ride Count

To understand usage patterns, we first explored trip duration and ride frequency on a quarterly basis.

- **Graph 1: Average Trip Duration per Ride per Quarter**
<img width="1037" height="565" alt="image" src="https://github.com/user-attachments/assets/5d6d35cb-0270-4738-a6c6-2ef79037e03e" />
  Customers consistently exhibit higher average trip durations than subscribers across all four quarters.

- **Graph 2: Total Ride Count by User Type per Quarter**
<img width="748" height="557" alt="image" src="https://github.com/user-attachments/assets/29be51ef-1f4d-4091-a6dd-0f84ca25a3e8" />

  Both customers and subscribers follow similar seasonal trends, with ride counts peaking in Q2 and Q3 and declining in Q1 and Q4.

- **Graph 3: Total Trip Duration by User Type per Quarter**
<img width="748" height="555" alt="image" src="https://github.com/user-attachments/assets/344c33ac-01b4-4a79-9d2b-4fda5852b260" />

  Total trip duration mirrors ride count trends, with significant increases in Q2 and Q3 for both user types.

**Key Insights:**  
- Customers take longer trips on average, suggesting they may use bikes for leisure or tourism rather than routine travel.  
- Both user types ride more frequently during warmer months, indicating a seasonal influence on bike usage.

To investigate the role of weather, we analyzed the correlation between temperature and ride frequency using data from [Visual Crossing](https://www.visualcrossing.com/).
<img width="712" height="531" alt="image" src="https://github.com/user-attachments/assets/9b943710-197b-4088-a364-b84043877412" />

- **Correlation Finding:** A strong positive correlation (0.880) exists between daily average temperature and total rides.  
- **Impact:** For every 1°C increase in temperature, daily rides increase by approximately 495.  

This confirms that warmer weather significantly boosts bike usage for both customers and subscribers, with Q2 and Q3 aligning with Chicago’s warmer seasons and peak tourism periods.

### Station Usage Patterns

We analyzed station data to identify where and when customers and subscribers ride, focusing on stations with the highest and lowest customer usage.

- **Top Customer Stations:**  
  - **Graph 4: Total Rides by User Type by Weekday at Millennium Park**
<img width="1472" height="1064" alt="image" src="https://github.com/user-attachments/assets/1bb0215b-0ba0-454b-98b1-832774c92e1e" />
 
  - **Graph 5: Total Rides by User Type by Weekday at Lake Shore Dr & Monroe St**  
<img width="1493" height="1061" alt="image" src="https://github.com/user-attachments/assets/e01b6546-9d0d-4239-b2a3-415cdeee2234" />

- **Bottom Customer Stations:**  
  - **Graph 6: Total Rides by User Type by Weekday at Wells St & 19th St**
<img width="1472" height="1071" alt="image" src="https://github.com/user-attachments/assets/cb661ab1-0ad5-4442-b116-0bdcd55efa56" />
  
  - **Graph 7: Total Rides by User Type by Weekday at Blue Island Ave & 18th St**  
<img width="1460" height="1072" alt="image" src="https://github.com/user-attachments/assets/7f9c07a0-6581-42a6-9d71-c6b6ce556117" />

**Key Insights:**  
- Across all stations, ride frequency rises in summer and fall (Q2 and Q3).  
- Customers show a clear spike in rides on weekends, particularly at popular stations like Millennium Park and Lake Shore Dr & Monroe St, which are tourist hotspots.  
- Subscribers maintain more consistent ride patterns throughout the week, with higher usage at stations likely tied to commuting routes (e.g., Wells St & 19th St).  

This suggests that customers primarily use bikes for recreational or tourist activities, especially on weekends, while subscribers rely on them for regular, weekday travel, such as commuting.

### Demographic Analysis

We examined gender and age distributions to uncover demographic differences between customers and subscribers.

#### Gender Distribution
- **Graph 8: Pie Charts Showing Gender Distribution for Subscribers and Customers**  
<img width="1294" height="633" alt="image" src="https://github.com/user-attachments/assets/d550e293-389b-453b-b7fc-2430d9cd8d7a" />


**Key Insights:**  
- The proportion of female subscribers is 7% lower than that of female customers.  
- This indicates that women are less likely to opt for annual memberships, possibly due to differing usage preferences or limited marketing appeal.

#### Age Distribution
- **Graph 9: Pie Chart Showing Age Distribution of Customers and Subscribers**  
<img width="1306" height="497" alt="image" src="https://github.com/user-attachments/assets/d9eb311e-ffc0-4400-8ebe-740b6a61d608" />

**Key Insights:**  
- The 26-35 age group dominates both user types, but it’s more pronounced among customers (81%) compared to subscribers (50.5%).  
- Riders aged 36 and older are more likely to be subscribers than customers.  

Younger riders (26-35) appear more inclined to use bikes casually, while older riders (36+) prefer subscriptions, possibly reflecting more established commuting habits.

### Comparison of Customers vs. Subscribers

The table below summarizes the key differences between customers and subscribers based on the analysis:

| **Category**             | **Customers**                                      | **Subscribers**                                      |
|--------------------------|---------------------------------------------------|----------------------------------------------------|
| **Trip Duration**        | Longer average trip durations                     | Shorter average trip durations                     |
| **Ride Frequency**       | More rides on weekends                            | Consistent rides throughout the week               |
| **Seasonal Usage**       | Peaks in Q2 and Q3                                | Peaks in Q2 and Q3                                 |
| **Station Usage**        | High usage at tourist-heavy stations (e.g., Millennium Park) | High usage at commuting-related stations (e.g., Wells St & 19th St) |
| **Gender Distribution**  | Higher proportion of females                      | Lower proportion of females                        |
| **Age Distribution**     | Predominantly 26-35 years old (81%)               | More evenly distributed, higher proportion of 36+ years old (50.5% in 26-35 group) |

**Key Insights:**  
- **Customers** are more likely to use Cyclistic bikes for leisure or tourism, as evidenced by longer trips, weekend spikes, and activity at tourist-friendly stations.  
- **Subscribers** demonstrate a pattern of regular, utilitarian use, with shorter, more frequent trips throughout the week and a broader age range, suggesting commuting or daily travel needs.  

### Conclusion

This analysis highlights distinct usage patterns between annual members and casual riders. Customers lean toward recreational use, influenced by weather and weekend availability, while subscribers exhibit consistent, practical usage tied to routines like commuting. These insights provide a foundation for crafting marketing strategies to convert casual riders into annual members by addressing their specific needs and preferences.
  

## Share & Act
I used Tableau to recreate graphs and you can view it [here](https://public.tableau.com/views/CyclisticDashboard_17533905637030/Home?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link) or the [PDF](https://github.com/Khang-Water/Cylistic-case-study/blob/main/Cyclistic%20Dashboard.pdf) version

<img width="1442" height="1170" alt="image" src="https://github.com/user-attachments/assets/02f54a14-e46c-464e-a307-173fe257c9dd" />
<img width="1439" height="1155" alt="image" src="https://github.com/user-attachments/assets/a689a101-5cf2-4044-adbb-135cdce9debb" />
<img width="1436" height="1170" alt="image" src="https://github.com/user-attachments/assets/a9c2a0ae-7d03-4928-847e-06f16426d2ec" />

### Recommendations 

#### 1. Annual Plan for Weekday Commuters: Annual subscription with unlimited weekday rides for commuters
- **Problem Solved**: Subscribers ride more on weekdays, indicating commuting patterns. This plan encourages casual riders who commute to switch from single-ride or day passes to annual memberships

#### 2. Annual Plan for Summer & Autumn Only: Seasonal subscription for Q2 and Q3, priced lower than full-year plans.
- **Problem Solved**: Targets casual riders active in warmer months (Q2, Q3), with a 0.880 temperature-ride correlation.

#### 3. Plan Only for Weekends: Unlimited weekend rides with discounts for longer trips.
- **Problem Solved**: Casual riders predominantly use bikes on weekends at tourist-heavy stations like Millennium Park. This plan targets their recreational habits, making membership more attractive without a full-week commitment.

#### 4. Discounts for Women on Special Days: Offer subscription discounts on days like International Women’s Day, promoted through targeted digital campaigns.
- **Problem Solved**: Addresses 7% lower female subscriber proportion.



