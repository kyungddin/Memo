## To Do List
- 스핀락 / 뮤텍스 / 세마포어 공부하기
- C#과 C++로 멀티스레딩 개념 강화하기
- 비즈니스 로직 기반 DB 설계 고민하기
 

## roadmap
- 4월: DB, Computer Network
- 5월: GUI, C++
- 6월: TEST


---


## 260503
- MAC vs IP, 둘을 비교해서 좀 더 공부하기
- 클라우드 서버를 기반으로 통신하는 프로그램 구상하기
- JSON, HTTP 파서 만들기 (C++? Python?)


## 260504
- 포인터의 레퍼런스
  - **와 *& 전부 가능하다
  - 다만 C Style은 **
  - C까지 호환되는 라이브러리 쓸 때는 보통 **로 선언되어 있음
    
- XML과 DOM Tree research하고 정리하기


## 260506
- git branch 생성 관련 테크닉
  - `$ git checkout -b <name>` 로 새로운 브랜치 생성
  - `$ git push --set-upstream origin feature/haha` 로 새로운 브랜치에 대해 원격에 push


## 260507
- SQL에서 Column이 ROM인 경우가 있는데 왜 그런지 Research

- C/C++에서 path를 상대경로로 지정하면 빌드된 exe 파일을 실행할 때 에로사항이 발생할 수 있다
  - 따라서 절대경로와 출력 디렉터리 설정을 적절하게 해줄 필요가 있음

## 260508
- `$ git config --global --get pull.ff` 를 해줘야 fast forward 없이 merge가 가능하도록 기본값이 바뀜
  - fast forward를 고려해서 브랜치를 관리하는 연습을 해보기


## 260509
- git commit 메시지는 제목과 본문이 나뉜다
  - 제목과 본문 사이에 빈 줄이 반드시 있어야 한다
  - CLI에서 merge 할 때도 이것이 적용된다

- git config 범위 플래그
  - `--system`: 이 컴퓨터의 모든 사용자
  - `--global`: 이 컴퓨터의 현재 사용자
  - `--local`: 해당 디렉터리 git에만

- python virtual env 정리

  ```markdown
  # 프로젝트 폴더에서
  python -m venv .venv              # 가상환경 생성
  source .venv\Scripts\activate            # 활성화 (Windows: git bash)
  pip install -r requirements.txt   # 패키지 설치
  # ... 작업 ...
  deactivate                        # 비활성화
  ```


## 260510
- StockMonitor 작업 내용
  - PySide6 기본 구조 이해
  - 커스텀 타이틀바 코드 분석
  - 네이버 금융 API JSON 구조 파악

- Git Alert 작업 내용
  - PySide6 타이틀바 코드 분석
  - GitHub Webhook + ngrok + Flask + winotify 연동
  - 방해금지 모드와의 전쟁 승리


## 260511
- Git Alert에 .env 추가하기


## 260512
- git에서 원격 브랜치 특정 커밋 삭제하기 (주의)
  - `$ git reset --hard` 로 특정 커밋 날리기
  - `$ git push origin 브랜치명 --force`로 해당 결과물 강제로 원격에 push

- git에서 merge가 완료된 feature는 삭제하자 (재사용 금지!)
  - `$ git branch -d feature/브랜치명`
  - `$ git push origin --delete feature/브랜치명`


## 260513
- C++ MFC 디버깅 팁
  - AssertValid()에 중단점 걸면 메모리 크러시 없이 추적을 진행할 수 있다

- C++ MFC Create Style
  ```markdown
  WS_  Window Style  윈도우 공통 스타일
  ES_  Edit StyleEdit  컨트롤 전용 스타일
  BS_  Button   StyleButton 컨트롤 스타일
  SS_  Static   StyleStatic 컨트롤 스타일
  LBS_  ListBox   StyleListBox 스타일
  CBS_  ComboBox   StyleComboBox 스타일
  SBS_  ScrollBar   StyleScrollBar 스타일
  TBS_  TrackBar   StyleTrackBar(슬라이더) 스타일
  PBS_  ProgressBar   StyleProgressBar 스타일
  WS_  EX_Window Style Extended  확장 윈도우 스타일
  ```

- C++ 동적 배열 생성
  ```cpp
  std::vector<CChartBalloonLabel<SChartXYPoint>*> pLabel(size);
  ```
  - 그냥 이런식으로 vector로 패자

- git --amend
  - `$ git commit --amend` 를 쓰면 이전 커밋과 합친다
  - `$ git commit --amend --no-edit` 을 하면 커밋 메시지 그대로 유지한다!


## 260514
- `$ git fetch --prune` ?
  - git fetch 동작에 대해서는 더 공부할 필요가 있어 보임


## 260515
- 전방 선언을 하지 않으면, 특정 클래스의 헤더를 가져와도 멤버 변수로 지정을 못하는 경우가 왕왕 발생하는데
  - 전방 선언에 대해 제대로 공부할 필요가 있어보인다
- C++ MFC에서 각 리소스에 대한 포인터 초기화에도 부모/자식별로 쓰이는 함수가 다 다르다


## 260516
- C++ 클래스 전방 선언
  - 특정 클래스에서 다른 클래스를 포인터로 사용할 때, 미리 해당 클래스가 필요하다는 것을 알려줌
  - 사용 가능한 경우
    - 클래스 멤버 포인터
    - 클래스 멤버 참조
    - 함수 매개변수/반환형 (포인터/참조)
  - 불가능한 경우
    - 객체 자체가 멤버인 경우
    - 멤버 함수를 호출하는 경우
    - 즉, 클래스 내부 정보를 진짜로 알아야 하거나 메모리에 배치해야 하는 경우
  - 보통 프로젝트에서는 헤더에서 클래스 전방 선언을 하고, 실제 include는 cpp 소스 파일에서 선언
  - #include를 하고 전방 선언을 안 했을 때 클래스 포인터 오류가 나는 이유
    - 순환 참조 (무한 루프)
    - 순환 참조를 `#pragma once` 와 같은 가드로 막아도, 해당 헤더의 일부만을 읽는 식의 오류가 발생
    - 이를 방지하기 위해 전방 선언을 사용하는 것

