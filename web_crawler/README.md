# How to crawler websites

## Chrome - DevTools 
* Network
    * click on a request
        * Headers
            * Request Headers
                |Element|Meaning|Note|
                |:---:|:---|:---|
                |Accept|||
                * Accept: application/json, text/javascript, */*; q=0.01
                * Accept-Encoding: gzip, deflate, br
                * Accept-Language: zh-TW,zh;q=0.9
                * Connection: keep-alive
                * Cookie: JSESSIONID=52728DA58B6A35B38F4F24A8CEC3E809
                * Host: www.twse.com.tw
                * Referer: https://www.twse.com.tw/zh/page/trading/exchange/MI_INDEX.html
                * sec-ch-ua: " Not A;Brand";v="99", "Chromium";v="102", "Google Chrome";v="102"
                * sec-ch-ua-mobile: ?0
                * sec-ch-ua-platform: "Windows"
                * Sec-Fetch-Dest: empty
                * Sec-Fetch-Mode: cors
                * Sec-Fetch-Site: same-origin
                * User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36(KHTML, like Gecko) Chrome/102.0.5005.62 Safari/537.36
                * X-Requested-With: XMLHttpRequest
        * Payload
            * Frow Data
        * Preview (see web contents)

    Note: there is no parameters in url, type to find an option - print to HTML and see its url 


## Website
|Comparison| GET | POST |
|:---:| :---: | :---: |
|Meaning|view something|change something|
|values|visible in the URL|not visible in the URL|
|Supported Data Type|Only String|Different Types|
|Advantage|save the results of a HTML form|send user-generated data to the web server|
|Disadvantage|1. can’t be used to send word documents or images 2. cannot be used for passing sensitive information|takes lots of time when uploading the large binary file|

## Package: request

res.json().get("aaData", "") => crawler_tpex

if status code is less than 400
    request.get().ok