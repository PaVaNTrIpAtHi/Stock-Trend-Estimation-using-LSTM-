# Stock-Trend-Estimation-using-LSTM-
Stock trend prediction is a great application of machine learning and when done with good and appropriate dataset can help in unique ways. Here we deployed the application using Streamlit and can select any stock we want and get the dataset from yahoo in real time and use the LSTM model we trained and we get a list of results like the 100 day MA, 200 day MA, and future trend of the stock.

Dataset Description:
We scrape the data from Yahoo website using pandas datareader library. You can mention the start date and end date to get the stock price details of that period.

![image](https://user-images.githubusercontent.com/88571564/178117469-a75469fe-4ea2-4fbe-9f3c-8d26b6173ab8.png)


Sample images after getting the data.
Algorithm Description:
LSTM:
If you want to predict the next word for the sentence “I like numbers, my favorite subject is …” your answer would be “mathematics”. How do you come to that conclusion, it is because of the word “numbers”. Recurrent Neural Networks help us achieve this. They are neural networks with loops, allowing the information to stay for some time.
 ![image](https://user-images.githubusercontent.com/88571564/178117480-6bc652f5-3f6b-492d-a021-eb5415993c94.png)

Figure 1: Recurrent Neural Network
Xt is the input, the Network analyzes and throws out output ht. RNNs have performed decently but the problem comes when the sentence is too long and has immense data. E.g. predict the next word for the sentence “I like numbers, my favorite subject is mathematics. My brother likes space and technology, his favorite subject is ….” your answer would be “astronomy”. How do you come to that conclusion, it is because of the word “space and technology”.
But how does the network know that word mathematics is not important now and “space and technology is important now”. Also the problem with RNNs is it cannot remember the entire sequence for long. Long Short Term Networks (LSTMs) are a special kind of RNN which are very much capable of handling long term dependencies. LSTMs has a cell state which holds the important word/information required for processing. The information in the cell state can be forgotten (removed) or added based on gates. It has 3 gates to help it decide:
1.	Forget gate: To forget the information in the cell state. Done with the help of a sigmoid function which returns a value between 0 and 1. If 1 or closer to 1, remove the word else retain the word.  
2.	Input gate: What input should be given to the cell state done with the help of tan-h function. 
3.	Update gate: Any information that can be added to the cell state. E.g. : When “space” was in cell state, update it with the word “technology” because word “technology” is important in decision making as well .
 ![image](https://user-images.githubusercontent.com/88571564/178117492-0a8a0a07-9170-48a5-b053-6a8aa69d8f25.png)

To get a clear understanding of LSTM along with mathematical insights, refer to this article https://colah.github.io/posts/2015-08-Understanding-LSTMs/

Run command pip install -r requirements.txt or conda install requirements.txt (Requirements.txt is a text file consisting of all the necessary libraries required for executing this python file. If it gives any error while installing libraries, you might need to install them individually.)
 
All the necessary files will get downloaded. To run the code, open anaconda prompt. Go to virtual environment if created or operate from the base itself and type “streamlit run app.py” to get the results.
 
 If you want to build your own model for detection, you can go through “lstm.ipynb”. It takes time to build the model from scratch again.


Results:
 ![image](https://user-images.githubusercontent.com/88571564/178117522-90f58948-1c28-4637-a042-569a46f1fa76.png)

You can enter any stock name.
Note: Be careful with the stock ticker according to the Yahoo website.
 ![image](https://user-images.githubusercontent.com/88571564/178117528-4cc9a6fe-a819-49e3-98e6-8e8f45a1ee91.png)

Ticker for NIFTY 50 (^NSEI), so in the input (^NSEI) .
![image](https://user-images.githubusercontent.com/88571564/178117533-b0880fd0-ea78-4e2d-b8a0-1043820fa691.png)
![image](https://user-images.githubusercontent.com/88571564/178117539-7055e522-659e-4df4-8d2b-cf70d0f2b1c3.png)
![image](https://user-images.githubusercontent.com/88571564/178117547-e383b39f-217e-49cb-9e0f-4409d6f20fb7.png)

 
Figure 2: Predicted trend vs. original

Issues faced/ Points to note:
1.	Ensure you have all libraries installed.
2.	Give correct paths wherever necessary.
3.	Make sure you have the appropriate versions of tensorflow and keras.
4.	Enter the correct stock ticker in the input screen when asked.
Picture credits: https://miro.medium.com/max/1400/1*7cMfenu76BZCzdKWCfBABA.png


This code was derived from a video from geek for geeks, link to the video https://www.youtube.com/watch?v=s3CnE2tqQdo
