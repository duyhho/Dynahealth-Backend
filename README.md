# DynaHealth Backend (Data Collection, Processing, Training, and Deployment)
Authors: Duy Ho, Hieu Trinh, Nhung Tran

Award Page: https://info.umkc.edu/hack-a-roo/spring-2021-it-track/

Note: For frond-end, please visit: https://github.com/ngchieu857529/hackaroo_spring_2021

# Motivation

Health insurance is one of the most important protections for an individual. Having a health insurance plan not only helps ease the mind but also covers a significant amount of cost in critical or unexpected conditions such as illness and accident.
However, not everyone has easy access to and knowledge about health insurance in a convenient and informative way. Thus, users may not have sufficient awareness about the topic to make a decision.
Moreover, data from many sources are not represented in a transparent or meaningful manner, leading to uncertainty and confusion.
# Overview

![image](https://github.com/duyhho/Dynahealth-Backend/assets/17374092/d3ad8048-ef8b-45e5-b114-967fbca39a26)

# Main Features

## Two domains:
### COVID-19:
#### Statistics
- Number of cases
- National
- Statewide
- County
#### Distribution of Cases
- Geography
### Vaccination
- Total first/second doses
- Geographic Distribution of doses

## Health Insurance

### Socioeconomic Visualizations:
- Employment status
- Insurance status
- Geography
- Coverage type
- Family status
- Education
- Income
- Poverty

### Smart Insurance:
- Cost Estimator 
  - Chatbot
  - Plan Recommendations
- Neural Network

# Implementation
![image](https://github.com/duyhho/Dynahealth-Backend/assets/17374092/e28157a0-e69d-4392-9116-0b683c5ea904)

## Front End
- React:
  - Leading platform for quick, reliable, and scalable web applications.
  - Mobile-friendly
  - Maintainability and support
- Vercel: deployment platform. Integrated with GitHub with automatic deployment

## Backend
- Python: best framework for data science and deep learning
- PyTorch: one of the most popular frameworks for building DL models
- Jupyter Notebook: an interactive tool to work and share Python code efficiently
- Jupyter Dash + Plotly: powerful & interactive visualization tool for Python

# Datasets
- COVID-19 Dataset:
https://data.cdc.gov/Case-Surveillance/COVID-19-Case-Surveillance-Public-Use-Data-with-Ge/n8mc-b4w4 - COVID-19 Dataset (updated April 13, 2021) ~ 22.5 million records

- Vaccination Datasets:
https://data.cdc.gov/Vaccinations/COVID-19-Vaccine-Distribution-Allocations-by-Juris/saz5-9hgg/data - Vaccination Data - Moderna (April 2021)
https://data.cdc.gov/Vaccinations/COVID-19-Vaccine-Distribution-Allocations-by-Juris/b7pe-5nws - Vaccination Data - Pfizer (April 2021)

- Health Insurance Datasets:
https://www.census.gov/data/datasets/time-series/demo/cps/cps-asec.html - Census Health Insurance Data and Demographics (updated April 13, 2021) 
https://www2.census.gov/programs-surveys/cps/datasets/2020/march/ASEC2020ddl_pub_full.pdf - Census Health Insurance Data and Demographics Data Dictionary (updated April 13, 2021) 
https://www.healthcare.gov/health-and-dental-plan-datasets-for-researchers-and-issuers/ - Health Insurance Plans and Prices for Individuals and Families (2017-2021)
https://www.kaggle.com/teertha/ushealthinsurancedataset - Simplified Health Insurance

![image](https://github.com/duyhho/Dynahealth-Backend/assets/17374092/a608bfcb-b562-4fbc-97fe-c4b7fe16223d)

# Approach
- Data Research/Collection
- Data Curation
  - Data simplification
  - Eliminate invalid values
- Data Integration
  - Time-series Analysis
  - Boundary Integration
- Data Visualization
- Multiple charts/graphs
- Model Training
  - Data Normalization
  - Neural Network architecture: 9 layers

- Model Inference
  - Input: Age, BMI, Sex, Children, Smoke, Location
  - Output: estimated yearly

- Model Deployment
  - API endpoints: `hackaroo.ngrok.io/api/model/quick`
  - Parameters: age, height, weight, children, smoker, state
  - `https://hackaroo.ngrok.io/api/model/quick?height=150&weight=55&age=65&children=1&smoker=0&sex=1&state=MO` [Deprecated]

- Application Deployment
  - Vercel: `https://hackaroo-spring-2021.vercel.app/` [Deprecated]
  - Automatic deployment upon commit.

# Sample Server JSON
Input : `http://hackaroo.ngrok.io/api/model/quick?height=150&weight=55&age=65&children=1&smoker=0&sex=1&state=MO`
Output: 
```
{
  "plans": {
    "silver": {
      "4748A0001A002008": {
        "State Code": "MO",
        "region": "southeast",
        "Metal Level": "silver",
        "Issuer Name": "WellFirst Health",
        "Plan ID (Standard Component)": "4748A0001A002008",
        "Plan Marketing Name": "WellFirst Silver HSA-E 4500X",
        "Plan Type": "EPO",
        "Customer Service Phone Number Local": "1-866-514-4194",
        "Customer Service Phone Number Toll Free": "1-866-514-4194",
        "Customer Service Phone Number TTY": "1-866-514-4194",
        "Network URL": "http://www.wellfirstbenefits.com/find-a-doc/marketplace-epo-plan-providers/",
        "Plan Brochure URL": "http://www.wellfirstbenefits.com/Individuals-and-Families",
        "Summary of Benefits URL": "https://sbc.wellfirstbenefits.com/api/GetPdf?wellFirst_WellFirst%20MO%20Silver%20HSA-E%204500X01_0121.PDF&true",
        "Individual+1 child, Age 50+": "888.99"
      },
      "99723M0009011": {
        "State Code": "MO",
        "region": "southeast",
        "Metal Level": "silver",
        "Issuer Name": "Ambetter from Home State Health",
        "Plan ID (Standard Component)": "99723M0009011",
        "Plan Marketing Name": "Ambetter Balanced Care 11 (2021)",
        "Plan Type": "EPO",
        "Customer Service Phone Number Local": "1-855-650-3789",
        "Customer Service Phone Number Toll Free": "1-855-650-3789",
        "Customer Service Phone Number TTY": "N/A",
        "Network URL": "https://ambetter.homestatehealth.com/findadoc",
        "Plan Brochure URL": "https://www.ambetterhealth.com/content/dam/centene/ambetter/brochures/MO-2021.pdf",
        "Summary of Benefits URL": "https://api.centene.com/SBC/2021/99723M0009011-01.pdf",
        "Individual+1 child, Age 50+": "901.26"
      },
      {...},
       ...
    }
  }
}

```
# Embedded Interactive Visualizations
![Media](https://github.com/duyhho/Dynahealth-Backend/blob/main/Media/media1.gif)
![Media2](https://github.com/duyhho/Dynahealth-Backend/blob/main/Media/media2.gif)
![Media3](https://github.com/duyhho/Dynahealth-Backend/blob/main/Media/media3.gif)
![Media4](https://github.com/duyhho/Dynahealth-Backend/blob/main/Media/media4.gif)
![Media5](https://github.com/duyhho/Dynahealth-Backend/blob/main/Media/media5.gif)
![Media6](https://github.com/duyhho/Dynahealth-Backend/blob/main/Media/media6.gif)
![Media7](https://github.com/duyhho/Dynahealth-Backend/blob/main/Media/media7.gif)
![Media8](https://github.com/duyhho/Dynahealth-Backend/blob/main/Media/media8.gif)
![Media9](https://github.com/duyhho/Dynahealth-Backend/blob/main/Media/media9.gif)
![Media10](https://github.com/duyhho/Dynahealth-Backend/blob/main/Media/media10.gif)
![Media11](https://github.com/duyhho/Dynahealth-Backend/blob/main/Media/media11.gif)
![Media12](https://github.com/duyhho/Dynahealth-Backend/blob/main/Media/media12.gif)
![Media13](https://github.com/duyhho/Dynahealth-Backend/blob/main/Media/media13.gif)

# Future Scope

- Human in the loop: Real-time feedback​
- Multiple simultaneous messages from each side.​
- More knowledge domains​
- UI improvement​
- Model deployment on the Cloud (Amazon AWS, Microsoft Azure, …)​
- Application Deployment in Google Playstore​ and App Store
- Multi-modality Analysis
- Natural Language Processing​
- Object Detection (to interpret user’s uploaded images)​
- User Sentiment Analysis​
- Diverse text-to-speech models (gender-based, age-sensitive, and more natural-sounding)​
- Speech-to-text features (to simulate phone calls or Facetiming)​






