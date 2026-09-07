## To Do List
- 스핀락 / 뮤텍스 / 세마포어 공부하기
- C#과 C++로 멀티스레딩 개념 강화하기
- 비즈니스 로직 기반 DB 설계 고민하기

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


## 260618
- CMake의 경우 package와 library등 라이브러리 제작한 곳에서 따라 지원하는 명령어가 다르다
- Linux 환경에서 C++ 소켓은 POSIX 함수를 활용할 수 있으니 이를 알아두기


- usbipd의 경우 다른 네트워크에 장치를 흘려주는 툴이다
  - 이때 wsl2의 경우 ip가 달라 다른 네트워크로 분류


## 260619
CMake 공부
	- find_package: CMake를 공식 지원하는 라이브러리
		- find_package(패키지이름, REQUIRED)
		- pkg_check_modules(): CMake 설정 파일도 없고, 단순 .so만 찾기도 애매한 경우.. Linux의 pkg-config의 별도의 파일을 읽음 (.pc 파일)
		- REQUIRED이면 없으면 에러, EXACT 붙이면 정확한 버전, QUIET은 걍 넘어감
	- find_library: CMake 지원 없이 그냥 .so 파일만 있는 경우
	- 추가 포함 디렉터리 기본 경로에 /usr/include가 있으며, 만약 여기에 헤더가 있으면, include_dir 해줄 필요가 읎다 (make install 하는 라이브러리는 다 이럼)
- libusb / libuvc

```
	libuvc ← UVC 카메라 제어 (고수준) 
	↓ 
	libusb ← USB 통신 (저수준) 
	↓ 
	USB 하드웨어
```
- USB 장치는 전부 고유한 VID/PID를 가져요.

```
VID (Vendor ID)   →  제조사 식별자
PID (Product ID)  →  제품 식별자
```

## 260621
# 260609

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
0x1e4e  →  Thermal Imaging 회사 (PureThermal 제조사)
0x0100  →  PureThermal 1/2 보드 제품 ID

이 값은 USB 표준 기관(USB-IF)에서 제조사에게 공식 할당하는 거라 전 세계적으로 고유해요. 그래서 `uvc_find_device()`에 이 값을 넣으면 PureThermal 장치만 정확히 찾을 수 있는 거예요.


## 260622
- git 관련 경험
  - amend를 활용한 커밋 시, 이를 원격에 push할 경우 --force를 붙여야 하니 신중할 것
  - PR 후에 수정 사항을 커밋하면 해당 내역이 자동으로 PR에 등록된다
 

## 260623
```
Rule of Zero는 한 줄로 말하면, 특수 멤버 함수를 직접 하나도 작성하지 않는 것을 목표로 클래스를 설계하라는 원칙이에요.
배경부터 짚을게요. C++에는 컴파일러가 자동으로 만들어주는 특수 멤버 함수가 다섯 개 있습니다. 소멸자, 복사 생성자, 복사 대입 연산자, 이동 생성자, 이동 대입 연산자죠. 이걸 다 직접 챙겨 쓰라는 게 그 유명한 Rule of Five예요. 자원을 직접 관리하는 클래스라면 이 다섯 개를 일관되게 맞춰줘야 버그가 안 생기거든요.
그런데 Rule of Zero는 발상을 뒤집어요. 다섯 개를 잘 작성하는 것보다, 애초에 직접 작성할 필요가 없게 만드는 게 낫다는 겁니다. 어떻게 그게 가능하냐면, 자원 관리를 이미 잘 만들어진 타입에게 위임하는 거예요. raw 포인터로 new와 delete를 직접 다루는 대신 std::unique_ptr나 std::shared_ptr를 멤버로 쓰고, 동적 배열 대신 std::vector를 쓰고, 문자열은 std::string을 쓰는 식이죠.
이렇게 하면 내 클래스는 자원을 직접 소유하지 않아요. 멤버인 vector나 unique_ptr가 알아서 자기 소멸자에서 메모리를 정리하고, 복사나 이동도 알아서 올바르게 처리합니다. 그러니 내 클래스는 소멸자를 쓸 이유도, 복사나 이동을 직접 정의할 이유도 없어져요. 컴파일러가 만들어주는 기본 버전이 그냥 정확하게 동작합니다. 결과적으로 특수 멤버 함수를 0개 작성하게 되는 거고, 그래서 Rule of Zero입니다.
```

