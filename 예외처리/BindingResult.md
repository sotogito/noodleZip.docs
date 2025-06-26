## ✅ 1. `BindingResult`란?

- `@Valid`나 `@Validated`와 함께 쓰는 **Spring의 유효성 검사 결과 저장 객체**
    
- `@Valid` 대상(DTO)의 **검사 결과**를 이 객체에 담음
    
- 유효성 검사 실패해도 **예외를 던지지 않고**, 컨트롤러까지 진입할 수 있게 해줌
    

java

복사편집

`@PostMapping("/register") public String register(@Valid UserDto dto, BindingResult result) {     if (result.hasErrors()) {         // 유효성 실패 항목 확인         result.getFieldErrors().forEach(error -> {             System.out.println(error.getField() + " : " + error.getDefaultMessage());         });         return "register-form";     }      // 유효성 통과한 경우 로직 실행     return "redirect:/success"; }`