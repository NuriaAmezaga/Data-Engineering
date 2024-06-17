# Data-Engineering
# Gans E-Scooter Data Pipeline Project

## Project Objectives & Overview

### The Business Challenge

Gans, an emerging e-scooter rental service, aims to establish a footprint in major global cities. They plan to deploy hundreds of e-scooters across city streets, offering them for rent by the minute. Despite gaining traction through an eco-friendly marketing strategy, their operational efficiency is critically dependent on the strategic positioning of these scooters.

Optimal positioning would naturally balance scooter distribution through user movement between key points. Nonetheless, several factors disrupt this balance:

- **Varied Elevation**: In cities with varied elevation, scooters are preferred for uphill travel, leaving them unevenly distributed.
- **Morning Commutes**: Morning routines typically involve commuting from residential areas to city centers.
- **Weather Conditions**: Rainfall significantly reduces e-scooter usage.
- **Tourist Arrivals**: The arrival of tourists, particularly those with backpacks arriving by plane, spikes demand at airports and train stations connecting to city centers.

My role as a Data Engineer at Gans involved gathering external data to anticipate e-scooter movement patterns. This entailed daily, real-time data collection accessible company-wide, necessitating the development and automation of a cloud-based data pipeline.

### Skills Utilized

- **Python (Pandas)**
- **Data Acquisition via Web Scraping (BeautifulSoup) and APIs**
- **Cloud Computing with Google Cloud Platform**
- **SQL Database Management (SQLAlchemy for Python-MySQL interaction)**

## Gathering Data

### Web Scraping for City Data

Employing web scraping, I extracted city-related data from Wikipedia using BeautifulSoup. This method facilitated the retrieval of structured data from HTML, allowing for dataframe creation. By leveraging Wikipedia's consistent URL structure across city pages, I devised a function to automate data extraction. This approach addressed Wikipedia's varied HTML structures for different cities, particularly for data like population figures, by incorporating conditional logic to ensure continuity in data collection.

### API Integration for Weather and Flight Data

#### Weather Data via API

For weather forecasts, I utilized OpenWeather's API, specifically their 5-day forecast offering. The API's data, formatted in JSON, allowed for easy manipulation and integration into our data model.

#### Flight Arrival Information

Flight data was sourced through AeroDataBox via Rapid API, a marketplace simplifying API usage. Functions were developed to fetch and structure this data into dataframes, focusing on acquiring next-day flight arrival times to aid operational planning.


### Project Phases

**Phase 1: Local Pipeline**

My first task will be to create a data pipeline locally, which involves collecting data from external sources, transforming it, and storing it in a SQL database. This will provide a foundation for building a scalable and automated pipeline in the cloud.

**Phase 2: Cloud Pipeline**

Once the local pipeline is up and running, I migrate it to the cloud using Google Cloud Platform (GCP). GCP offers numerous advantages for data pipelines, including scalability, flexibility, automation, and maintenance.


![image](https://github.com/NuriaAmezaga/Data-Engineering/assets/168557674/0673f1a2-7c0f-4e83-8c5c-50d29f1a3b66)




## Data Storage

### Local Storage with MySQL

Following data collection, the resultant city, weather, and flight data were organized into dataframes and stored in a MySQL database for analysis.

![image](https://github.com/NuriaAmezaga/Data-Engineering/assets/168557674/d35f333b-9153-4e95-b549-d8066604cc54)


## Google Cloud Platform Integration

Transitioning the local data pipeline to the cloud was a crucial step for enhancing Gans' operational efficiency by providing real-time insights into e-scooter demand influenced by weather changes and flight arrivals. The migration to Google Cloud Platform (GCP) entailed setting up a scalable, cloud-based infrastructure for data storage and processing.

### Creating and Connecting to a SQL Instance

Initially, I established a MySQL database within GCP to serve as our central repository for storing weather, city, and flight data. This involved creating a relational database instance and configuring it for secure access.

### Serverless Computing with Google Cloud Functions

To modernize our approach to data processing, I leveraged Google Cloud's serverless computing solution, specifically Google Cloud Functions. This Function as a Service (FaaS) model enabled me to deploy individual functions that execute in response to cloud events, such as HTTP requests or Cloud Scheduler triggers, without the need to manage server infrastructure.

### Automating Data Updates with Cloud Functions

A pivotal component of our cloud-based solution was a set of Google Cloud Functions designed to update our database with the latest weather and flight information. These functions were triggered automatically, ensuring that our data remains current and reliable for making operational decisions.

### Scheduling Tasks with Cloud Scheduler

To automate the execution of our data collection and processing tasks, I utilized GCP's Cloud Scheduler. This fully managed cron job service allowed us to schedule our Cloud Functions to run at predetermined intervals, guaranteeing that Gans always has access to the most recent data without manual intervention.


### Key Learnings and Deliverables

- **Data Collection: Web Scraping and APIs**
- **Data Storage: SQL Database**
- **Cloud Integration: GCP MySQL, Cloud Functions, and Cloud Scheduler**

## Conclusion

Working on this engineering project taught me several key skills. I learned how to gather information from the internet, including HTML pages like Wikipedia, and how to use APIs for dynamic data retrieval. I also developed the ability to store this data in the cloud, ensuring that the database remains operational and updated in real-time through automation. This project allowed me to apply my Python and MySQL skills in conjunction with cloud functions. Although I encountered numerous coding errors, I realized that errors are valuable learning opportunities rather than obstacles. Overall, this experience demonstrated the importance of resilience and continuous learning in engineering. 

Additionally, I wrote my first article explaining my journey in this new field of Data Engineering. You can read it here: https://medium.com/@namez07/my-first-project-as-a-data-engineer-8b6cec29ab6d





