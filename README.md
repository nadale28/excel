# excel

엑셀 출력시 작업 진행도를 사용자가 확인 할 수 있으며, 다운로드 보관함에서 언제든 다시 받을 수 있는 기능

가장 큰 목적은 메모리 관리이며, rowhandler를 사용하여 대용량 엑셀 변환에도 outOfMemory 에러가 발생하지 않음
 
![image](https://user-images.githubusercontent.com/16552382/180671709-ccdd202c-c495-45ff-a539-f0be07a35af3.png)



[기본 세팅]

 1. le.excel 패키지 복사

 ![image](https://user-images.githubusercontent.com/16552382/180364466-25f4c15a-ae6c-4b8b-b175-497809659149.png)

 2. component-scan 설정에 le 패키지 추가

 ![image](https://user-images.githubusercontent.com/16552382/180364961-a9f8d2aa-5e7b-4f9c-8918-bb9b2d1fad90.png)

 ![image](https://user-images.githubusercontent.com/16552382/180365107-ee04ddd7-b051-4d03-a75e-38e46e5ca4b5.png)


 3. SQL 파일 복사 (sql파일 추가에 따른 설정은 각자 프로젝트에 맞게 설정)

 ![image](https://user-images.githubusercontent.com/16552382/180364641-06383657-9feb-46af-9da8-57595fcd4e8d.png)

 4. js 파일 복사

 ![image](https://user-images.githubusercontent.com/16552382/180365527-5a4339d9-53a8-4b5c-9237-eb04a33d49a3.png)

 5. 테이블 생성 (MySQL)
 
CREATE TABLE `excel_download` (
  `FILE_REAL_NM` varchar(100) NOT NULL,
  `FILE_TYPE` varchar(20) DEFAULT NULL,
  `TOT_CNT` varchar(20) DEFAULT NULL,
  `CUR_CNT` varchar(20) DEFAULT NULL,
  `STATUS` varchar(20) DEFAULT NULL,
  `REG_ID` varchar(50) DEFAULT NULL,
  `REG_DT` datetime DEFAULT NULL,
  `FILE_NM` varchar(500) DEFAULT NULL,
  PRIMARY KEY (`FILE_REAL_NM`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;




[예제]

 - back-end
 
 (Controller)
 
 ![image](https://user-images.githubusercontent.com/16552382/180374504-dd7764a7-0e55-48b9-9f12-7b1f308cf11b.png)
 
 ![image](https://user-images.githubusercontent.com/16552382/180374717-691ba58f-128b-4827-8746-7a035cfbead5.png)
 ![image](https://user-images.githubusercontent.com/16552382/180374812-ce58480c-5764-4071-adb5-e1980a6dfc6d.png)

 (Service)
 
 ![image](https://user-images.githubusercontent.com/16552382/180375293-e554d865-d627-4f5a-8d8a-64e5db630199.png)

 (ServiceImpl)
 
 ![image](https://user-images.githubusercontent.com/16552382/180375368-58c02755-32b5-4874-a507-05055a829c7e.png)

 (DAO) handler 실행을 위해 기존 list가 아닌 getSqlMapClientTemplate().queryWithRowHandler() 함수를 사용
 
 ![image](https://user-images.githubusercontent.com/16552382/180375428-7e8f1156-bf6c-4e41-b14a-bf43d7bb4068.png)

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

