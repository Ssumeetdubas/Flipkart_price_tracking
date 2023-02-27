# Flipkart_price_tracking


#----------------------------------------------------- main prog--------------------------------------------------------
import re
import time
import requests
from bs4 import BeautifulSoup
import matplotlib.pyplot as plt
from datetime import datetime


def curr_date_time():
    now = datetime.now()
    # print("now =", now)
    # dd/mm/YY H:M:S
    dt_string = now.strftime("%d/%m/%Y %H:%M:%S")
    return dt_string
def curr_date_time_min():
    now = datetime.now()
    # print("now =", now)
    # dd/mm/YY H:M:S
    dt_string = now.strftime("%M")
    return dt_string
url=input("enter the link of product you want to track")

price_lis=[]
min_list=[]
for i in range(0,5):
    r=requests.get(url)
    html=r.content

    soup=BeautifulSoup(html,'html.parser')

    text=soup.get_text()

    r = requests.get(url)
    html = r.content

    soup = BeautifulSoup(html, 'html.parser')
    t= soup.get_text()
    search_pattern2 = re.compile(r'(₹)(\d,\d\d\d)')

    price2 = search_pattern2.search(t)
    print(price2)
    o=(price2.group(2))
    print(o)
    o.replace(">","")
    price_lis.append(o)
    date_tim=curr_date_time()
    f=open("flipkart_pricing_track.txt","a")
    f.write(o)
    f.write("--------------")
    f.write(date_tim)
    f.write("\n")
    f.close()
    min = curr_date_time_min()
    min_list.append(min)
    time.sleep(2)  # its 2 min

x=min_list
y=price_lis

plt.plot(x, y)
plt.xlabel('Min')
plt.ylabel('Price')
plt.title('Flipkart price tracking ')
plt.savefig("price123.jpg")
plt.show()


