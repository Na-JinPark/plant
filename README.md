# 식물 관리 서비스

키우는 식물을 관리하고 다른 사용자와 소통 및 관련 용품을 구매할 수 있는 식물 관리 서비스 입니다.

## 프로젝트 기능

1. 회원 관리
    - 회원 가입
        - 네이버, 카카오를 통한 회원가입
        - 아이디, 비밀번호, 닉네임 입력을 통한 회원가입
        - 사용자 아이디, 비밀번호, 닉네임, 회원 유형 (사용자, 판매자) 정보를 저장한다.
    - 로그인 및 로그아웃
        - jwt 토큰 사용
2. 나의 식물 관리
    - 식물 등록
        - 사용자는 자신이 키우는 식물 정보를 등록할 수 있다.
            - 식물이름, 식물 별칭, 식물 사진, 키우기 시작한 날짜 정보를 저장한다.
    - 식물 별 관리 일정 등록
        - 관리 일정 등록（물주기, 분갈이 등）
            - 관리 날짜 와 시간, 관리 내용 정보를 저장한다.
        - 시간을 입력 한 경우 해당 시간에 알림 기능
            - 알림 기능은 스케줄러를 자정마다 실행하도록 설정하여 관리 목록 테이블에서 현재날짜로 저장된 데이터를 가져와 메시지 큐에 저장하고 만약 사용자가 당일 예약 알림을 등록할 경우 메시지 큐에
              직접적으로 넣어준다.
              메시지 큐에 있는 데이터는 스케줄러를 1분마다 실행하도록 설정하여 현재 시간과 비교하여 시간이 같을 경우 알림을 푸시하는 방식으로 구현할 계획
3. 식물 검색 기능
    - 식물 검색시 해당 식물에 대한 정보 조회
        - 농사로 - 실내정원용 식물 api사용
          식물 설명, 생육 온도 및 습도, 관리 정보 , 난이도, 발화계절, 배치 장소 등의 데이터를 받아와서 보여준다.
4. 커뮤니티 관리
    - 게시글 등록
        - 게시글 제목, 내용, 사진, 게시글 작성자 정보를 저장한다.
    - 게시글 검색
    - 댓글 등록
        - 게시글아이디, 댓글 작성자, 댓글 내용 정보를 저장한다.
    - 좋아요
        - 게시글 아이디, 사용자 아이디 정보를 저장한다.
5. 스토어 관리
    - 상품 등록
        - 로그인한 사용자가 판매자인 경우만 가능
        - 스토어 이름, 판매자 아이디, 스토어 설명, 주소, 번호 정보를 저장한다.
    - 상품 등록
        - 판매할 상품을 등록한다.
        - 스토어아이디, 상품 이름, 상품 설명, 가격 정보를 저장한다.
    - 주문 등록
        - 사용자의 수문 정보를 등록한다.
        - order테이블에 구매자, 받는사람, 주소, 전화번호 정보를 저장하고
          order_detail테이블에 해당 주문 건에 대한 상품과 수량 정보를 저장한다.
    - 결제 시스템 (Iamport api)
    - 리뷰 등록
        - 상품을 구매한 사용자에 한해서 리뷰를 등록할 수 있다.
        - 리뷰 내용, 리뷰 사진 정보를 저장한다.
          <br>

# ERD

<img width="802" alt="erd" src="https://github.com/Na-JinPark/Plant/assets/119678193/a409114d-1d63-4e93-9193-ead34dc6126b">
<br>

# Trouble Shooting

<br>

# 사용 기술(Tech Stack)

<div align=left> 
  <img src="https://img.shields.io/badge/java-007396?style=for-the-badge&logo=java&logoColor=white"> 
  <img src="https://img.shields.io/badge/mysql-4479A1?style=for-the-badge&logo=mysql&logoColor=white"> 
  <img src="https://img.shields.io/badge/spring-6DB33F?style=for-the-badge&logo=spring&logoColor=white"> 
  <img src="https://img.shields.io/badge/git-F05032?style=for-the-badge&logo=git&logoColor=white">
</div>
