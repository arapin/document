# API Documentation

## API Overview
이 API는 [서비스 이름]에서 제공하는 기능을 외부에서 사용할 수 있도록 하는 RESTful API입니다.

### Base URL
https://api.example.com/v1


## Authentication
API는 Bearer 토큰을 사용한 인증 방식을 사용합니다. 요청 시 HTTP 헤더에 다음 형식으로 인증 토큰을 포함해야 합니다.
```text
--header 'Authorization: Bearer {your_token}'
```


## Endpoints
### 1. User 정보 조회
**Endpoint:**  
`GET /users/{id}`

**Description:**  
지정한 사용자의 정보를 조회합니다.

**Request Example:**

```text
curl -X GET 
--header 'Accept: application/json' 
--header 'Authorization: Bearer test' 
--header 'GME-TOKEN: test' 
--header 'lang: en' 
'http://localhost:5000/api/v1/finance/951210/leave-step'
```


**Response Example:**
```json
{
  "id": "12345",
  "name": "John Doe",
  "email": "john.doe@example.com",
  "created_at": "2022-01-15T12:34:56Z"
}
```
## Response Codes:
- 200 OK - 요청 성공
- 401 Unauthorized - 인증 실패
- 404 Not Found - 사용자 정보가 없음
## Error Codes
- 400 Bad Request - 잘못된 요청 (예: 필수 파라미터 누락)
- 401 Unauthorized - 인증 실패
- 403 Forbidden - 접근 권한 없음
- 404 Not Found - 리소스를 찾을 수 없음
- 500 Internal Server Error - 서버 에러

## Rate Limiting

- API 요청은 시간당 1000회로 제한됩니다. 초과 시 `429 Too Many Requests` 응답을 받습니다.


