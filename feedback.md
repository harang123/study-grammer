# 1/3 review

## PS
### 구름 ide - 약수 구하기
`23 123 31 23` 이런식의 출력을 해야하는 거라면, 반복문으로 매번 출력문을 돌려야하는지?
JS는 배열에 join 메서드가 있음(다트도 유사한 게 있을 것)

### 구름 ide - 369게임
정규식은 지금 공부할 필요는 없음
그리고 없어도 쉬운 문제
JS 풀이인데 반복문의 도는 값을 문자열로 바꾼뒤 스플릿해서 체크해주면 됨
```
  const tsn = ['3','6','9']	const N = Number(line)
	const tsn = ['3','6','9']
  let cnt = 0
  for(let i = 1; i < N; i++){
    String(i).split('').forEach(val => {
      if(tsn.includes(val)){
        cnt+= 1
      }
    })
  }
  console.log(cnt)
```
### 구름 ide - 최소값
최소값을 반복문을 돌면서 찾는데, 배열메서드나, 다른 방법으로 최소값을 구하는 방법이 분명히 있을 것임
map 함수는 배열메서드로
ex)\_ arr.map(int.parse) 라면
arr 배열을 돌면서 순차적으로 배열값에다가 () 의 함수를 적용해줌
새로운 배열 [int.parse(첫번쨰 배열값),int.parse(두번쨰 배열값) ...]

---

## Grammer
- MD 문법을 좀 공부하고 작성할 것
  -  코드 부분, 제목이 없음(중요도에따라)
- 보기가 힘들다.


# 1/4 review

## Grammer

List 심화

1.  심화라는 표현은 적절하지 않은듯 기본적인 메서드 사용임
2.  forEach 함수의 특징
    따로 return 값을 받지 않는다. -> 리턴값을 받는 함수는 없음 결과값을 리턴하는게 함수
    forEach함수 안에서 모든 것을 해결한다. -> ?
    이부분이 무슨 말인지 모르겠음. 그냥 배열메서드로, 배열의 값들을 순차적으로 돌리는게 다임

    ```
      const arr = [1,2,3,4,5]
      for(let i = 0; i < arr.length; i++){
        console.log(arr[i]) // print랑 동일
      }
      arr.forEach((v) => {
        console.log(v)
      })
      둘은 동일하게 동작함
      하지만 반복문과 다르게 개발자가 신경써줄 포인트가 줄어듦
    ```

3.  map 함수의 특징
    1.  map은 해당 리스트를 새로운 값이나 새로운형태로 바구고 싶을 때 사용한다.
        1. 배열의 값들을 변경해 새로운 배열을 리턴함
        2. 배열의 값을 바꾸는거는 파라미터로 넣는 함수의 내용대로
    2.  forEach와 다르게 리턴값을 받는다. -> 오류
        1. 맵함수의 파라미터로 함수를 넣는거고 그 함수 안에 리턴값이 있는 것임
        2. 그래야 기존배열의 배열값 -> 함수를 적용한 새 배열값으로 변경 가능

Map

1.  정의 : map 또한 List와 마찬가지로 하나의 변수에 여러개의 값을 넣을 수 있다.
    1. map, array는 자료구조라고 표현하는게 더 적합한듯

## PS

새로운 문제 없음

## etc

- 1. 어제 어떤걸 공부했는지 명확하지 않음
     브런치를 일자별로 만들고, 마무리 할 때, 메인 브런치로 머지하는 식으로 작업 할 것

- 2. stydy-grammer readme 마지막 부분에 왜 피드백에 들어갔는지 모르겠음

# 1/5 review

## PS

문자열 형식으로 입력받아 리스트를 만드는 것을 생각못해 많은 시간을 잡아먹었던 문제였다. arr.map(int.parse)에 대한 이해가 아직 부족함으로 좀 더 공부할 예정이다.
- arr.map(parameter) map method는 함수를 parameter로 받고, 
- parameter에 들어가는 함수의 파라미터에 배열 메서드(map)에서 제공하는 파라미터를 자동으로 넣어줌 JS는(value, idx, ... , ...) 뒤에 2개는 기억이 안남 잘안씀
- 그래서 int.parse(val) 라고 명시적으로 적어주지 않아도 되는 것임
```
ex
예시코드
arr.map(int.parse) === arr.map((val) => int.parse(val))
// dart도 화살표 있다는데, 이렇게 쓰는게 정확한진 모름
```

구름 ide - 시험성적 평균과 등급 구하기
아래의 코드같은 애들은 앞으로 reduce 메서드로 구현할 것(fold도 reduce랑 비슷한거같던데 설명 카톡으로 보내주세요)
```
int count = 0;
	arrInt.forEach((value){
		count += value;
	});
	double aver = count / 3; // if문에서 비교식에 사용하기 위하여 평균값을 변수에 받아주었다.
	
```
구름 ide - Min 함수  이런느낌 굿!

