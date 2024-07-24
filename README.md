# URL 단축 서비스 구현

## 개요
fastapi를 이용하여 URL 단축 API를 제공합니다 <br>
- `GET /<short_key>` <br>
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
  
### 실행방법
- `git clone https://github.com/hjn5018/240719URL_jinyong/edit/main/README.md`
- `cd 240719URL_jinyong`
- `py -3.8 -m venv venv`
- `source venv/Scripts/activate`
- `pip install -r requirements.txt`
- `uvicorn shortener_app.main:app --reload` <br>
- `POST /shorten` <br>

## Swagger
![image](https://github.com/user-attachments/assets/84444bf9-9b9e-4e9b-b414-0b3c0a3875e1)

## 데이터베이스
SQLite <br>
데이터베이스 없이 json만을 이용하기보다는 활용해보고 싶었고, 가볍게 SQLite를 사용했습니다. 

## 후기
fastapi 처음 써봤는데, 재밌었습니다.
URL 단축도 평소에는 별로 관심이 없었는데, 기업에서 스스로 엔진을 만들어서 사용하면 유용하겠다는 생각을 했습니다.

익숙하지 않고, 자료가 많지는 않아서 적용해보기 어려웠습니다.
중간에 pydantic에서 orm_mode가 from_attribute로 바뀌면서 사용구조가 변경된 점이 있어서 해결해보려고했는데, 시간이 부족했습니다.

현재는 origianl_url이 있다면 5글자의 key를 만들어서 `127.0.0.1:8000/<key>`로 적용하여 들어갈 수 있습니다.
2024.07.19 - 2024.07.24 (5일)
1. URL shortener reference 조사 (url.kr, bitly.com ...)
2. fastapi 탐구
3. 자료: https://realpython.com/build-a-python-url-shortener-with-fastapi/
