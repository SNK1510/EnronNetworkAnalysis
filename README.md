# EnronNetworkAnalysis
A project that revolves around Organizational Network Analysis - To understand the internal working of a company  and its most influential employees.
By Ana Alferez, Mohammad Umar, Srinanda Kurapati


## Background and Motivation
We wanted to work on a dataset that represents Organizational Network Analysis. While the best kind of network data that we can find is that of email logs and communications, we wanted to pick an email dataset of a company that has history and a backstory to correlate it with our findings of internal organizations and network statistics.
It was in this quest that we came across the Enron Email Dataset. Fortunately, it had actual work mail ID’s and communications amongst employees.
Our objective was to get a glimpse of the internal working of the company, identifying the most powerful and influential employees of the company.  Our background research about the company and its scandal also gave us a lot of names of employees who were at leadership roles in the company at that point who may or may not have played a role in the fraud. We wanted to identify these employees in the network and understand their role in social interaction and information transfer. In simple words, ‘to identify hubs and authorities’ and information progression. 

## Objective
- Analyse intra-company email communications to look for hubs and authorities

- Analyse network to speculate information diffusion through cascading behaviour in network



- Hypothesize primary stakeholders in the company who could possibly know the happenings within 

## Business Questions
- Who are the most influential employees in the company?

- If the CEO knew, how likely it is that other boards also knew about the fraud?


## Data Description

- Email data from Kaggle containing “from”, “to” and an email body
- Downloaded dataset from Kaggle- 1.3GBDataset contains emails of people from and to along with the email body.
- Data pre-processing- removing extra texts to only get “from” and “to” email addresses
- Multiple emails are sent from single user to multiple users. 
- One single user sends email to all users using subject line “Enron mentions”
- Create IDs for both “from” and “to” emails/users for every unique user.
- Create “Route” column by concatenating “from” and “to” email using the unique ID for each user. E.g: 111<->112
- Add weights by frequency of emails with respect to a single route by creating a pivot table on “Route” and how many time that route occurred in the data
- Kenneth Lay, founder, Chairman and CEO Jeffrey Skilling, former President, and COO Andrew Fastow, former CFO Rebecca Mark-Jusbasche, former Vice Chairman, Chairman and CEO of Enron International Stephen F. Cooper, Interim CEO and CRO
- With respect to different centrality measures, where are the most important people in Enron

## Findings
### Hub/Authority Scores

![image](https://user-images.githubusercontent.com/27859890/225455379-21916c38-4f44-46ba-a811-f61c2d97a760.png)

Tana Jones, Sara Shackleton and Mark Taylor are the candidates with best Authority and Hub score which are not the CEO/CFO/Board Members hence CEO/CFO are NOT the primary movers of communication
![image](https://user-images.githubusercontent.com/27859890/225455406-0a485d27-e51b-4462-9e79-33ade5a30e35.png)


### Degree Analysis

![image](https://user-images.githubusercontent.com/27859890/225455502-b3cbdad9-aee4-4135-b73b-b7412fbd8a7d.png)

Tana Jones,  Sara Shackleton, Jeff DasoVich, Kay Mann and Vince J Kaminski are employees with some of the highest degrees, which in this case means high connectivity with other employees. These people have had  maximum number of email exchanges with their colleagues. They most likely could be line heads or managers that overlook large teams explaining the high degree.
![image](https://user-images.githubusercontent.com/27859890/225455517-63868f72-1c4d-4e55-bc7f-84dc5546a91f.png)

### Network Stats/ Centrality measures!








