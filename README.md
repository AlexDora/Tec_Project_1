# Food Requirements for a Healthy Life

   Ma. Luisa Castellanos\
   Alejandro Dorantes


## Project Motivation

    These days, it is necessary to have a helthier life by exercising and eating well.
    But eating well is not only stop or start to eat some type of food!!
    
    According to your gender, age & height you can calculate your ideal weight and the calories and nutrients
    you must consume every day.
    The calories consumed are divided in Proteins, Carbohydrates & Fats.
    
    The intention is to make a tool with wich nutritionists and regular people can make a comparison between the 
    needed calories and the ones actually consumed in a period of time and with the information obtained know how 
    many calories are under or above the requirements, calculating the body fat that could be lost or gained in a 
    certain time.
    
    
### Questions

1. **Which are the nutritional and energy requirements of each individual?**\
    With help of estimation equations and the personal information of the patient we are calculating his ideal weight (if he is over or     under of the normal classification of the CMI) in order to estimate his/her energy and nutritional requirements based on the EER of     the IOM (Institute of Medicine) formula. 

2. **How close are the calories we consume vs the ones we need?** \
    For the purpose of the 1st part of the project, we are working with a random sample of the food consumed.\
    Each food contains certain amount of nutrient and calories, and with the information obtained We sume the total grams of proteins,       carbohydrates & fats and compare them with the ones needed.\
    After a month or the certain of time worked, we can see how far or close the person is for the grams needed for each nutrient.
    
3. **What would be the weight (bodyfat) we will have at the end of one month with the food we consume?**\
    Considering the amount of calories ingested each day, we calculate the kg gained or lost per day and the end
    of the month, we can see the final weight.

### Data

We get two databases from the USDA:
   1) A list of food products
   2) The nutrients for each product

From the database **Products** we got a code which is *unique* for each product and then match the code with the info in the
database **Nutrients** to get the information for each nutrient: *Protein, Carbohydrate* or *Fat*.


## Data Cleanup & Exploration

1. Describe the exploration and cleanup process

    ```
    nutrients_data = 'Resources/Nutrients.csv'
    nutrientsdf = pd.read_csv(nutrients_data, encoding="ISO-8859-1")
    nutrients_loc=nutrientsdf.loc[nutrientsdf["Nutrient_Code"].isin([203,204,205])] 
    ```
    
    ```
    products_data = 'Resources/Products.csv'
    productsdf = pd.read_csv(products_data, encoding="ISO-8859-1")
    
    products_index = products_nutrients["NDB_Number"].unique()
    selected_products = productsdf.sample(n=12)
    nutrients_sample=nutrients_loc.loc[nutrients_loc["NDB_No"].isin(products_index)]
    
    nutrients_proteins = nutrients_sample.loc[nutrients_sample["Nutrient_Code"] == 203]
    nutrients_fats = nutrients_sample.loc[nutrients_sample["Nutrient_Code"] == 204]
    nutrients_carbs = nutrients_sample.loc[nutrients_sample["Nutrient_Code"] == 205]
    ```

2. Discuss insights you had while exploring the data that you didn't anticipate

3. Discuss any problems that arose after exploring the data, and how you resolved them

4. Present and discuss interesting figures developed during exploration, ideally with the help of Jupyter Notebook

    [Table 1](https://github.com/AlexDora/Tec_Project_1/blob/FinalResults/Nutrients_Consumed.csv)
    "Total nutrients consumed in one month"
    
    [Table 2](https://github.com/AlexDora/Tec_Project_1/blob/FinalResults/User_Results.csv)
    "Total information for one user in one month"


## Data Analysis

1. Discuss the steps you took to analyze the data and answer each question you asked in your proposal

2. Present and discuss interesting figures developed during analysis, ideally with the help of Jupyter Notebook

    [Figure 1](https://github.com/AlexDora/Tec_Project_1/blob/FinalResults/Daily_Carbs.png)
    "Daily Carbs consumed"\
    [Figure 2](https://github.com/AlexDora/Tec_Project_1/blob/FinalResults/Daily_Proteins.png)
    "Daily Proteins consumed"\
    [Figure 3](https://github.com/AlexDora/Tec_Project_1/blob/FinalResults/Daily_Fats.png)
    "Daily Fats consumed"
    
    [Figure 4](https://github.com/AlexDora/Tec_Project_1/blob/FinalResults/Daily_Requirements_Distribution.png)
    "Daily Requirements Distribution"\
    [Figure 5](https://github.com/AlexDora/Tec_Project_1/blob/FinalResults/Average_Nutrients_Consumed_Distribution.png)
    "Average Nutrients Consumed Distribution"
    
    [Figure 6](https://github.com/AlexDora/Tec_Project_1/blob/FinalResults/Body_Fat_Loss-Gain%20(Kg).png)
    "Body Fat Loss / Gain (kg)"


## Discussion

Discuss your findings. Did you find what you expected to find? If not, why not?
What inferences or general conclusions can you draw from your analysis?


## Post Mortem

Discuss any difficulties that arose, and how you dealt with them
Discuss any additional questions that came up, but which you didn't have time to answer: What would you research next, if you had two more weeks?



## Questions
