처음에 마이페이지를 구현했을 때 내가 보는 마이페이지와 상대방이 보는 마이페이지가 달라야하기 떄문에 url을 둘로 나누었다.

```java
    @GetMapping("/")  
    public String myPage(@AuthenticationPrincipal MyUserDetails myUserDetails, Model model) { /// 자기 자신의 마이페이지로 이동  
        User user = myUserDetails.getUser();  
  
        model.addAttribute("userId", user.getId()); ///마이페이지 내부에서 하위 페이지 이동시 herf에 필요  
//        return "index";  
        throw new ResponseStatusException(HttpStatus.NOT_FOUND);  
    }  
  
    @GetMapping("/{userId}")  
    public String userMyPage(@PathVariable String userId, Model model) { /// 특정 사용자의 마이페이지로 이동  
        return "index";  
    }
```
그넫 이렇게 했을 때의 문제점은  
수정을 할 수 있는 개인의 마이페이지로 저근하는 경로가 제한적이라는것이다.  
만약 내가 글을 쓰고 내 프로필을 눌렀을때 url이 {userid}로 넘어가기 때무에 다른 사라밍 조회했을떄처럼 뜬다
아근데  
지금생각하니까 마이페이지 메인 펭지 정도ㅇ는 그렇게 관리하는게 맞는거갗다.  

다만 가게 수정 로직같은 경우는  
같은 {userId}형식의 url을 사용하고 isMyPage로 판단을 한 뒤 view에서 처리해주면 될거같다.

```
@GetMapping("/{userId}/saved-store/list")  
public String savedStoreList(@AuthenticationPrincipal MyUserDetails userDetails, Model model) {  
    return  
}
```
가게 저장 목록을 확인하는 사용자경로는 마이페이지를 꼭 저쳐야하는데,
내가 내 페이지를 조회했을때랑 다른사람이 조회했을때랑 userId를 연결해줘서 공용적으로 사용하면 된다.


그럼 나의 가게저장같은 경우는 사용자가 본인의 가게저장페이지에 들어와야만 수정이 가능하게 처리해야되잖아 그럼url을 {userId}로 공통으로 넣고 처리를 해야할까? 가게 저장을 보는 사용자 경로는무조건 마이페이지를 거쳐가야돼 그럼 마이페이지도 정대적인 ㄱㅇ로로 분리해놨으면 저장가게도 정대적인 경로ㅗㄹ 분리해두는게 맞을까?

```java
@Slf4j  
@RequiredArgsConstructor  
@RequestMapping("/mypage")  
@Controller  
public class MySavedStoreController {  
  
    @GetMapping("/my/saved-store/list") /// 사용자가 본인의 마이페이지에 접근해야만 들어올 수 있음  
    public String mySavedStoreList(@AuthenticationPrincipal MyUserDetails userDetails, Model model) {  
  
        model.addAttribute("isOwner", true);  
        return "index";  
    }  
  
    @GetMapping("/{userId}/saved-store/list")  
    public String savedStoreList(@AuthenticationPrincipal MyUserDetails userDetails, Model model) {  
  
        model.addAttribute("isOwner", false);  
        return "index";  
    }  
}
```
마이페이지에서 한번 url을 분리했다면 그 뒤로도 분리하는게 맞다. 만약 사용자가 {userId}경로로 들어가서 다름사람이 보는 마이페이즐ㄹ 조회하는데 저장가게를 누르니까 수정이 가능한 상태가 되는게 더 이상한거같다.
배지같은 경우도 {userId}로 처리했는데 (일단 조회만있어서) 나중에 즐겨찾기나 배지 숨기기같은 기능이 추가되기 위해서는 url은 분리하는게 맞느너같다.