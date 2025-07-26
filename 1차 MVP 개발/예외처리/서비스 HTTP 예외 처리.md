서비스에서 예외 던짐
    ↓
ExceptionHandler(=핸들러)가 그 예외를 catch
    ↓
ApiResponse DTO 에 예외 정보 (code, message, status) 담아서
ResponseEntity 로 반환
    ↓
REST API JSON 응답으로 클라이언트(화면/앱)에 전달

---

만약에 회원가입시 이미 존재하는 아이디가 있을 경우를 예시로 들어 설명해보자면
#### 1. 서비스에서 예외 던짐
```java
throw new CustomException(UserErrorStatus._ALREADY_EXIST_LOGIN_ID);
```
CustomException예외 객체를 생성한다.
매개변수을 Enum 자료형으로 넘긴다.
    
아래와 같은 본인 도메인의 에러 정보를 담아 Enum 상수로 관리한다.
- httpStatus
- error code
- error message

#### 2. ExceoptionHandler에서 받음
```java
@ExceptionHandler(CustomException.class)
public ResponseEntity<ApiResponse<ErrorReasonDto>> handleCustomException(CustomException e) {
    logError(e.getMessage(), e);
    return ApiResponse.onFailure(e.getErrorCode());
}
```
CustomExceoption예외가 뎐져지면
`@RestControllerAdvice` 가 정의되어있는 핸들러 클래스에서
`@ExceptionHandler(CustomException.class)`어노테이션이 달린 handleCustomException메서드가 호출된다.  

그리고 onFailure statuc 메서드에 처리해야할 에러 정보가 정의되어있는 Enum을 넘긴다.
#### 3. ResponseEntity에 ApiResponse를 담아서 JSON으로 반환
```java
public static <T>ResponseEntity<ApiResponse<T>> onFailure(BaseErrorCode code) {
    ApiResponse<T> response = new ApiResponse<>(false,
        code.getReasonHttpStatus().getCode(),     // "USER-014"
        code.getReasonHttpStatus().getMessage(),  // "이미 존재하는 로그인 아이디입니다."
        null);
    return ResponseEntity.status(code.getReasonHttpStatus().getHttpStatus())
        .body(response);
}
```
ApiResponse는 DTO이다 
전달 받는 Enum에서 에러 정보를 꺼내 ApiResponse를 생성한다.  
ResponseEntity에 HttpStatus와, ApiResponse를 바디에 담아 넘긴다.

JSON 으로 아래와 같은 응답을 만들어낸다.
```
{
  "isSuccess": false,
  "code": "USER-014",
  "message": "이미 존재하는 로그인 아이디입니다.",
  "payload": null
}
