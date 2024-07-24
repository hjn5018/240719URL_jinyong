# URL 단축 서비스 구현

## 개요
fastapi를 이용하여 URL 단축 API를 제공합니다 <br>
- `POST /shorten` <br>
  요청 본문: `{"target_url": "<original_url>"}` <br>
  응답 본문:
  ```
  {
  "target_url": "<original_url>",
  "is_active": boolean,
  "clicks": int,
  "url": "<shortened_url_key>",
  "admin_url": "<admin/<secret_key>>"
  }
  ``` 
- `GET /<short_key>` <br>

## Swagger
![image](https://github.com/user-attachments/assets/84444bf9-9b9e-4e9b-b414-0b3c0a3875e1)

## 데이터베이스
SQLite <br>
데이터베이스 없이 json만을 이용하기보다는 활용해보고 싶었고, 가볍게 SQLite를 사용했습니다. 

2024.07.19 - 2024.07.24 (5일)
1. URL shortener reference 조사 (url.kr, bitly.com ...)
2. fastapi 탐구
3. 자료: https://realpython.com/build-a-python-url-shortener-with-fastapi/
