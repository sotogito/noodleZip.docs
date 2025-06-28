컨트롤러 예외처리는 `@Validated`로 DTO 검증시 터진 예외를 말한다.  
어노테이션 예외에 걸리면 바로 예외를 던지지 않고 BindingResult에 에러 내용을 담아서 컨트롤러에 같이 넘겨준다.  
이때 에러 내용은 validation 어노테이션에 message로 정의할 수 있다  

```
@NotNull(message = "ID 값은 비어있을 수 없습니다", groups = {ValidationGroups.OnCreate.class})  
@NotBlank(message = "ID 값은 비어있을 수 없습니다", groups = {ValidationGroups.OnCreate.class})  
private String loginId;
```

즉 BindingResult는 폼에서 넘어온 값에 대한 유효성 검증 결과를 담은 객체이다.  
`if (bindingResult.hasErrors())`로 에러가 있는지 검사하여 처리한다.  
만약 에러가 존재한다면 model.addAttribute에 에러 메시지와 다시 필요한 정보를 담아 보낸다.  

```js
<script th:if="${validationError}">
    alert([[${validationError}]]);
</script>
```
그럼 클라이언트에서 만약 넘겨온 에러 메시지가 있을 경우 alert를 띄운다.