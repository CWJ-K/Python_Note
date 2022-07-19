<!-- omit in toc -->
# Introduction
How to crawler websites by Python?

<br />

<!-- omit in toc -->
# Table of Contents
- [Fundamental Concepts](#fundamental-concepts)
  - [1. Chrome - DevTools](#1-chrome---devtools)
  - [2. Website](#2-website)
  - [3. web offset](#3-web-offset)
- [Packages](#packages)
  - [1. request](#1-request)
- [Commands](#commands)
    - [1. revise encoding](#1-revise-encoding)
    - [2. urlretrieve](#2-urlretrieve)
    - [3. session vs get](#3-session-vs-get)
- [Questions](#questions)
- [Reference](#reference)
  - [URL parameters](#url-parameters)

<br />

# Fundamental Concepts

## 1. Chrome - DevTools 
*  If a website uses POST, try to find an option "print to HTML" and see its URL

* Network
    * click on a request
        * Headers
            * Request Headers
                |Element|Meaning|Note|
                |:---:|:---|:---|
                |Accept|application/json, text/javascript, */*; q=0.01||
                |Accept-Encoding|gzip, deflate, br||
                |Accept-Language|zh-TW,zh;q=0.9||
                |Connection|keep-alive||
                |Cookie|JSESSIONID=52728DA58B6A35B38F4F24A8CEC3E809||
                |Host|www.twse.com.tw||
                |Referer|[www.twse.com.tw](https://www.twse.com.tw/zh/page/trading/exchange/MI_INDEX.html)||
                |sec-ch-ua|" Not A;Brand";v="99", "Chromium";v="102", "Google Chrome";v="102"||
                |sec-ch-ua-mobile| ?0||
                |sec-ch-ua-platform| "Windows"||
                |Sec-Fetch-Dest| empty||
                |Sec-Fetch-Mode| cors||
                |Sec-Fetch-Site| same-origin||
                |User-Agent| Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36||(KHTML, like Gecko) Chrome/102.0.5005.62 Safari/537.36||
                |X-Requested-With| XMLHttpRequest||
        * Payload
            * Frow Data
        * Preview (see web contents)

<br />

## 2. Website
|Comparison| GET | POST |
|:---:| :---: | :---: |
|Meaning|view something|change something|
|values|visible in the URL|not visible in the URL|
|Supported Data Type|Only String|Different Types|
|Advantage|save the results of a HTML form|send user-generated data to the web server|
|Disadvantage|1. can’t be used to send word documents or images 2. cannot be used for passing sensitive information|takes lots of time when uploading the large binary file|

<br />

## 3. web offset 
* a form of offset printing in which a continuous roll of paper is fed through the printing press
* e.g. offset = 100: get next set of 100 records


<br />

# Packages

## 1. request


<br />

# Commands

  ```python
  res.json().get("aaData", "")

  if status code is less than 400
      request.get().ok

  response.raise_for_status()
  ```

<br />

### 1. revise encoding
  ```python
  response.content.decode
  ```

<br />

### 2. urlretrieve
* Copy a network object denoted by a URL to a local file.

<br />

### 3. [session vs get](https://stackoverflow.com/questions/65575601/python-requests-get-vs-session-get)
* session:
  * requires persistent cookies
  * performance increase: speed up multiple requests to the same host
  
* get
  * only want to fetch a single Item
  * no need for cookies to be persistent
  * no need to login

<br />

# Questions
1. When to use beautiful soup
2. record steps of different types of files/websites


# Reference
## URL parameters
https://www.semrush.com/blog/url-parameters/