# 소켓기반 네트워크 게시판
Server클래스와 Client클래스로 구성. 
소켓을 이용 Client서버 콘솔창으로 입력받은 내용을 Server서버에 저장하여 관리합니다.

## 개발환경
![js](https://img.shields.io/badge/Eclipse-2C2255?style=for-the-badge&logo=eclipse&logoColor=white)

## 프로그래밍 언어
![js](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)

## 주요 메서드
### Server 클래스(Server.java)
1. **메인 메서드(main)**:
   - 서버 소켓을 생성하고, 클라이언트의 접속을 대기합니다.
   - 클라이언트가 접속하면, 해당 클라이언트 소켓에 대한 처리를 담당하는 `ClientHandler` 스레드를 생성하고 시작합니다.

2. **ClientHandler 클래스**:
   - 클라이언트 소켓에 대한 처리를 담당하는 내부 클래스입니다.
   - 각 클라이언트별로 별도의 스레드가 실행되며, 클라이언트로부터 받은 명령을 처리합니다.
   
3. **run 메서드**:
   - 클라이언트로부터 명령을 읽고, 해당 명령에 따라 작업을 수행합니다.
   - "LIST": 게시물 목록 조회
   - "ADD": 새로운 게시물 추가
   - "UPDATE": 게시물 수정
   - "DELETE": 게시물 삭제
   - "EXIT": 클라이언트 종료
   
4. **getPostList 메서드**:
   - 게시물 목록을 문자열 형태로 반환합니다.

5. **addPost, updatePost, deletePost 메서드**:
   - 게시물 추가, 수정, 삭제 기능을 수행합니다.

### Client 클래스(Client.java)
1. **메인 메서드(main)**:
   - 서버에 연결하고, 사용자 입력을 받아 서버로 전송하고 서버로부터 응답을 받아 출력합니다.

2. **사용자 입력 및 요청 전송**:
   - 사용자에게 제공되는 메뉴를 통해 조회, 추가, 수정, 삭제를 선택할 수 있습니다.
   - 선택에 따라 서버에 요청을 전송하고, 필요한 데이터를 함께 전송합니다.

3. **서버 응답 수신 및 출력**:
   - 서버로부터 받은 응답을 화면에 출력합니다. 주로 게시물 목록 조회 시 사용됩니다.

이렇게 서버와 클라이언트는 사용자 요청을 받아 처리하고, 그에 대한 결과를 주고받습니다. 이러한 상호작용을 통해 원활한 통신이 이뤄집니다.

## 실행화면
![image](https://github.com/welcomeglory/NetworkBulletinBoard/assets/153584777/608572d1-b18e-4d19-a519-1b29a52ecab5)

    

