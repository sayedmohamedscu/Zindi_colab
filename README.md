# Zindi_colab
Download Zindi's compositions datasets directly to google colab 

******************

## What is Zindi?

[Zindi](https://zindi.africa/) is Zindi is a social enterprise whose mission is to build the data science ecosystem in Africa.
Our vision is for a vibrant community of data scientists across Africa, mobilized towards solving the region’s most pressing problems.

******************

## How to download Zindi's Datasets directly to Colab ?

we need to get the URL and the authentication value 

1. joining the competition
2. Right click in the page + Inspect
3. click the top left icon or (Ctrl + shift +c)
4. then click on the dataset name (training for example ) 
you will see that the right page will show the Web script which contain the **URL of the dataset**
and the **authentication value**
5. copy them and use the python script in colab to download them  directly 

*****************


```
import requests
import requests, zipfile

#the url and auth_value from the website 
url = 'https://api.zindi.africa/v1/competitions/iclr-workshop-challenge-1-cgiar-computer-vision-for-crop-disease/files/train.zip'
myobj = {'auth_token': 'sfffghgghgvkhuf'} #use your own

x = requests.post(url, data = myobj,stream=True)
target_path = 'data.zip'

handle = open(target_path, "wb")
for chunk in x.iter_content(chunk_size=512):
    if chunk:  # filter out keep-alive new chunks
        handle.write(chunk)
handle.close()

!unzip -qq /content/data.zip

```




*******************



![First](https://github.com/sayedmohamedscu/Zindi_colab/blob/master/1.jpg)

![sec](https://github.com/sayedmohamedscu/Zindi_colab/blob/master/2.jpg)

![3rd](https://github.com/sayedmohamedscu/Zindi_colab/blob/master/3.png)
