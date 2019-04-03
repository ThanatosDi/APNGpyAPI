APNGpyAPI
===========
APNG 圖片編輯 WEB API

方法
===========
- playnum_

  - playnum.POST_
  
  - playnum.GET_

使用
===========
server : https://api.kawai.moe/apng/

.. playnum:

playnum
---------

.. playnum.POST:

* POST

  +------+------+---------+-----------------------------+
  |Key   |Type  |Required |Description                  |
  +======+======+=========+=============================+
  |image |string|necessary|圖片二進位檔                 |
  +------+------+---------+-----------------------------+
  |num   |int   |optional |APNG播放次數，預設為 0 (loop)|
  +------+------+---------+-----------------------------+

  .. code-block:: python

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

.. playnum.GET:

* GET

  +------+------+---------+-----------------------------+
  |Key   |Type  |Required |Description                  |
  +======+======+=========+=============================+
  |url   |string|necessary|圖片二進位檔                 |
  +------+------+---------+-----------------------------+
  |num   |int   |optional |APNG播放次數，預設為 0 (loop)|
  +------+------+---------+-----------------------------+
  
  .. code-block:: python
    
    https://api.kawai.moe/apng/playnum?url=https://www.example.com/example.png&num=3
    # Response
    {"code": 200, "message": "success", "link": "https://api.kawai.moe/apng/i/kZyi48.png"}
