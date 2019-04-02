# APNGpyAPI
APNG web API

# 方法
* - [x] [playnum](#playnum)

# 使用
## playnum 
* **POST**  
  
Key | Required | Description
----|---- | ---
image|necessary | 圖片二進位檔
num|optional |  APNG播放次數，預設為 0 (loop)
```python
# POST to server
import requests
data = {
    'image':open('example@2x.png', 'rb'),
    'num':0
}
with requests.post('https://api.kawai.moe/apng/playnum',files=data) as resp:
    print(resp.status_code)
    print(resp.text)
    
# Response
{"code": 200, "message": "success", "link": "https://api.kawai.moe/apng/i/kZyi48.png"}
```

* **GET**  
  
Key | Required | Description
----|---- | ---
url|necessary | 圖片網址
num|optional |  APNG播放次數，預設為 0 (loop)
```python
https://api.kawai.moe/apng/playnum?url=https://www.example.com/example.png&num=3
# Response
{"code": 200, "message": "success", "link": "https://api.kawai.moe/apng/i/kZyi48.png"}
```
