# **Predicting Squid Game Survival Using AI: A Fictional Analysis**  

## **Introduction**  
While watching *Squid Game*, I found myself wondering: could an AI model predict which participants would survive each game based on their traits, like age, gender, or the amount of debt they’re in?  

This curiosity inspired me to build a machine learning project to explore how personal attributes might influence survival in each game. The goal is to develop a model that predicts whether a participant would survive while also analyzing the most significant factors contributing to survival.  

---

## **Defining the Problem**  
### **Objective**  
Predict whether a player in *Squid Game* would survive or be eliminated during the “Red Light, Green Light” game based on their personal attributes.  

### **Features**  
- **Input Variables**:  
  - **Age**: Player's age in years.  
  - **Gender**: Player's gender.  
  - **Debt**: Total debt amount (in won).  

- **Output Variable**:  
  - **Survival Status**: Whether the player survives ("1") or is eliminated ("0") during the “Red Light, Green Light” game.  

### **Feature Selection**  
- I deliberately excluded features like **hair color** and **eye color**, as they are not logically linked to survival skills, decision-making, or fitness. Including these features could:  
  - Introduce unnecessary noise, reducing the model's performance.  
  - Risk unintentional biases or reinforcement of stereotypes.  

---

## **Collecting Data**  
Finding a dataset specific to *Squid Game* participants proved challenging. Since no existing dataset aligned with my requirements, I used Python's **BeautifulSoup** library to scrape data from the [Squid Game Wiki](https://squid-game-minor-players.fandom.com/wiki/List_of_players).

The scraping process involved editing the URL to loop through each player's wiki profile, extracting relevant attributes, such as age, gender, and debt amount. The collected data was formatted into a structured CSV file for analysis.  

- [Data Collection Notebook](./collecting-data.ipynb): Contains the code used for scraping and processing data.  
- [Player Records CSV](./player_records.csv): The resulting dataset in CSV format.  

## **Data pre-processing**
I first went through the data manually to edit any records which were corrupted and I could find the actual data for - I found that a lot of the main characters profiles had been vandilised at the time of web-scraping! I updated any actual debt values and any tr ages I could find. To clean the data I: 
- Randomly genereated an age ranging from the youngest to oldest for any trace values in age
- Replaced debt from a randomly generated value ranging from ₩100,000,000 to ₩700,000,000 and heavy debt from a randomly generated value from ₩700,000,001 to ₩1,500,000,000 (these figures guided by the debts known)
- Randomly generated a sex if any tr in sex
  
