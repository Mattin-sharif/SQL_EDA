# Strategic Analysis Report: Analysis of Customer Demographics and Preferences in Insurance Product selection

## Introduction

There is a paradigm shift seen towards data-centric strategies in contemporary insurance companies. In order to gain a competitive edge in the market, insurance companies recognize the value of using data analytics. This report uncovers and explores customer behavior preferences and patterns through the implementation of advanced data analytics across different insurance products and marketing channels. The company's strategic planning and marketing tactics are guided by these insights, which align with current industry trends (Koutsomitropoulos et al., 2017).

This project provided a sophisticated analytical framework that includes variances in customer characteristics and preferences. The project was designed to capitalize on the strengths of both technologies and to take advantage of the company's transition from SQL to R for data analysis. For a thorough analysis of data, R was leveraged to identify and rectify data quality issues including missing values and outliers to ensure data reliability and integrity (Reda et al., 2020).
The data was exported to excel after being rectified by R for data quality issues. As a bridge between Excel and Microsoft Access, this step allowed us to reimport the data to Microsoft Access where it was used for further analysis and manipulation. The reason for choosing Microsoft is that it provides seamless integration with the existing system and aligns it with the company’s existing data infrastructure.

An in-depth descriptive analysis were performed in Microsoft Access. In order to facilitate a comprehensive examination of customer data across a variety of dimensions, an analytical base table (ABT) was created. The descriptive analysis conducted highlights key insights about customer patterns and preferences across preferred communication channels and different insurance products. This analysis reflects the crucial role of data analytics in modern businesses. The findings of the analysis are expected to guide strategic marketing decisions and enhance customer engagement strategies (Baig et al., 2021).

This report outlines the methodologies and detailed processes used in the project. A comprehensive discussion of database development in Microsoft Access is highlighted in section 2.1. It provides the rationale behind design choices as well as an in-depth look at the database’s structure. Furthermore, it examines potential limitations by critically evaluating the technology used and offers opportunities for future improvements.

The Data Quality Report, presented in Section 2.2, provides an overview of the data quality challenges that were identified, along with the methodologies that were applied in R and SQL to solve them. This part explains how data accuracy and consistency were achieved in the project.
The final section of the report, Section 3.0, summarizes the key findings derived from the descriptive analysis carried out in Access. It also offers interpretations and implications backed up by industry sources along with the results. Considering the current analysis limitations and suggesting future research and exploration pathways, this section concludes with actionable recommendations for the insurance company.

The main aim of this report is to equip insurance company with a strategic roadmap and sophisticated analytical framework to foster sustainable growth, boost data analytical capabilities and support decision-making.


## Database Documentation

### Database development in Microsoft Access

To leverage and harness the power of advance data analytics in the company, the first critical step was the development of a structured and efficient database. The process started with the importation of different tables into SQL environment. This crucial step laid the ground for all subsequent analytical endeavors and tasks.
The imported datasets regarding customers and insurance policies were carefully processed to ensure data quality and integrity before joining the tables. The process involved the implementation of distinct function on every table to remove any duplicate rows (observations) in the tables. This strategic move not only insured the data quality but also laid the foundation of accurate and reliable data analysis.

The database was developed comprising of four primary tables, which were cleaned earlier: customer_NoDup, health_NoDup, motor_NoDup, and travel_NoDup. Each table served as a unique purpose in contributing to the unique and comprehensive customer profile.

customer_NoDup: Serving as a keystone of the database, this table holds unique customer information. Having a primary key as customerID and three foreign keys as HealthID, TravelID, and MotorID used to join different tables with the customer table. The table contain customer demographic like age, gender to location and furthermore, preferred 
communication channels, it offered a comprehensive and panoramic view of the customer. As exhibited in the figure below.