## 260624
- 테스트 프로그래밍
	- C++에서 gtest(Google Test)를 하면 테스트 코드 작성을 간소화할 수 있다. 다만 입력값은 여전히 개발자 본인이 생각해서 집어넣어줘야함
	- 다만 rapidcheck을 쓰면 이를 해결할 수 있다. 이는 무작위로 입력값을 넣어주는 라이브러리로 gtest와 조합하면 강력한 테스트 프로그래밍이 가능할듯?
    - 그럼에도, MFC는 모듈 단위 검증이 힘들다. 리소스끼리 서로를 참조하는 스파게티 구조라서.. 그래서 내가 만든 로직 모듈에 대해서만 검증을 거치자.

- 즐거운 문자열 변환
```
1. const char* → std::string가장 쉽습니다. std::string 생성자가 받아줍니다.cppconst char* p = "hello";
std::string s = p;          // 또는 std::string s(p);2. std::string → const char*앞서 본 .c_str(). (수명 주의)cppstd::string s = "hello";
const char* p = s.c_str();   // const char* (읽기 전용, s가 살아있는 동안만 유효)3. const char* → CStringCString 생성자나 대입이 받아줍니다. 유니코드 빌드여도 CString이 알아서 변환해줍니다.cppconst char* p = "hello";
CString cs(p);              // 또는 CString cs = p;4. CString → const char* (또는 LPCTSTR)CString은 LPCTSTR로의 캐스팅을 지원합니다. 단, 이게 빌드에 따라 타입이 다릅니다.cppCString cs = _T("hello");
LPCTSTR p = (LPCTSTR)cs;     // 또는 cs.GetString();유니코드 빌드면 LPCTSTR은 const wchar_t*, 멀티바이트면 const char*입니다. 그래서 "순수 const char*"가 필요하면 유니코드 빌드에서는 한 단계 더 변환해야 합니다(아래 5, 6번 활용). 앞서 Format에서 (LPCTSTR) 캐스팅을 다뤘던 게 이 부분입니다.5. CString → std::string여기가 까다롭습니다. 빌드에 따라 갈립니다.멀티바이트 빌드라면 단순합니다(둘 다 char):
cppCString cs = "hello";
std::string s = (LPCSTR)cs;   // 또는 s = cs.GetString();유니코드 빌드라면 wchar_t → char 인코딩 변환이 필요합니다. 가장 간편한 건 MFC의 CT2A(또는 CW2A) 변환 매크로입니다.cppCString cs = _T("hello");
std::string s = CT2A(cs);        // CString → ANSI(char)로 변환
// 또는 명시적으로: std::string s = CW2A(cs.GetString());CStringA를 거치는 방법도 있습니다.
cppstd::string s = CStringA(cs);    // CStringA로 변환 후 char*로6. std::string → CString이것도 빌드에 따라 갈립니다.멀티바이트 빌드:
cppstd::string s = "hello";
CString cs = s.c_str();       // 단순 대입유니코드 빌드 (char → wchar_t 변환 필요):
cppstd::string s = "hello";
CString cs = CA2T(s.c_str());    // ANSI(char) → CString으로 변환
// 또는: CString cs(s.c_str());  // CString 생성자가 변환해주기도 함
```

## 260625
- Getter와 Setter는 필요할때만 만들자..
- IP를 특정하는 코드를 짜는 것은 어렵다, NIC 때문에

## 260626
- **GUID(Globally Unique Identifier)** 는 전 세계적으로 유일하도록 만든 128비트 식별자입니다. 무언가를 중복 없이 구별해야 할 때 쓰는 "고유 번호표"라고 보면 됩니다.
- 대충 만들어도 128비트라 절대 중복날 일 없음
- C++로 GUID 만들기

```cpp
GUID guid; CoCreateGuid(&guid); // 새 GUID 하나 생성
```

