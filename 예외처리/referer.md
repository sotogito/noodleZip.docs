## 🕒 사용자 잘못된 입력 발생 시 타임라인

### 1️⃣ [사용자]

웹 브라우저에서 폼을 작성하고, 잘못된 값을 입력한 상태로 submit 버튼 클릭  
예: `/register` 페이지에서 이름을 비워둔 채 제출

---

### 2️⃣ [브라우저 → 서버]

`POST /register` 요청 전송됨  
`Content-Type: application/x-www-form-urlencoded`  
필드 값: `name=`

---

### 3️⃣ [서버 컨트롤러 진입]

java

복사편집

`@PostMapping("/register") public String register(@Valid UserDto dto, BindingResult result, HttpServletRequest request) {     ... }`

---

### 4️⃣ [Spring 내부]

- `@Valid`에 의해 `UserDto`의 필드 유효성 검사 수행
    
- 실패하면 `BindingResult`에 에러 정보 저장
    
- 컨트롤러 메서드는 **정상 진입** (REST와는 달리 예외가 터지지 않음)
    

---

### 5️⃣ [컨트롤러 내부 분기]

java

복사편집

`if (result.hasErrors()) {     String referer = request.getHeader("Referer");  // 이전 페이지 주소     return "redirect:" + (referer != null ? referer : "/form"); }`

- 유효성 실패 감지
    
- `Referer` 헤더를 기반으로 다시 **폼 페이지로 리다이렉트**
    
- `RedirectAttributes`를 써서 에러 메시지를 flash로 전달할 수도 있음
    

---

### 6️⃣ [브라우저]

- `/form` 페이지로 다시 이동
    
- 에러 메시지와 함께 사용자가 입력했던 값도 일부 유지될 수 있음
    

---

## ✅ 참고 흐름도 (요약)

text

복사편집

`[사용자 잘못된 입력]       ↓ [POST 요청 발생]       ↓ [@Valid + BindingResult]       ↓ [유효성 실패 → result.hasErrors() == true]       ↓ [Referer 기반 redirect 또는 에러 메시지 출력]       ↓ [사용자 폼으로 다시 돌아감]`

---

## ✅ 비교: REST 방식과의 차이점

|항목|REST 방식|JSP/Form 방식|
|---|---|---|
|유효성 실패 시|예외 발생 (`MethodArgumentNotValidException`)|예외 안 터지고 `BindingResult`로 처리|
|응답|JSON 에러 응답 (`@ControllerAdvice`)|리다이렉트 또는 폼 재렌더링|
|Referer 활용|거의 안 함|자주 사용 (리디렉션용)|
|클라이언트 UX|API 응답 기반으로 프론트에서 처리|서버 템플릿 페이지에서 오류 표시|