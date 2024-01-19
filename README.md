# PricePredictorAI
Artificial intelligence model that can predict the price direction of a stock or cryptocurrency.  
The accuracy of the AI varies from **50%-60%**.  
Made using Python and the [Jupyter](https://jupyter.org) IDE.  
I used the [Scikit-Learn](https://scikit-learn.org/stable) library for the obtention and training of the ```MLPClassifier``` model.  

## How to use the AI
1. Download ```PricePredictorAI.joblib```.
2. You will need a dataset that is well formatted for the AI to recognise it (Look at ```1hVHLV.csv```) :  
   * The ```Vx``` column represents the percent variation between the open price and the closing price of a previous candle, calculated by this formula: ```(Close - Open) / Open * 100```.
   * The ```VHLx```column represents the percent variation between the highest price and the lowest price of a previous candle, calculated by this formula: ```(High - Low) / Low * 100```.
   * The numbers go from 1 to 12 and represent the inverse distance of the current candle to the candle which we are trying to predict the direction of.
     The lowest number represents the farthest candle and the highest number represents the closest candle.
3. Import the ```Scikit-Learn``` library in your Python project.
4. Format your data with  
   ```sc = StandardScaler()```  
   ```formattedData = sc.transform(importedData)```
5. Use the model to make a prediction using your data with ```prediction = model.predict(formattedData)```.
6. The result ```True``` means that the next candle should go **Up**. The result ```False``` means that the next candle should go **Down**.  
7. Use ```prediction``` to do whatever you'd like!
