# excel 내보내기 기능

## [기능소개](https://github.com/nadale28/excel/blob/main/INTRO.md)

## 구현
 ### [백엔드](https://github.com/nadale28/excel/blob/main/BACK.md)
 ### [프론드엔드](https://github.com/nadale28/excel/blob/main/FRONT.md)








 4. js 파일 복사

 ![image](https://user-images.githubusercontent.com/16552382/180365527-5a4339d9-53a8-4b5c-9237-eb04a33d49a3.png)


 - front-end
 
 (jsp)
 
 js파일 import
 
 ![image](https://user-images.githubusercontent.com/16552382/180376678-59467a15-6593-4009-8493-99f4182e7d85.png)

 변수 선언 및 초기화
 
 -- formId (검색조건 form id)
 
 -- url (엑셀 내보내기를 수행할 url)
 
 -- initFn (엑셀 내보내기 수행  전 실행 될 함수)
 
 init(formId, url, initFn)
 
 ![image](https://user-images.githubusercontent.com/16552382/180376803-e1efc540-457f-42c5-a593-d8dac0b80c35.png)

 엑셀 내보내기 버튼에 excelDownload 클래스명 부여
 
 ![image](https://user-images.githubusercontent.com/16552382/180377321-786ee460-ab34-491d-b94d-08742fdbfb5a.png)
 
 엑셀 보관함 버튼에 excelDownloadBox 클래스명 부여
 
 ![image](https://user-images.githubusercontent.com/16552382/180671623-8448f092-47b4-4b63-b877-a28292174ee9.png)

