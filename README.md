# Excel-Analysis

1.   Introduction
 
The National Health Service's (NHS) effectiveness can be evaluated by taking into account the length of the cancer treatment wait list and the occupancy rate of NHS hospitals. These factors offer helpful perceptions and insights into the effectiveness of the healthcare system, allowing medical professionals to identify areas that need to improve patient care quality.
To ensure that patients receive quick treatment, which is crucial for their survival and recovery, patients with suspected cancer have a maximum 62-day wait period before receiving their first cancer treatment following an urgent referral from their GP. The NHS bed occupancy rate refers to the percentage of hospital beds that are currently occupied by patients in order to assess the NHS's capacity to handle the demand for medical care. Increased bed occupancy can lead to overcrowding, protracted waiting times, and a higher risk of infection, all of which can be detrimental to patient’s well-being.
The information about cancer waiting times and bed occupancy forecasting using linear trend, the linear trend with seasonality, and exponential smoothing is examined in this report to help medical professionals streamline resource distribution, control patient traffic, increase patient satisfaction, and reduce operational costs while maintaining or raising the standard of medical care.
      2. Forecasting Evaluation
 
a)    Forecasting techniques play a critical role in ensuring that NHS Scotland allocates resources effectively and meets the healthcare needs of the population. To measure the success of their forecasting techniques, management at NHS Scotland should consider four key questions.
 
Firstly, they should assess whether they have built an unbiased momentum case that incorporates internal and external data, and end-market trends, and allows for new information to be layered on top.
 
Secondly, they should determine whether they are using a variety of operational indicators and external inputs, such as hospital admissions and waiting times, to better anticipate changes in demand for healthcare services.
Thirdly, companies should assess if they are utilising technology, such as sophisticated analytics tools and artificial intelligence, to provide more precise projections and make better resource allocation decisions.
In order to guarantee that everyone is working towards the same goals and has access to the most recent data and insights, they should evaluate how well they are collaborating across departments.
b)    However, there are several challenges and implications that NHS Scotland may face when applying forecasting approaches and processes.
1.   Data quality is crucial for accurate forecasts, and incomplete or inaccurate data can lead to inaccurate forecasts.
2.   Data privacy and security concerns may arise when sharing patient data across departments or with external partners.
3.   Resistance to change and reluctance to adopt new forecasting approaches could lead to continued use of outdated methods.
4.   Lack of expertise in the healthcare industry and advanced analytics could affect the accuracy of forecasts.
5.   Funding constraints could limit investment in technology and resources required for accurate forecasting.
3. Data Access, Cleaning and Preparation
 
3.1 Cancer Waiting Times with a 62-day waiting standard
The plot represents the percentage of referrals for cancer that have received treatment in Scotland NHS from 2012 to 2021.
Over time, more recommendations have been accepted for treatment on average. However, the data indicate that there are significant differences in the treatment rates across the NHS, with some achieving rates close to 100% and others falling below 80%. The percentages of referrals treated in 2014 by NHS Western Isles (66.66%) and The Golden Jubilee National Hospital (55.55%) both experienced notable drops.    


The covid pandemic struck a portion of the NHS in the year 2020 (period 33–36), which results in a decline in the proportion of referrals treated.This can be mainly due to the high demand for intensive care beds during that period[2]. The dips in the plot show the challenges in cancer treatment which have been a persistent issue in Scotland. For example, a 2021 article in BBC News reported that a cancer patient had to cancel her surgery three times in a month due to a lack of intensive care beds at Ninewells Hospital in Dundee. The article also shows that 407 planned operations were cancelled the day before or on the day due to capacity or non-clinical reasons. To further investigate the percentage of referrals that received treatment, it is essential to consider other factors that may influence treatment rates, hospital size, location, resources etc. It is also crucial for hospitals to adopt efficient & effective referral and treatment protocols to reduce waiting time and improve treatment rates[3].       
              
3.2 Beds by the Board of Treatment and Speciality
￼
 
The plot shows there is significant bed shortages in Medical Oncology department in Scotland. But NHS Tayside got 100% of bed occupancy rate throughout the given period.From the graph it is also noticed that the all Health boards execpt the tayside has a huge in bed occupancy rate during the pandemic time period. But the health board including NHS Lothian, Scotland, NHS Grampian, and NHS Greater Glasgow and Clyde bounces back to their initial occupancy percentages.
As per the article  ‘Bed blocking is crippling Scotland’s NHS’[5] reffered some of the challenges of bed shortages in the Medical Oncology department in Scotland are due to various factors such as continous increase in the number of cancer patients which made the hospitals to allocate all of them. Another reason found is due to high old age population as they needs quick treatment with proper care.In addition to it article mentions about the shortage of staff and strikes going on in many NHS which is a great challenge of patients treatment[1]. Furthermore, COVID Pandemic [4] has also been a majour contribution as the demand for bed was very high and the health boards in scotland don’t have the required amount of bed for the treatment.

4. Time Series Forecasting
 