- SonarQube Test
  - Sequrity Spot: strlen or wcslen
    - 이 두 함수는 기본적으로 string이나 wide character 문자열이 nullptr이 아니라는 가정하에 짜여진 함수이다
    - 따라서, 예외처리 로직이 앞서 선행 되지 않으면 undefined behavior, 즉 미정의 동작 발생 가능성이 있다


## 260518
- `git push --force-with-lease` 를 써서 --amend 커밋에 대해 강제 push


## 260522
- git config에서 user 정보는 local과 global이 나뉘어 적용될 수 있다
- UML 클래스 다이어그램 접근 제어자
  - 기호(+): public
  - 기호(-): private
  - 기호(#): protected


## 260526
- rebase를 쓰면, base 커밋을 옮기면서 브랜치를 정리해주기 때문에.. merge에 비해 그래프가 깔끔해질 수 있다
- 그러나 base 커밋을 git에서 자동으로 강제 정리하므로, git이 좀 숙련되면 써주자..
- gitignore의 경우 !를 사용하면 예외처리를 할 수 있지만 항상 먹히지 않는다


## 260529
```markdown
std::thread기본 스레드 생성std::async / std::future비동기 작업 + 결과 수령std::mutex / std::lock_guard상호 배제std::condition_variable스레드 간 신호std::atomic원자적 연산std::jthread (C++20)join 자동화된 threadstd::latch / std::barrier (C++20)동기화 포인트

+ Windows API Thread 연습
#include <windows.h>

HANDLE h = CreateThread(nullptr, 0, task, nullptr, 0, nullptr);
WaitForSingleObject(h, INFINITE);
CloseHandle(h);
```
- 객체 배열의 경우 당연히 크기를 알아야하므로 전방선언이 안 먹는다


## 260601
- this는 호출 시점의 실제 객체 (windows.h의 스레드를 공부하며)
- IS-A 관계에서는 public 상속 (실무에서 private 상속인 HAS-A 관계가 나올 일은 잘 없다)
- 순수 가상 소멸자가 존재하는 이유는 하나야. AGVState 자체는 추상 클래스로 만들고 싶은데, 다른 순수 가상 함수가 없을 때 소멸자에 = 0 붙여서 추상 클래스로 만드는 트릭이야.


## 260603
- 읽은 책 정리하기
- 옵시디언 사용법 익히기
- 기술 스택 정리하기


## 260609
- boost::asio 비동기 I/O 처리를 위한 C++ 라이브러리
	- 네트워크 통신, 타이머, 파일 I/O에 사용됨
	- WinSock API 보다, 소켓 통신이 훨씬 간편하다~
- 스태틱 함수는 멤버 변수에 직접 접근이 불가 (대신에 LPVOID lpData 테크닉 이용)
	- CreateThread()에서, 함수 다음에 this를 넣어주면 lpData에 this가 들어감
	- 대신에, 나중에 활용할 때 명시적 형변환 해줘야겠지..?
- WinSock에서 recv()-send() 루프는 블로킹 (정확히는 recv)
	- asio는 기본이 비동기(~= 논블로킹)
- 패킷 직렬화
	- // 구조체 그대로 전송하면 될 것 같지만
		struct PDU { int cmd; int result; int len; char data[1024]; };
		send(sock, (char*)&pdu, sizeof(pdu), 0);
		
		// ❌ 문제 발생
		// 1. 패딩 - 컴파일러마다 구조체 정렬 다름
		// 2. 엔디안 - x86(리틀) vs ARM(빅) 다를 수 있음
		// 3. 크기 낭비 - data[1024] 중 10바이트만 써도 1024 전송
- 우리가 소켓 통신에서 지정하는 헤더는.. 어플리케이션 헤더다
	- struct PACKET_HEADER
		{
		int m_iCmdType;   // "이게 어떤 명령이야"  → 수신측이 어떻게 처리할지 결정
		int m_iResult;    // "성공이야 실패야"     → 응답 패킷일 때 결과 전달
		int m_iDataLen;   // "뒤에 N바이트 읽어"  → 패킷 경계 구분
		};
	- DataLen이 사실상 유일한 필수값

## 260610
- MFC 이쁘게 그리는 갓크닉
  - CMFC 리소스로 대체
  - MFC 클래스 오버라이딩


## 260611
- 왜인지는 모르겠는데 커스텀 스플리터 쓰면, 더블 버퍼 깨짐


## 260612
- MFC 클래스 오버라이딩으로 Ui 개선


## 260614
1. Getter에서 return 타입이 객체이면 const &를 붙여서 복사 방지
2. getter에 함수에 const를 붙이는 이유
첫째, const 객체에서도 호출 가능해져. const 없으면 const 객체에서 Getter 호출 자체가 안 돼.
둘째, 실수로 멤버 변수를 수정하면 컴파일 에러가 나줘서 버그를 미리 잡아줘.
3. getter return 타입에 const를 붙이는 이유
ibh.GetCurNode() = "다른노드"; // 원본 멤버 변수가 바뀌어버림
이런 거 막으려고


- usbipd의 경우 다른 네트워크에 장치를 흘려주는 툴이다
  - 이때 wsl2의 경우 ip가 달라 다른 네트워크로 분류
