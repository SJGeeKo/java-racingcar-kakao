# Calculator
## 설명
- 쉼표(,) 또는 콜론(:)을 구분자로 가지는 문자열을 전달하는 경우 구분자를 기준으로 분리한 각 숫자의 합을 반환 (예: “” => 0, "1,2" => 3, "1,2,3" => 6, “1,2:3” => 6)
- 앞의 기본 구분자(쉼표, 콜론)외에 커스텀 구분자를 지정할 수 있다. 커스텀 구분자는 문자열 앞부분의 “//”와 “\n” 사이에 위치하는 문자를 커스텀 구분자로 사용한다. 예를 들어 “//;\n1;2;3”과 같이 값을 입력할 경우 커스텀 구분자는 세미콜론(;)이며, 결과 값은 6이 반환되어야 한다.
- 문자열 계산기에 숫자 이외의 값 또는 음수를 전달하는 경우 RuntimeException 예외를 throw한다.


## 기능
- 문자열 쪼개기
- 커스텀 구분자
- 더하기
- 예외처리

### 문자열 쪼개기, 커스텀 구분자 예시
- "//;\n1;2;3" -> ["1", "2", "3"]
- "1,2,3" -> ["1", "2", "3"]
- "" -> ["0"]
- null -> ["0"]
- "1, 2, 3" -> ["1", "2", "3"]
- "2,1,-2,a" -> ["2","1","-2","a"]
- "4,,1,2" -> ["4","0","1","2"]

### 더하기 예시
- ["1", "2", "3"] -> 6
- ["2","1","-2","a"] -> RuntimeException

## 클래스 목록
StringSplitter
- 커스텀 구분자 함수
- 쪼개기 함수

SumHelper
- 판단 함수
- 더하기 함수

---
# RacingCar
## 설명
- 주어진 횟수 동안 n대의 자동차는 전진 또는 멈출 수 있다. 
- 각 자동차에 이름을 부여할 수 있다. 전진하는 자동차를 출력할 때 자동차 이름을 같이 출력한다.
- 자동차 이름은 쉼표(,)를 기준으로 구분하며 이름은 5자 이하만 가능하다.
- 사용자는 몇 번의 이동을 할 것인지를 입력할 수 있어야 한다.
- 전진하는 조건은 0에서 9 사이에서 random 값을 구한 후 random 값이 4 이상일 경우 전진하고, 3 이하의 값이면 멈춘다.
- 자동차 경주 게임을 완료한 후 누가 우승했는지를 알려준다. 우승자는 한 명 이상일 수 있다.

## 기능
- 입력 / 출력
  - 이동횟수 입력
  - 차 이름 / 이동거리 출력

- 이름 할당 (자동차 생성)
  - 5자 이하만 가능
  - 쉼표 기준 구분
- 반복 (이동횟수)
- 우승 판단

- 랜덤값 생성
  - 0부터 9
- 랜덤값 판단 (이동/정지)
  - 4 이상 전진

## 클래스 목록
**IOHelper**
- 입력
- 출력


**Validator**
- 차 이름 입력 유효성 검증
- 시도 횟수 입력 유효성 검증
- 구현체: **BasicValidator**

**Game**
- 차 목록 / 남은 라운드 횟수
- 게임 시작(차 정보 초기화)
- 이동횟수만큼 Car 인스턴스들을 이동
- 게임 종료시 우승자 판단
- Dto
  - **GameInfo**

**Car**
- 이동거리 / 이름
- 이동시 랜덤 생성 및 판단
- Dto
  - **CarInfo**

**Movable**
- Car의 이동 조건 설정을 위한 함수형 인터페이스