As the data has a constant mean and the statistical properties are independent of time, the percentage occupancy of hospital beds for the Tayside health board from 2018 to 21 follows a stationary time series. This also applies to Tayside data without 2020. The horizontal pattern and random variations that the time series plot displays are proof that it is stationary. Due to its consistent data and lower Mean Squared Error than other approaches, Tayside's cancer referral data uses exponential smoothing with smoothing constant α = 0.7 when including and omitting 2020.
Because of its general stability, lack of trend or seasonality, and lower Mean Squared Error under exponential smoothing with a smoothing constant of = 0.9 than under linear trend and linear trend with seasonality, the Lothian bed occupancy data is thought to follow a horizontal pattern. However, when we excluded 2020 from the analysis, we could find a linear trend with seasonality (Mean Squared Error is smaller than other approaches). Lothian's cancer referral data use exponential smoothing with a smoothing constant of 0.8 when including and omitting the year 2020 due to its consistent data and lower Mean Squared Error than other techniques.
Since the time series exhibit both trend and seasonality, we could see that the hospital beds data in Grampian follows a linear trend with seasonality while including and excluding the year 2020. Because it has less Mean Squared Error than other methods, the cancer referral data in Grampian follows a linear trend with seasonality while including and excluding the year 2020.

5. Linear Optimisation
 
Decision Variables
·      X1 = Number of staff for 09.00-13.00
·      X2 = Number of staff for 13.00-17.00
·      X3 = Number of staff for 17.00-21.00
·      X4 = Number of staff for 21.00-01.00
·      X5 = Number of staff for 01.00-05.00
·      X6 = Number of staff for 05.00-09.00
Result Variable and Objective
The objective is to minimize the total number of staff required for 24 hours.
·      Z = X1 + X2 + X3 + X4 + X5 + X6
Uncontrollable variables (Constraints)
·      X1 + X2 + X3 >= 36  (for shift 1)
·      X2 + X3 + X4 >= 26 (for shift 2)
·      X3 + X4 + X5 >= 22  (for shift 3)
·      X4 + X5 + X6 >= 16  (for shift 4)
·      X5 + X6 + X1 >= 10  (for shift 5)
·      X6 + X1 + X2 >= 6    (for shift 6)
Justification
The constraint "X1 + X2 + X3 >= 36" means that the total number of staff required for shifts 1, 2, and 3 combined should be equal to or greater than 36. This ensures that there are enough staff available during the morning shift (09:00-13:00) to meet the demand of 36 staff members.
Similarly, the other constraints ensure that the demand for staff is met every 4 hours of the day.

6.   Ethical Issues in Business Intelligence
 
The use of business intelligence (BI) technologies in healthcare, particularly in NHS Scotland, raises significant ethical, legal, and privacy problems that could jeopardise patient information availability, confidentiality, and integrity. They must address critical problems such as patient privacy, informed consent, bias and discrimination, openness and accountability, and data security when using BI systems.
Patient privacy[6] is a critical concern, and must ensure that data is encrypted, access is restricted to approved workers only, and data breaches are reported to the Information Commissioner's Office (ICO) if the BI system collects information that can be used to identify specific patients. Informed consent is also essential, and NHS Scotland must tell patients about data collection and planned uses, as patients have the right to know how their data is being used and to opt-out.
Business intelligence systems can be biased and discriminatory[6], thus NHS Scotland must verify that the algorithms used to train the system are fair and that no patients are singled out for prejudice. Transparency and accountability[6]  are also critical, and must be upfront and honest about how data is used, who has access to it, and if it can be confirmed.
Finally, they must protect data[6] from unlawful access, alteration, or destruction. If the BI system is used to identify patients at high risk of getting a specific disease, the data must be securely maintained, and only approved workers should be provided access.
To summarise, implementing BI tools in NHS Scotland requires careful consideration of ethical, legal, and privacy concerns to guarantee that patient data is properly handled and used. Following these guidelines will increase trust and confidence in the usage of BI technologies in healthcare.
 
7.   References
 
1.     Cancer patient’s surgery was cancelled three times due to ICU beds shortage. (2021). BBC News. [online] 7 Dec. Available at: https://www.bbc.co.uk/news/uk-scotland-tayside-central-59561747.
 
2.     Scottish cancer waiting times performance at record low. (2022). BBC News. [online] 28 Jun. Available at: https://www.bbc.co.uk/news/uk-scotland-61968630.
 
3.     Covid in Scotland: Thousands fewer had cancer treatment. (2021). BBC News. [online] 29 Jun. Available at: https://www.bbc.co.uk/news/uk-scotland-57650825.
 
4.     Scottish hospitals are almost full, says Nicola Sturgeon. (2023). BBC News. [online] 9 Jan. Available at: https://www.bbc.co.uk/news/uk-scotland-scotland-politics-64211393.
 
5.     bed-blocking-is-crippling-scotlands-nhs ,says Lucy Dunn.(2023).The Spectator. [online] 13 Jan. Available at: https://www.spectator.co.uk/article/bed-blocking-is-crippling-scotlands-nhs/
 
6.      Guidance data ethics framework, GOV.UK(2020) [online] 16 Sep. Available at:  https://www.gov.uk/government/publications/data-ethics-framework/data-ethics-framework-2020
 
 
 
