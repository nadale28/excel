## 대용량 엑셀 다운로드 처리를 위한 기능

### 기존 문제점
 - 대용량 엑셀 다운로드시 서버 부하 발생
 - 사용자가 다운로드가 어느정도 진행됐는지 알 수 있는 방법이 없음
 - 브라우저를 닫으면 작업이 중단됨

### ㅇ 대용량 엑셀 다운로드시 서버 부하 발생
 - #### ibatis rowHandler 사용

     -> 대용량 데이터를 한번에 불러와 outOfMemory 에러가 발생하지 않도록 관리
 
 - #### 사용자당 한건의 엑셀 다운로드만 진행가능하도록 DB에서 상태를 관리
 
     ![image](https://user-images.githubusercontent.com/16552382/182095722-972446df-9e2f-450f-9c6c-a7de915768eb.png)
     
### ㅇ 사용자가 다운로드가 어느정도 진행됐는지 알 수 있는 방법이 없음
 - #### 사용자가 작업 진척도를 확인 할 수 있음
    ![image](https://user-images.githubusercontent.com/16552382/182097571-937f5ea0-6897-4805-9135-5af0afd6e91b.png)

### ㅇ 브라우저를 닫으면 작업이 중단됨
 - #### 브라우저를 닫아도 파일이 서버에 저장되기 때문에 다시 받을 수 있음
    ![image](https://user-images.githubusercontent.com/16552382/182098084-fdb576ca-9930-477e-97de-1dbb767bc883.png)