![image](https://github.com/user-attachments/assets/38c2d263-eede-4952-86a9-4c3f39438378)

Figure 1.1-Customer Table

customer_NoDup, health_NoDup, motor_NoDup, travel_NoDup: These tables dive deeper in the specifics of each insurance policies. They capture data regarding each insurance policy types – health, motor, and travel - including detailed aspects such as policy duration and furthermore, in motor policy

it gives more details like vehicle value and claim history. Overall each table is having its own primary key which is the foreign key in the customer table. As exhibited in the figure below.

![image](https://github.com/user-attachments/assets/b6cddbae-5c9d-47bc-b6c3-424136751f13)

Figure 1.2-Motor Policy Table

![image](https://github.com/user-attachments/assets/3c2459c0-bb08-4367-b7b0-9293d1fd088d)

Figure 1.3-Health Policy Table

![image](https://github.com/user-attachments/assets/53b58f24-2f3c-47e3-a095-d578012cb2c7)

Figure 1.4-Travel Policy Table

The Analytics base table was hence created incorporating the customer demographics and their respective insurance policy offering a more granular view of the customer patterns having different policies. Only the specific columns needed for later analysis were incorporated in the ABT instead of choosing all the columns. To synchronize the data into a cohesive unit in Analytical base table, a series of left joins were executed, initiated from customer_NoDup table. All the other three tables were left joined with customer – retaining the rows of customer table which means that customerID is our ABT table is a primary key. The figure below exhibits the entity relationship diagram.

![image](https://github.com/user-attachments/assets/18e39ae9-fe6b-47de-8728-543a39dc76be)

Figure 1.5-Entity – Relationship Diagram

However, the development of Analytics base table was challenging considering the primary challenge of matching the keys between the tables. Any discrepancy in the primary and foreign key could potentially lead to incomplete data, effecting the analysis of customer patterns and behaviors.
To counter this challenge a rigorous data validation and cleaning process was incorporated to remove any duplicated observation in each table before joining the tables (Fan and Greets, 2022).

Furthermore, the choice of Microsoft Access, which might be suitable for current needs might pose scalability challenges in the future as the volume and complexity of the data increases. Incorporating more robust and scalable systems like SQL server or any cloud based data management platform could cater the scalability needs. Moreover, the integration of more advance statistical analysis tools like R would be a strategic move. This will not only align with the industry evolving technological trends but also the give an advantage to leverage the powerful toolkit to better understand the data patterns and trends and most importantly to identify data quality issues (Kabacoff, 2022).

In summary, the development of ABT stands as a testament of a structured approach to blend data from different tables into a whole unit to set grounds for insightful analysis that could drive strategic decision making and data driven culture within the company.

### Data Quality Report

In the dictionary of data analytics, the saying “quality over quantity” holds eminent importance. Recognising this extensive data quality analysis is the integral part of this project. The process was divided in two phases. Initial data cleaning in Access followed by an extensive quality analysis and resolution in R, a strategy which leverages the strengths of both the tools.

Initial data cleaning in SQL Access: The foundation of the data quality was laid in the Analytical base table (ABT_v1) creation process were pre-joining data quality was carried using the distinct function to filter out the distinct rows in every table before joining the tables. Descriptive statistics were carried out to gain insights into data structure and data integrity. The queries highlighted anomalies in the key variable. In Gender column, variation in categorical data were identified (e.g., ‘f’ and ‘female’, ‘m’ and ‘male’). Similarly, in ComChannel column also exhibited such discrepancies (‘E’ for ‘Email’, ‘p’ for ‘Phone’, ‘S’ for ‘SMS’). Addressing these data quality issues was crucial as it may affect and skew the analysis. However, considering the limitation of SQL where it was difficult for us to identify the outliers in the Age column. As exhibited in the tables below.

![image](https://github.com/user-attachments/assets/ce3ac4c6-3646-46ce-868a-fddb5ca18cb9)

Figure 2.1-Initial Descriptive of CommChannel

![image](https://github.com/user-attachments/assets/7756e9fa-f04c-4032-99ae-7a7ecc59de3e)

Figure 2.2- Initial Descriptive of Gender

![image](https://github.com/user-attachments/assets/889824a8-441c-4392-b5fa-4f5938054a5f)

Figure 2.3- Initial Descriptive of Age Across insurance type

Our focus shifted to data quality analysis in R.
Data quality analysis in Resolution in R: Considering the limitations of SQL Access to do an extensive data Quality analysis (Gu et al. 2021). Our focus shifted to R, a powerful and more robust statistical tool. Additionally, having capabilities of Data management. The initial step involved importing the table, converting categorical data to factors for the identification of any anomalies in categorical data, and then Creating an Analytical base table (ABT_v1) using distinct rows of every table. The Summary() function provided an overview of data revealing issues like outliers in the Age column.

![image](https://github.com/user-attachments/assets/9038eef8-5a7a-4d04-9940-fd5b7e39b56d)

Figure 2.4-Box Plot showing Outliers of Age
Furthermore, Boxplot() function identified three extreme values in the Age column, the outliers were replaced with median value of the age. Median was used based on its resistance to skewness compared to the mean value. This step was crucial for the accuracy of the statistical analysis which might have get distorted if not resolved. Moreover, SQL Access does not have a build in function to calculate the median value. The table below show the corrected outliers in Age column.

![image](https://github.com/user-attachments/assets/b7249420-6dac-4d98-944a-90348922a98a)

Figure 2.5- Box Plot without Outliers of Age
The other two columns ComChannel and Gender column went standardization – likewise done in SQL access. Categories representing similar information were merged together to ensure reliability of gender and communication specific analysis.
Post this Data Quality resolution, second Analytical base table (ABT_v2) was created filtering out any customer data with no insurance policy. This filtration of rows insured the focus to remain on the customers who are relevant.
Preventing Future Data Quality Issues: The Company could establish strict data entry protocols and regular training sessions for professional to reduce human error. Automated data collection, where feasible can be implemented to avoid human interaction with the data. Additionally, advance data validation techniques could be implemented to not allow the entry of data in the wrong format at the first place to maintain high data quality standards.
In conclusion, Implementation of this meticulous approach to data quality will not only boost the reliability of the analysis but have also set the standard for future data management practices.

## Insights Report

The data driven exploration in SQL have unveiled multi-layered insights into customer preferences across different insurance products and communication channels. This analysis is critical for redefining the strategic marketing and customer engagement strategies.
Insurance Age Analysis.

![image](https://github.com/user-attachments/assets/ca39d072-0d5c-457e-ba84-d32aa3607428)

Figure 3.1-Age distribution across Insurance types

The distinct insurance preferences revealed by the analysis exhibits that motor insurance is favored by a mature demographic (41.69 of average age). While, the health insurance is favored by the older segment with higher (47.28) average age (Giles, 2022). The travel insurance pleads to a younger generation with the average age of 38.66 years and a notably wider range distribution of age. These results propose opportunities for custom marketing strategies to align with every age group specific insurance needs and preferences.

**Communication preference across Gender**
![image](https://github.com/user-attachments/assets/1061d70c-a005-40d7-905d-643716ade125)

Figure 3.2- Communication preference across Gender
The data exhibits a nuanced landscape where females marginally favor email (887) and SMS (406) over males (877 and 351 respectively), suggesting an incline towards digital communication mediums. Whereas, Phone is equally popular in both the genders (782) indicating its continued relevance as a communication channel.

**Age and insurance type correlation**
![image](https://github.com/user-attachments/assets/c6bec657-14dc-40e9-afd1-cf5e331187ab)

Figure 3.3- Age and insurance type correlation

The age wise analysis present a fascinating big picture: the youngest age group (18-30) shows the highest number of travel policies subscribed (874), reflecting a possible attraction to travel or more transient lifestyle. On the other hand, the 46-60 age bracket demonstrates a strong preference for motor policies (1611), due to the people in the age group being more financially stable and looking for investments. Similarly, health insurance is also popular in 45-60 age bracket (1453), indicated due to greater health consciousness with increasing age (Giles, 2022).

**Location Based divide in Communication Channels and Insurance products**
![image](https://github.com/user-attachments/assets/4f729ceb-e5e8-4f97-90b0-57a505753bdb)

Figure 3.4- Location Based divide in Communication Channels
![image](https://github.com/user-attachments/assets/6273cf75-1ec8-4ca0-b497-a48a59232166)

Figure 3.5- Location Based divide on Insurance products

Urban areas exhibits a higher engagement with all the communication channels, especially email (1197) and SMS (500), compared to rural area, suggesting greater digital connectivity and better infrastructure in Urban areas. Similarly, urban customers hold more insurance policies across all the three different policy. Motor policies (1908) and health policies (1339) being the most predominant, reflecting a higher awareness of health and better infrastructure as compared to rural areas.

**Communication effectiveness by age group**
![image](https://github.com/user-attachments/assets/82d07536-9145-41e1-ba18-7d89201ff607)

Figure 3.6- Communication effectiveness by age group
Email is the preferred communication channel among 18-30 age group with a count of (626). Whereas, Phone communication is quite popular in 46-60 age group (932) and SMS is in the younger cohort (536). This signifies the importance of tailor made marketing strategies to target each age group to get more leads and subsequently more conversion for the company (Pieterson et al., 2020).

**Gender difference in policy type**
![image](https://github.com/user-attachments/assets/1f30d307-1ee0-4edc-9c27-055e876cc651)

Figure 3.7- Gender difference in Health policy type
![image](https://github.com/user-attachments/assets/8744c6e1-aa89-45a6-a2d4-9dc8bb848167)

Figure 3.8- Gender difference in Motor policy type
![image](https://github.com/user-attachments/assets/ffe8c78a-faa3-44ef-b3eb-0dd1c54fa0c8)

Figure 3.9- Gender difference in Travel policy type

Surprisingly, females hold more health (1129) and motor policies (1697) than males. There is a slight difference in the policy count indicating an equal awareness, similar travel habit and equal perception of risk regarding health across different genders.

**Age specific policy preference**
![image](https://github.com/user-attachments/assets/9d1c2703-31ad-42b1-9af4-21ca6d1d1739)

Figure 3.10- Age specific Health policy preference
![image](https://github.com/user-attachments/assets/2b3aa1f9-7184-4ae4-8351-341c51769dfe)

Figure 3.11- Age specific Motor policy preference
![image](https://github.com/user-attachments/assets/6deaae9f-7d78-45d8-aca4-82dfa61a5cf0)

Figure 3.12- Age specific Travel policy preference

The analysis of insurance types within are groups suggests that younger cohort 18-30 are most likely to buy a bundled motor policy (851). For the health insurance, age group does not exhibits any trend in the data across different health product types. However the oldest cohort 60+ shows the least number of policies which might be due to the availability of another healthcare facility for older people.

**Preference of policy levels by gender and age**

Choosing the specific policy type vary across different genders, with females favoring more to health policy across level 1 and level 3 respectively. For the travel insurance, business and standard is evenly distributed among different genders. Moreover, females slightly leading in the business category.
An age wise analysis of the health policies indicates that the majority of the customers opt for level 2 health policy were in age bracket of 46-60 . Whereas, the youngest and the oldest cohort shows a contrasting tendency for level 1 and level 3 insurance type. This indicated the need of awareness about the policy types at different life stages and this could also exhibit different health coverage needs.

## Strategic recommendations and implications

As referred in earlier literature (Mau et al., 2015). The findings from the analysis shows a multilayered approach for the insurance company. The company could redefine their communication mix, prioritize their digital communication channels for younger generation. While on the other hand, maintain traditional means of communication for the older people. Furthermore, the data analysis supports a gender based approach towards redefining the product strategy, emphasizing motor and health insurance products for the female customers and maintaining a balanced focus on the travel products across both genders.
To address the difference among rural and urban customers there is a big gap. The company could rely on digital outreach programs to increase the engagement and do partnerships that can bridge gaps between the different demographic groups

## Limitations and future directions

The analysis provided the actionable insights but still the limitations exist as this analysis only focus on the visual trend within the data without the development of any causation and correlation among different variable (Foster et al., 2016). Further analysis could include quantitative research to enrich these findings. Moreover, the company should invest in predictive analytics and machine learning model to better understand the trends in the data and the customer behaviors. Such proactive measure can empower the company to have a competitive advantage in the market, ensuring long term growth and customer satisfaction.

## Conclusion of the findings

Summing up, the findings present a compelling narrative of insurance company’s current market position and customer share. With these insights as an action plan the company can well position its defined marketing and communication strategies according to the demographic characteristics of the customers. The recommendation given will empower the company towards a more informed decision making to achieve suitability and growth.


## References
1. Baig, M.R., Govindan, G. and Shrimali, V.R., 2021. Data Science for Marketing Analytics: A practical guide to forming a killer marketing strategy through data analysis with Python. Packt Publishing Ltd.
2. Fan, W. and Geerts, F., 2022. Foundations of data quality management. Springer Nature
3. Foster, E.C., Godbole, S., Foster, E.C. and Godbole, S., 2016. Some Limitations of SQL. Database Systems: A Pragmatic Approach, pp.339-345.
4. Giles, S.E.T., 2022. Policy and Health (In) Equities among Native Elders (Doctoral dissertation, Virginia Tech).
5. Gu, R., Qi, Y., Wu, T., Wang, Z., Xu, X., Yuan, C. and Huang, Y., 2021. SparkDQ: Efficient generic big data quality management on distributed data-parallel computation. Journal of Parallel and Distributed Computing, 156, pp.132-147.
6. Kabacoff, R., 2022. R in action: data analysis and graphics with R and Tidyverse. Simon and Schuster.
7. Koutsomitropoulos, D.A. and Kalou, A.K., 2017. A standards-based ontology and support for Big Data Analytics in the insurance industry. Ict Express, 3(2), pp.57-61.
8. Mau, S., Cvijikj, I.P. and Wagner, J., 2015. Understanding the differences in customer portfolio characteristics and insurance consumption across distribution channels. Working Paper presented at the WRIEC in Munich.
9. Pieterson, W.J. and Ebbers, W.E., 2020. Channel choice evolution: An empirical analysis of shifting channel behavior across demographics and tasks. Government Information Quarterly, 37(3), p.101478.
10. Reda, O., Sassi, I., Zellou, A. and Anter, S., 2020, September. Towards a data quality assessment in big data. In Proceedings of the 13th International Conference on Intelligent Systems: Theories and Applications (pp. 1-6).

