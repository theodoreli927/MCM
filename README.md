# MCM 2025 Problem C

Here is my attempt at solving a real world problem given to me at the Mathematical Contest in Modeling (MCM) 2025. 
In this repository you will find 

* 2025_Problem_C_Data: Data given to me for the competition containing information on 1896 - 2024 Summer Olympics
* 2025_MCM_Problem_C.pdf: PDF file of question I attempted to answer. Contains all necessary details for the competition.
* MCM_questionC_report.pdf: Math report submitted to be judged explaining my workflow and the mathematical concepts used in the process.
* medal_prediction_sandbox: Jupyter Notebook of where I conducted my coding portions. 

## Methodology
Key tools used in this project is SQL for data manipulation and Tableau for creating visualizations in my report. 
The most crucial part of this project was creating a dataset that replicated the 2028 Olympics as closely as possible 
based on previous Olympic game data.

Specifically, we know there are going to be new sports introduced in the 2028 Olympics, thus we need to account for more
contestants and more medals to be won as each event awards 3 medals gold, silver, and bronze.

I analyzed the representation of different countrys from 1896 - 2024 and assigned new contestants in proportion to the country's 
representation throughout history. It would be unrealistic to assign a even number of contestants to all countrys as 
historically some countrys have much less participants compared to others.


![image](https://github.com/user-attachments/assets/451f188b-0b4b-44dd-9b4c-14c418b75b30)


## Results

Upon passing the constructed data through the model we were able to get a leaderboard of the top five countries.

![Screenshot 2025-02-01 205913](https://github.com/user-attachments/assets/223493df-bcfd-4f38-b44f-d4a6552bfb48)

However these top 5 countries are identical to that of 2024. This is because I chose to build the 2028 data on top of 
2024 Olympic data. I thought it we be more realistic as the contestants from 2024 will likely participate in 2028 but
that led to data that was practically identical apart from new additions we constructed to incorporate the new sports.

The predicted 2028 data only experienced few changes with 2024 with the most being a difference of 2:

![Screenshot 2025-02-01 205843](https://github.com/user-attachments/assets/b8cc3f54-2f39-47aa-aa00-b89bb99854cb)

## Improvements to come
Currently revisioning the model to have the data aggregated on events, thus instead of the model randomly predicting out 
a random number of medals won in a specific year, we know we have a specific quota of medals needed to be assigned.
For example every Olympic game we know how many events there will be, each event will award a gold medal. Thus we know 
the medal total.

However my current model sometimes predicts less medals or more medals than the given events. I need to have the model
be trained to assign a set amount of medals each time.

Additionally, how Olympics are structured is that the ranking of each country is based on the number of gold medals but in
the case of a tie, silver and bronze medals will be used to determine the ranking. Thus, I am attempting on implementing
a multivariate model to also account for silver and bronze medals to give a more accurate representation of the Olympics.