- SDL2 
	- 그래픽, 오디오, 입력 장치 등 하드웨어에 저수준으로 접근할 수 있게 해주는 크로스 플랫폼 멀티미디어 라이브러리입니다. C로 작성됐고, 게임이나 멀티미디어 애플리케이션을 만들 때 널리 쓰입니다.
	- 앞서 검색에서 본 PNM 로더 소스를 떠올려보면, SDL_image는 파일 확장자를 보고 포맷을 정하는 게 아니라 **파일 첫머리의 식별 바이트(매직 넘버)** 를 읽어서 판단합니다. PNM 계열의 경우:

```
PNM 매직 시그니처는 P1은 PBM(ASCII), P2는 PGM(ASCII), P3는 PPM(ASCII), P4는 PBM(바이너리), P5는 PGM(바이너리), P6는 PPM(바이너리)입니다. [GitHub](https://github.com/SDL-mirror/SDL_image/blob/master/IMG_pnm.c)
		
즉 파일을 열어 첫 2바이트가 `P5`인지 `P2`인지를 보고 "아, 이건 PGM이구나"를 알아냅니다. 확장자가 `.pgm`이든 `.foo`든 상관없이, 내용이 PGM이면 PGM으로 읽습니다. 반대로 확장자가 `.pgm`이어도 내용이 깨졌으면 못 읽습니다. `IMG_Load`가 확장자를 참고하는 경우가 있긴 하지만(앞 문서에서 본 것처럼), 그건 보조적 힌트일 뿐이고 PNM처럼 매직 넘버가 있는 포맷은 내용으로 자동 판별합니다.
		
### "1바이트"는 채워 넣는 게 아니라 파일 헤더에서 읽어냅니다
		
그리고 BytesPerPixel이 1이 되는 건, 라이브러리가 ".pgm이니까 1로 적어두자"가 아니라 **PGM 파일 자체의 구조를 파싱한 결과**입니다. PGM 파일은 헤더에 자기 정보를 담고 있습니다. 구조가 이렇습니다.
```

## 260627
- DLL 로딩, extern 등에 대해 복습하기
- 그냥 C++을 되돌아보자
- TCP 소켓을 활용한 멀티 LLM 프롬프트 구조?


## 260629
- extern 클래스 다시 정리하기
- VDA5050 표준 파악하기
- WebView2 파악하기

## 260730
- 코드 줄이 너무 짧으면 sonarqube가 정적분석을 못잡는다 (나 같은 경우에는 중복)
- sourcetree git도 익혀두기
- 특정 branch 작업 중 기능 추가가 필요하면 거기에서 브랜치를 뻗어나가기
- sonarqube 중복의 경우 설정마다 다르겠지만 중복 횟수가 늘어난다고 이것까지 잡진 못한다
- git rebase 공부하기

---

## 260812
- TRACE의 경우에는 debug 구성 환경에서만 사용 가능
- 소켓 통신에서 양단이 클라이언트와 서버를 동시에 갖추는 경우 TCP 재연결 로직에 신경 쓸 것, retry 이후 실패 시, 스레드 등을 이용한 주기적 반복 연결 시도 로직이 필요할 수 있다


## 260820
- 주요 디버깅 메세지
  - 변수가 최적화되어 사용할 수 없습니다
  - 소스코드가 원래 버전과 일치하지 않습니다


## 260903
- pch.h를 cpp에서만 include 하는 이유
  - MSVC(MicroSoft Visual C++ Compiler) 자체가 cpp 시작 시점에 #include "pch.h"를 만날 때 미리 컴파일된 헤더를 로딩하기 때문이다
- hpp는 C++ 전용 헤더 파일로 C 헤더와의 구분을 위한 것


## 260907
- 디자인 패턴: 퍼사드 패턴 (Facade Pattern)
  - 최소 지식 원칙에 따라, 복잡한 절차를 단순화 하기 위해 여러 서브시스템의 시퀀스를 묶는 인터페이스를 만드는 패턴
- 보드에 내장된 코드가 펌웨어라면, 장비에 대한 인터페이스 (ex: Drive()) 와 같은 것이 HAL이다
- `__declspec(dllexport)` : dll을 외부에 공개할 때는 dllexport, 내부일 때는 dllimport
- extern 테크닉: 선언과 정의를 동시에 하기 위한 테크닉
```cpp
#ifdef _DLL_MAIN_CPP_
#define EXTERN
#else
#define EXTERN extern
#endif
```
