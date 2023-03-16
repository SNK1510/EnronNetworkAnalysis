# Enron Network Analysis
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

### Network Stats/ Centrality measures

1) Degree
The average degree of the network is 2.968. However, the distribution of degrees is skewed.
Majority of the employees  lie in the 0-25 degree range and as the degree increases, we can see that the count of the nodes reduces, indicating that only a few people in the company have a large number of connections whereas the rest of them have minimal connections

![image](https://user-images.githubusercontent.com/27859890/225457406-8d8ae65e-80af-4137-a4a2-97b9c6e5deb8.png)

![image](https://user-images.githubusercontent.com/27859890/225457424-9c470666-4ef8-48a8-8e91-cbb3aaafc992.png)


2) Betweenness Centrality

- These are the employees with the highest betweenness centrality, indicating that they act like bridges between a lot of teams/ other employees

- Due to their high betweenness values, they could be key players in the network especially when it comes to information flow

![image](https://user-images.githubusercontent.com/27859890/225457560-74638ffb-7047-4acc-9cd2-07f199934b79.png)


![image](https://user-images.githubusercontent.com/27859890/225457544-e8824184-28a5-42b6-a990-eebeaff2bc88.png)

3) Closeness Centrality

- A major portion of the company has low closeness centrality, but a significant number of employees  have high values. 
- A lot of these ‘close’ employees could have just one or two close connections
- Looking at the scatterplot, one can say that having a high degree does not guarantee high closeness. 
- Especially in the case of information transfer, the Employees with high degree centrality (Assuming Leadership) may not be the first ones to receive any news. This makes sense because no news directly goes to leadership considering organizational hierarchy

![image](https://user-images.githubusercontent.com/27859890/225457663-6a42d7df-cb00-4ab1-9efa-bc8f378adbc2.png)

![image](https://user-images.githubusercontent.com/27859890/225457679-148f08f4-d8ff-4d39-9188-1b905c1f1a79.png)


4) Eigen Centrality

- We see that most of the nodes are either 0 or close to 0 and very few nodes are heading towards 1
- This indicates that most employees hardly have any connections or are connected to others with less scores themselves
- These employees have less influence on the network
- Tana Jones is the employee with a perfect score of 1, with the next highest scores for Vince J Kaminski and Sara Shackleton

![image](https://user-images.githubusercontent.com/27859890/225457783-ed12dd72-37b5-4564-b709-5bd9ffad93db.png)

![image](https://user-images.githubusercontent.com/27859890/225457801-daa72771-4799-42e6-8512-5bb4bf791905.png)

### Key Employees of Enron

![image](https://user-images.githubusercontent.com/27859890/225457860-31d0ee40-e329-48d7-b93d-c2295b9c5d0d.png)


### Conclusion 
We started off with the motivation to be able to identify a company’s underlying structure in terms of organization and hierarchy. We were able to identify various groups and communities using various algorithms. Since this is a dataset consisting of real employees of a huge organization, we were also able to identify key players in the company. We identified hubs and authorities, members with the highest number of connections, most influential employees, employees that could help in the fastest transfer of information. We were fortunate enough to be able to validate our results with actual information available online regarding Enron Leadership. Most of the members we identified were in the news or listed in a public website at some point in time.
While we were able to achieve what we wanted to extract out of the project, we came up with some more ideas that could be worked on in the future. Enron has a history of scandal and quite a few third parties were involved, and we want to explore our dataset further to see if any of the employees, especially those that we identified as key players had to do with the Scandal. Since our project was built on an email dataset, we are considering the possibility of using Sentiment analysis to understand the nature of each email and use some more classification techniques to identify the type of emails exchanged. We could also include a dictionary of terms that are used in the context of fraud and malpractice and find out which employees have used these words extensively. This way, we can connect employees with their practices within their company. We can also check the cascading effect of information and how information diffuses in the network- a concept like the Epidemics lab. However, these are some ideas, we need to do a lot more research to work on the same.


#### Bibliography
1)	https://www.history.com/this-day-in-history/enron-files-for-bankruptcy#:~:text=An%20energy%2Dtrading%20company%20based,the%20top%20500%20U.S.%20companies
2)	https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0098679
3)	https://en.wikipedia.org/wiki/Force-directed_graph_drawing
4)	https://bookdown.org/markhoff/social_network_analysis/centrality.html
http://igraph.wikidot.com/community-detection-in-r
https://www.sci.unich.it/~francesc/teaching/network/transitivity.html
5)	https://www.tandfonline.com/doi/pdf/10.1080/10691898.2015.11889734
6)	https://cambridge-intelligence.com/using-social-network-analysis-measures/
7)	https://www.kaggle.com/code/jamestollefson/enron-network-analysis/notebook
8)	https://www.youtube.com/watch?v=lexLrl7Fhlg
9)	http://jse.amstat.org/v23n2/hardin/EnronTutorial.pdf
10)	https://www.energy.gov/sites/default/files/maprod/documents/enron2001.pdf

11)	https://www.hartenergy.com/news/ziff-energy-group-announces-new-staff-88587
12)	https://www.corporationwiki.com/Texas/Houston/bradford-o-larson/29734927.aspx
13)	https://en.wikipedia.org/wiki/Arthur_Andersen
14)	https://fortune.com/2009/12/15/sorry-accenture/
15)	https://www.britannica.com/event/Enron-scandal	
16)	https://www.journalofaccountancy.com/issues/2002/apr/theriseandfallofenron.html






