# [Test case 1] Image use markdown syntax - Image Alt Text Duplicated

## 1. Against the rule
### 1.1 Image markdown syntax
![test alt text](./images/pig1.jpg)
### 1.2 Alt text with inline container
![**test** alt text](./images/pig2.jpg) 
### 1.3 Alt text with html tag
![<b>test</b> alt text](./images/pig3.jpg)
![<div><b>test</b></div> alt text](./images/pig4.jpg)
### 1.4 Image with error source
![test alt text](./images/error.jpg)

## 2. Follow the rule
### 2.1 Image with unique alt text
![unique alt text](./images/pig11.jpg)
### 2.2 Image with empty alt text
![](./images/pig12.jpg)

--------------------------------------------------
Result: 
    "test alt text": 5
