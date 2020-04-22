# Test Case 200496: [SEO Validation][Standard]: Verify suggestion reported for duplicated image alt text(html Syntax)

## 1. Against the rule

### 1.1 Html image tag

<img src = "./images/pig1.jpg" alt = "test alt text" />
<IMG src = "./images/pig2.jpg" alt = "test alt text" />

### 1.2 Image tag in html container
<div><img alt = "test alt text" src = "./images/pig3.jpg" /><div>

### 1.3 Line break
<div>
<img src = "./images/pig4.jpg" 
alt = "test alt text" /><div>

### 1.4 Empty source
<img alt = "test alt text" />

### 1.5 Multiple alt text (Use first alt text)
<img alt = "test alt text" alt = "another alt text" src = "./images/pig5.jpg"/>

### 1.6 Multiple source (Use first source)
<img alt = "test alt text 1" src = "./images/pig.jpg"/>
<img alt = "test alt text 1" src = "./images/pig6.jpg" src = "./images/pig.jpg"/>

## 2. Follow the rule
### 2.1 Alt text attribute in other html element
<a alt = "test alt text"></a>

### 2.2 Empty alt text
<img src = "./images/pig11.jpg" />
<img alt = "" src = "./images/pig12.jpg" />

### 2.3.1 Multiple source (Use first source) report suggestion
<img alt = "test alt text 2" src = "./images/pig.jpg"/>
<img alt = "test alt text 2" src = "./images/pig13.jpg" src = "./images/pig.jpg"/>

### 2.3.2 Multiple source (Use first source) Not report suggestion
<img alt = "test alt text 3" src = "./images/pig.jpg"/>
<img alt = "test alt text 3" src = "./images/pig.jpg" src = "./images/pig13.jpg"/>

### 2.4 Unique alt text
<img alt = "unique alt text" src = "./images/pig13.jpg"/>

--------------------------------------------------
Result: 
    "test alt text": 6
    "test alt text 1": 2
    "test alt text 3": 2
