This program is used for tracking the price of flipkart products 
firstly you need to give the link input to the program of the product which you what to track the price 
this program is pirtucally runs for only 5 times based on the product price it provide the graph

modules used :
1.Regex 
2.bs4 
3.datetime 
4.time
5.matplotlib
6.request 

flow of program :

1. gets the link from user parse it to the request moduel 
2. request moduel gets the HTML content from the link provided 
3. This HTML content is again parsed to the bs4 this bs4 seperates the achor,tags,header,footer form the HTML content 
4. this seperated content is passes to the json which converts the HTML content to the readable form 
5. using the regex module we need to the search perticular pattern of the number using this we get the price of product and store it in the varible 
6. to get the graph of the price we parse the price to the matplot lib moduel which will diplay the graph of the given data.  

  This is how the program works 
  
  Future improvements in the progam:
  1.we can get the notification if the price of the product gets below the perticular price.
  2.track the price of product when the price of product gets lower with its time.
  
  This is all about the Flipkart price tracking programming  
  
