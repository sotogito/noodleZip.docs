일단 수정과 삭제를 비동기로 처리를 했는데,
업데이트된 결과를 프론트에서 처리해주면 될까
아니면 업데이트된 결과를 백에서 다시 뿌려줘야할까

```
@PostMapping(  
        value = "/my/saved-store/categories/update",  
        consumes = MediaType.APPLICATION_JSON_VALUE  
)  
@ResponseBody  
public SavedStoreApiResponse updateCategoryList(@AuthenticationPrincipal MyUserDetails myUserDetails,  
                                                @RequestBody @Validated List<SavedStoreCategoryUpdateRequest> requestList) {  
    User user = myUserDetails.getUser();  
    saveStoreCategoryService.updateSavedCategoryList(user.getId(), requestList);  
  
    return SavedStoreApiResponse.builder()  
            .isSuccess(true)  
            .message(SavedStoreSuccessStatus._OK_UPDATE_SAVED_STORE_CATEGORY.getMessage())  
            .build();  
}  
  
  
@PostMapping(  
        value = "/my/saved-store/categories/delete",  
        consumes = MediaType.APPLICATION_JSON_VALUE  
)  
@ResponseBody  
public SavedStoreApiResponse deleteCategory(@AuthenticationPrincipal MyUserDetails myUserDetails,  
                                            @RequestBody List<Long> categoryIdList) {  
    User user = myUserDetails.getUser();  
    saveStoreCategoryService.deleteSavedCategoryList(user.getId(), categoryIdList);  
  
    return SavedStoreApiResponse.builder()  
            .isSuccess(true)  
            .message(SavedStoreSuccessStatus._OK_DELETED_SAVED_STORE_CATEGORY.getMessage())  
            .build();  
}
```
다행히도 내가 컨트롤러 부분에서 성공했을 경우에 true 상태를 보내는 코드를 작성ㅎ해뒀기 때문에 

#### 1. 프론트에서 낙관적으로 UI를 먼저 바꿔주고,
#### 2. 실패시 rollback한다.

```
const oldName = category.name;
category.name = newName;

try {
  await axios.post("/api/update", payload);
} catch (err) {
  category.name = oldName;  // 🔥 이게 롤백
  alert("수정에 실패해서 원래 이름으로 돌렸습니다.");
}
```