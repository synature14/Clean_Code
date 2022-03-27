# Clean Code?


## 들어가며

운영업무를 하다보니, 레거시 코드 기반으로 수정하거나 추가해서 구현해야하는 일이 있었습니다. 앱 기동 프로세스, 자동로그인 체크, 로그인 화면을 띄우는 등 로직은 단순한데 구조가 얼키고 설킨 상태라 로그인 수단을 하나 추가하는 것 뿐인데 건드려야할 부분과 사이드 이펙이 많았던 경험이 있었습니다. 

그때마다 ‘이게 최선일까?’라는 질문을 스스로하며 좋은 아키텍처에 대한 갈증이 있었습니다.

이 책을 통해, 좋은 코드란 무엇인지 조금 알게 된 것 같습니다.

팀원 의견, 각 프로젝트 환경과 도메인에 따라 ‘Clean Code’의 정의는 조금씩 다를 것 같습니다만, 기본적으로 모두가 공감할 것 같은 요소들을 다음과 같이 추려보았습니다.


## 목차

[나쁜 코드 vs. 깨끗한 코드](https://github.com/synature14/Clean_Code/blob/main/객체와%20자료%20구조.md)

[그래서 의미 있는 이름이 무엇일까?](https://github.com/synature14/Clean_Code/blob/main/%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%89%E1%85%A5%20%E1%84%8B%E1%85%B4%E1%84%86%E1%85%B5%20%E1%84%8B%E1%85%B5%E1%86%BB%E1%84%82%E1%85%B3%E1%86%AB%20%E1%84%8B%E1%85%B5%E1%84%85%E1%85%B3%E1%86%B7%E1%84%8B%E1%85%B5%20%E1%84%86%E1%85%AE%E1%84%8B%E1%85%A5%E1%86%BA%E1%84%8B%E1%85%B5%E1%86%AF%E1%84%81%E1%85%A1%3F.md)

[좋은 함수란?](https://github.com/synature14/Clean_Code/blob/main/%E1%84%8C%E1%85%A9%E1%87%82%E1%84%8B%E1%85%B3%E1%86%AB%20%E1%84%92%E1%85%A1%E1%86%B7%E1%84%89%E1%85%AE%E1%84%85%E1%85%A1%E1%86%AB%3F.md)

[좋은 주석?](https://www.notion.so/34f905980dc14c7f9addbc4f0752e575)

[형식 맞추기](https://www.notion.so/c226e9aa31ea4ede879985e6a9c8a2ae)

[객체와 자료 구조](https://www.notion.so/b6da7471dac647358365d0654b93fa5d)

[오류처리를 어떻게 clean하게 할까?](https://www.notion.so/clean-4a4cd1e9840549d2b33fb71529eff0e5)

[외부 코드를 어떻게 사용해야하나?](https://www.notion.so/5a376737a59d476ca87d993543e213b7)

[Clean Test Code](https://www.notion.so/Clean-Test-Code-d6e9e0d8d3e846419d1e4d49db95c1a6)

[Clean 클래스](https://www.notion.so/Clean-9e6743fad38040d1b4c599d959a6d5a3)

[Clean 시스템을 어떻게 구현하나?](https://www.notion.so/Clean-c07fe3e7608746499c3a3a461d49633d)

[Clean 설계란?](https://www.notion.so/Clean-90f47975ea7b4b968340ffd5a844bf69)

[Clean 동시성 코드라는걸 어떻게 보장할까?](https://www.notion.so/Clean-59ffa27a73d74bfa90b52176e6c8a22c)

[점진적인 개선](https://www.notion.so/9e3a92b2bb1a4dbb8fb3ba96085f273d)


## 💬 Clean Code 정의를 마주한 소감

**[스펙 구현 >>> 아키텍처, 클린 코드]** 
한번도 클린코드에 관한 책을 읽은 적이 없었는데, 생각보다 제 개인적인 코드 컨벤션과 비슷한 면도 있다는 점에 놀랐습니다. 
그리고 특히나 모바일 앱개발에 있어 레이어를 나누고 아키텍처를 clean하게 가져가는 것도 중요하지만, **더 중요한것은 서비스 스펙을 구현(구조나 클린코드를 위반해야 구현할 수 있는 애니메이션/화면이동 등) 하는것이 더 우선순위이기 때문에 ❗️ 두 가지가 충돌 하는 경우,** 아키텍처 클린코드 보다는 스펙 구현이 우선순위라고 생각합니다.


## 참고

[로버트 C. 마틴](https://www.aladin.co.kr/search/wsearchresult.aspx?AuthorSearch=%eb%a1%9c%eb%b2%84%ed%8a%b8+C.+%eb%a7%88%ed%8b%b4@182538&BranchType=9) [****클린 코드 Clean Code -**** 애자일 소프트웨어 장인 정신]
