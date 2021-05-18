How to create NEWS application using python

So here we are going to make news application using python 
For this we are going to use NEWS API from https://newsapi.org/ from there we will get the API key.
So we will divide our code in three part
In the first part we will import the packages and in the second step we will create UI for the app
, at the end we will create function which will fetch the data  and present in UI

STEP no. 1
Importing the packages

import requests
import tkinter as tk

So here we are importing requests because we going to deal with API and tkinter provide use widget like button and label

Step no. 2


app = tk.Tk()
app.title("news application")
#button
button = tk.Button(app,font = 24,text = "refresh", command= getLatestnews)
button.pack(pady = 20)
#label
label = tk.Label(app,font = 18 ,justify ="left")
label.pack(pady= 20)


So here we are giving title to our app and in the next line we are creating button and label
And packing it.

Step no 3 

def getLatestnews():
   
    url = "your app url"
   news = requests.get(url).json()
   store = news["articles"]

   my_app_articles = []
   my_latest_news = ""
   for article in store:
       my_app_articles.append(article["title"])
   for i in range(10):
       my_news = my_latest_news +str(i+1) +" "+my_app_articles[i] + "\n"
   print(my_latest_news)
   label.config(text = my_latest_news)

getLatestnews()
app.mainloop()

So here in this function we have defined one funcation and we are converting data in json formate and then we will fetch the data from there and presnet in our UI