구름 ide - 네 수의 곱
작은 부분들을 쪼개서 함수로 만드는 느낌은 좋음
그런데 이거 reduce면 한줄임
```
void main() {
	String line = stdin.readLineSync(); // 공백으로 값을 입력받기 때문에 String으로 입력받는다.
	List<String> arrLine = line.split(' ');  // 각각의 값들을 따로 사용해야 하기때문에 List에 값을 분리해 넣어준다.
	List<int> arrInt = arrLine.map(int.parse).toList();  // String형식의 List를 int형식의 List로 변환하여 준다.

	print(multi(arrInt[0], arrInt[1], arrInt[2], arrInt[3])); // multi 메서드를 만들어 사용하여 네 정수의 곱을 출력한다.
}

int multi(int a, int b, int c, int d)
{
	return mul(mul(a, b), mul(c, d));  // mul 메서드를 생성하여 네 정수의 곱을 구하는 multi 메서드를 만든다.
}

int mul(int a, int b)
{
	return a * b;
}
```
구름 ide - 특정 문자 개수 구하기
`// 쨀 처음 입력받은 문장을 공백을 이용해 분리하였음에도 완전히 분리가 안되었기때문에 한번 더 분리하였다.` 
문자열을 모두 개별로 쪼갤려면 처음부터 `value.split('')` 쪼개야됨 
위에서 잘못쪼개서 아래에서 다시 쪼깨는 이런 식의 코드는 반드시 리팩토링 할 것

구름 ide - 3의 배수 게임
- 접근 방식 좋음.
- for 문 말고 다른 방식으로도 작성할 것

구름 ide - 비트연산 기본 1
비트연산 같은 경우는 웹개발에서 전혀 할일이 없어서 저도 안해봄
**여러가지 방법으로 풀어보고 싶어 다양하게 풀어봤던것 같다.** ^^

## grammer
- 뭘 어제 공부한 건지 찾기가 힘들게 만들어 놓음
- 그래도 전체적인 가독성이 좋아짐

## etc
- PS,grammer 둘다 최신날짜 브런치에 모든 내용이 다 있고, main이 뒤에있음
  - 공부를 main에서 하다가, 하루 마무리 할 때, 
  - 메인 브런치를 올리고(전체 학습 내용기록에 오늘 내용 추가 됨)
  - 일자 브런치를 만듦
  - 일자 브런치 안에서 오늘 학습한 내용을 제외한 모든 내용 삭제
  - 일자 브런치 push 하면 됨
- 사실 어제 피드백 작성할 때, 화요일 공부량이 너무 작은거 같았는데
- 오늘은 쫌 한 것 같네요. 전업 취준생인만큼 앞으로 계속 빡세게 했으면 좋겠습니다
- 회사 10시 출근인데 본인도 아침에 나와서 30~40분씩 보고 피드백 작성중임

 # 1/6 review

 ## PS
- feedback에 대한 개선 ## 3의배수
  - map 함수 안에서 value를 변경한다음 리턴하지말고 그냥 리턴 하는게 더 좋습니다.
  - 변경하는 부분을 최소화하는게 안전
    List<String> arrResult = arr.map((value){
      value = i++;
      if((i - 1) % 3 == 0){
        return 'X';
      }
      return value;
    });
- 구름 ide - 가위바위보
  - 본인이 직접 작성해서 푼 것 같은데, 실력이 좀 느는 것 같네요!
  - 푸는게 1순위, 좋은 코드를 작성하는게 그 다음.
  ```
  배열 한번만 돌려도 되는데 3번 쓴건 이게 더 가독성이 좋은 것 같아서(선택임)
  const inputList = line.split(" ");
  const scissors = inputList.filter((v) => v === "1").length;
  const rock = inputList.filter((v) => v === "2").length;
  const paper = inputList.filter((v) => v === "3").length;
  const ans = check(scissors, rock, paper);
  console.log(ans)

  function check(scissors, rock, paper) {
    const arr = [scissors, rock, paper];
    const zero = arr.filter((v) => v === 0).length;
    if (zero !== 1) {
      return 0
    }
    if(arr.indexOf(0) === 0){
      return arr[2]
    }
    if(arr.indexOf(0) === 1){
      return arr[0]
    }
    if(arr.indexOf(0) === 2){
      return arr[1]
    }
  }

  ```

## Grammer
없음
## etc
어느정도 문법은 익숙해지면서 문제 푸는 것 같네요.
어제 뭘 공부했는지 제가 확인하기도 편하고 좋습니다.
하루에 얼마정도 공부하는지 알려주세요.
	

# 1/7 review

## PS

- 구름 ide - 피라미드

  - i 값을 외부로 빼고, 올려주는데 JS 배열메서드는 두번째인자로 index를 받음
  - dart도 문법이 비슷해 있을 수도 있음, 체크 `ex_(arrLine.forEach((val, idx){})`

- 구름 ide - 인공지능 청소기
  - N에서 x,y좌표의 절대값을 뺀 값이 2로 나누어 지면 그 좌표는 어디던 N번째에 도착을 할 수 있다는 뜻이므로 조건으로 사용할 수 있다.
  - 이 조건을 알아야 풀 수 있는 문제인데, 검색없이 푸셨는지?

## Grammer
없음

# 1/8 review

## PS
없음
## Grammer
없음
	
# 1/9 review

## 요구사항
- 날짜별 브런치는 그날 공부한 내용만 있도록 작성할 것
- 깃 관련 내용 브런치 내용 수정할 것
- flutter-docs 레포를 만들고, 플러터 공홈 docs 내용 읽고 정리할 것
  - 외울 필요 없음
  - 자주 쓰는 것들은 저절로 외워지고, 어쩌다 쓰는건 그냥 찾아보면 됨
  - 독스를 3번 정독하고, 유튜브나 어디든 타 학습자료 찾아 볼 것
