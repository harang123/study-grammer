# 헷갈리는 개념정리 

#### 오버로딩과 오버라이딩의 차이점
1. 오버로딩
- 메서드의 이름은 같고 매개변수의 갯수나 타입이 다른 함수를 정의하는 것을 의미한다.
- 리턴값만을 다르게 갖는 오버로딩은 작성할 수 없다.
2. 오버라이딩
- over + ride = 먼가 위에서 달린다?
- 상위 클래스의 메소드를 하위 클래스가 재정의 하는 것이다.
- 메서드의 이름은 물론 파라미터의 갯수나 타입도 동일해야 하며, 주로 상위 클래스의 동작을 상속받은 하위 클래스에서 변경하기 위해 사용된다. 
즉 오버로딩은 기존에 없던 새로운 메서드를 정의하는 것이고, 오버라이딩은 상속받은 메서드의 내용만 변경 하는 것이다.
 

#### 상수
정의 : 변수와 마찬가지로 데이터를 저장할 수 있는 메모리 공간을 의미한다.

하지만 상수가 변수와 다른 점은 프로그램이 실행되는 동안 메모리에 저장된 데이터를 변경할 수 없다는 점이다.
상수에는 정수형, 실수형, 문자형 상수가 있다. 

매개변수와 인수의 차이점
매개변수는 함수를 정의할 떄 사용되는 변수를 의미한다. 

	ex) int add(int x, int y){
	    return x + y; 
	}
여기서 (int x, int y) <- 이것을 매개변수라고 한다. 
그렇다면 인수는 무엇인가? 인수는 함수가 호출될 때 매개변수에 실제로 담기는 값을 의미한다.
ex) 위의 add 함수를 호출할때 add(2, 7); 이렇게 사용하게 되는데 이때 들어간 (2, 7)을 인수라고 한다. 

#### private 변수 선언방법
변수를 생성할때 변수명의 시작을 _로 해준다.
ex) _id;
이렇게 변수명을 적어주게되면 private 변수라는 뜻이다. 

#### 로컬 저장소와 원격저장소
- 로컬 저장소 : 현재 사용하고 있는 컴퓨터 내부에 저장되어지는 곳!
- 원격 저장소 : git hub와 같이 원격으로 업로드를 할 수 있는 곳을 뜻함!

****
# List

#### 정의 : 여러개의 값을 저장할 수 있는 클래스이다.(배열)
List의 선언 방법은 여러가지가 있는데 우선 유동적인지 고정되어있는지를 기준으로 나눠보겠다.
1. Growable List -> List arr = []; or List arr2 = new List();
2. Fixed Length List -> List arr3 = new List(List의 크기); 

1번 방식일때는 아래와 같이 List 요소를 추가, 삭제, 변경이 가능하다.
리스트 요소 추가방법 : arr.add(값);
리스트 요소 지우는 방법 : arr.removeAt(index);
리스트 요소 변경하는 방법 : arr[index] = 값;

2번 방식은 List를 생성할때부터 List의 크기가 정해지기 때문에 .add, .removeAt 과 같은 메소드들의 사용이 불가능하다.
이런 Fixed Length List의 경우에 값을 지정하는 방법은 arr3[index] = 값; <- 이런방식으로 값을 지정해 주어야 한다.

다음으로는 List를 생성할때부터 값을 넣은채로 생성하는 방법이 있다.
1. List arr4 = [
값, 값, 값, 값 
];
2. List arr5 = new List.from([
값, 값, 값, 값
]);

## List 심화
1. Looping(순환한다는 뜻)

	List<String> redVelvet = [
	'아이린', '슬기', '웬디', '조이', '예리',
	];
일반적으로 Looping할때는 forEach를 사용한다. 이것은 List의 메소드이다. 
Looping - forEach // forEach에서는 파라미터로 함수를 받는다. 거기다가 그 함수에 파라미터도 받는다. 이 파라미터 값은 어떠한 변수를 설정하여 넣어준다.

redVelvet.forEach((value){
print(value);
});
이렇게 하면 List redVelvet의 요소들이 차레로 출력이된다.  또한 forEach의 특징으로는 forEach로 나온 값들은 따로 return 값을 받지 않았다.
forEach함수 안에서 모든것을 해결하였다. 
forEach메소드를 실행하면 리스트의 각각의 값을 루핑(for문처럼 돌면서) 이 파라미터안에 넣어준 변수인 value안에 각 값을 넣어준다.
그래서 그 값들로 우리가 어떠한 처리를 하면 되는 것이다. ex) print(value);
위의 forEach문과 아래의 for-in 구문은 완전히같은 것이다. 어떤걸 선택하여 쓰는지는 개인적인 취향에 따라 다르다.
for(String value in redVelvet){
print(value);
};

2) Mapping - map (Mapping에서는 일반적으로 map을 사용한다.)
ex)
final newList = redVelvet.map((value){
return '제 이름은 $value입니다.';
});
이 map이라는 것은 위의 forEach와는 다르게 리턴값을 받을 수 있다.
이런식으로 작성하면 redVelvet에 들어있는 각각의 값들을 value로 받아 '제 이름은 $value입니다.'로 값들을 변경해주며 그 값들을 다시 newList의 값들로 넣어주게 됩니다.
여기서 체크할 것은 map을 사용하였을때 newList를 출력해보면 () <- 소괄호 안에 값들이 들어 있는 것을 알수있다. 이 이유는 map의 출력값들은 List의 부모 클래스인 Iterable형태로 출력되기 때문이다. 만약 List형식으로 바꾸고 싶으면 끝에 .toList()를 붙여주면 된다.

3) Reduce / Fold -> 이것은 Reduce란 함수와 Fold란 함수를 실행하는 것이다.
3-1) Fold 
각각의 값들을 루핑(for문과 같은 순환)을 시키면서 그 값들을 이용하여 total을 쌓아가는 역할을 합니다.
ex)
List<int> numbers = [
0, 1, 2, 3, 4, 5, 
];
int toal = numbers.fold(0, (total, element){
return total + element;
});
위에서 total은 numbers라는 리스트의 값들을 더한 값을 저장하기 위해 생성한 변수이다.
fold에는 포지셔널 파라미터가 2개가 들어가는데 처음에 들어가는 것은 처음에 시작하는 값이 들어간다. 
0부터 시작할거면 0, 1부터 시작할거면 1
다음으로 두번째로 어갈 파라미터로는 함수가 들어가는데 해당 함수의 파라미터에도 2개의 값이 들어간다.
여기서 들어가는 2개의 변수는 임의의 변수로 지정해도 상관 없다. 또한 이 안에 들어가는 함수의값도  리턴값을 받는데 
여기서 numbers의 각 값들이 두번째 파라미터 자리에 들어간 함수의 파라미터중 element자리에 들어가게된다 . 그리고
루핑을 할때마다 처음에는 0부터 시작하여 total이라는 값이 안에서 리턴해주는값이 total값이 된다.
그러면 리턴값으로 return total + element; 이렇게 함수의 바디가 정해지게된다 . 그래서 int total 값으로numbers 리스트에 있는 모든 값들을 더한 값이 들어가게 된다. 

여기서 위의 파라미터 안의 total 값은 무조건 첫번째 값이 됨으로 0이 된다. 
(0, (total, element) <- 여기서처음시작하는값이  0이기 떄문에 total은 0으로 시작하게된다 . 
따라서 이 fold는 값을 쌓아갈때 자주 사용이 된다.!! 고 알고있으면 될거 같다.

3-2) reduce
ex)
List<int> numbers = [
0, 1, 2, 3, 4, 5, 
];

int toal2 = numbers.reduce((total, element){
return total + element;
});

reduce에서는 파라미터를 하나 받는데 함수를 받는다. 
reduce도 fold랑 거의 비슷하다. 
reduce는 fold와 다르게 시작하는 값을 적어줄 필요가 없이 파라미터로 함수하나를 받아 실행하고 
가장 처음 시작하는 값이 total값이 된다. 
reduce와 fold가 둘다 필요한 이유는 reduce는 numbers 리스트 안에 들어있는 각각의 값들과 리턴값이 반드시 같아야 하고 fold는 상관이 없다.
fold의 사용예로는
List<String> names = [
'코드팩토리', '레드벨벳', 'BTS'
];

int total3 = names.fold(0, (total, element){
return total + element.length;
});
이렇게 List의 각각의값 들은 String인데 fold함수를 사용하여 int값으로 값을 받아올 수 있다. 
다시 정리하자면 List 내부의값들의 타입과 fold함수를 사용하여 리턴해주려는 값이 다르면 fold를 사용해야하고
같으면 reduce를 사용하면 된다. 

3-3) arrow 함수

int total3 = numbers.reduce((total, element) => total + element); <- 안에서 =>의 값이 리턴이 된다는뜻이다. 
이렇게 작성하는 을 arrow함수라고부른다. 위와같이 성한 것은 결국 reduce함수와 똑같은 기능을 수행한다. 
int toal2 = numbers.reduce((total, element){
return total + element;
});
다시말해 3-3)안에서 위의 함수와 아래의함수가  같다는 뜻이다. 이건 Mapping에서도 똑같다.
만약 
final newList = redVelvet.map((value){
return '제 이름은 $value입니다.';
});
이런 함수가 있다면
final newList = redVelvet.map((value) => '제 이름은 $value입니다.'); 이렇게 적어도 같은 뜻이된다.


List 정리!
Looping에서는 - forEach를사용한다.
Mapping - map이라는메소드를  사용하는데 이것은 forEach와 조금다르게 리턴값을 돌려주는데 새로운 리스트를 만들수 있게해준다 . 

Reduce - reduce 함수를 사용한다. 
Fold = fold함수를사용한다 . 
Reduce와 Fold는 둘다 값을 점점 쌓아갈때 사용한다. 

****






Map
다음으론 Map인데 Map같은 경우는 자바의 HashMap과 아주 비슷하다. HashMap의 key와 Value를 생각하면된다.

  Map dictionary = 
  {
    'Harry Potter' : '해리포터',
    'Ron Weasley' : '론 위즐리',
  };
  Map<String, String> dictionary2 = 
  {
    'Harry Potter' : '해리포터',
    'Ron Weasley' : '론 위즐리',
  };
이렇게 짝을 지어 값을 넣어 준다.
이제 Map타입 변수에 값을 추가하고, 변경하고 삭제하는 방법을 알아보자.

  dictionary.addAll({
    'Hermione Granger' : '헤르미온느',
  });
  dictionary['Hermione Granger'] = '코드팩토리';
  dictionary.remove('Hermione Granger');
위에서부터 차레로 값을 추가하고, 변경하고, 삭제하는 방법이다.

print(dictionary.keys.toList()); // Map타입의 변수인 dictionary의 키의 값들을 리스트 형식으로 출력해준다.
print(dictionary.values.toList());  // Map 타입의 변수인 dictionary의 value 값들을 리스트 형식으로 출력해준다.

final과 const
final은 처음 선언한 값을 다시 바꿀 수 없다.
const도 처음 선언한 값을 다시 바꿀 수 없다.
하지만 final과 const의 dart에서의 차이는 final은 런타임에 값이 지정돼도 상관이 없다. ex) final now = new DateTime.now();
const는 빌드타임에 꼭 값이 지정이 돼있어야 한다. 
const타입일 경우 빌드타입에 값이 선언되어있지 않으면 런타임때 오류가 발생한다! 


enum 
enum타입은 1) 한정된 상수 값 집합을 나타내기 위해 사용한다. 2) 직관적인 코드 작성에 용이하다.
ex) 
enum Color{
red, black, yellow
}
열거형의 변수를 설정할 때 명칭의 첫 문자를 대문자로 쓰는 게 관례이다.
앞에 enum 키워드를 붙이고 중괄호 블록에 필드로 상수값들을 나열한다. 

상수 목록은 List와 마찬가지로 인덱스로 관리할 수 있다.
상수 목록 전체 값을 읽을 때는 .values를 사용한다.

enum Status 
{
  approved,
  rejected,
  pending, // 대기중
}
void main()
{
  Status status = Status.rejected;
  switch(status)
  {
    case Status.approved:
      print('승인 상태 입니다.');
      break;
    case Status.rejected:
      print('거절 상태 입니다.');
      break;
    case Status.pending:
      print('대기 상태 입니다.');
      break;
    default:
      print('어디에도 해당되지 않습니다.');
      break;
  }
}

함수

함수의 기본형식
리턴값 함수명 (매개변수(파라미터)){
return a * x + b;
}
ex)

double linearExp(double a, double b, double x){
  return a * x + b;

옵셔널 파라미터
ex)
double linearExp(double a, double x, [double b = 2]){
  return a * x + b;
}
위의 예시에서 [double b = 2] 를 옵셔널 파라미터라고한다. 
double res = linearExp(1, 2); 
옵셔널이란 말그대로 옵션으로 인수로 값을 넣었을때 옵셔널 파라미터까지
인수를 넣어준다면 그대로 파라미터의 값으로 계산이 되지만
옵셔널 파라미터 자리에 인수를 넣지 않는다면 위의 예시에서 
지정한 default 값인 2로 인식하여 계산하게 된다. 


기본 파라미터란 포지셔널 파라미터라고 불리며 위의 예시처럼
[double b = 2] 이런것을 옵셔널 파라미터, 다음으로 네임드 파라미터가 있다.
ex)
double linearExp(double a, double x, {double b}){
  return a * x + b;
}
위와 같이 사용한 것이 네임드 파라미터(dart의 특이성)이고 
main메소드에서 사용하려면 
double res = linearExp(1, 2, b : 3); 이런식으로 
값을 넣어주게 됩니다.

typedef를 사용하면 함수를 미리 시그니처와 해서 여러가지 함수를 유용하게 다룰 수 있는
기능을 제공해준다.
typedef를 사용할때 주의할 점은 typedef에 정의해둔 것과 사용하려는 함수의 파라미터가 같아야 한다는 것이다.! 
typedef Operation(int x, int y);이렇게 지정하였을때 Operation oper에 들어갈 수 있는 함수명들의 조건으로는 반드시 
typedef Operation에서 지정한것과 같이 2개의 파라미터를 가져야 한다는 것이다. 

-------------------------------------------------------------------------------------------------------------------------
2022/01/02(일)

Class

기본적인 형태
void main(){
  Idol redVelvet = new Idol();
  redVelvet.sayName();
}
class Idol{
  String name = '레드벨벳';
  void sayName()
  {
    print('저는 ${this.name}입니다.');
  }
}

생성자
생성자 기본 구조(다른 언어와 약간 다름)

class Idol{
  final name;
  Idol(
    String name
  ) : this.name = name;
  void sayName(){
    print('저는 ${this.name}입니다.');
  }
}  

이런식으로 변수 설정과 메소드 생성은 비슷하지만
생성자를 만들때 
  Idol(
    String name
  ) : this.name = name;
이렇게 생성자를 만들어야 한다.

생성자 오버로딩
2가지 방법이 있는데 
1. 기존 생성자에서 매개변수 내용의 값을 추가하는법

Idol(String name, String group, int id)
      : this.name = name,
        this.group = group,
        this._id = id;

 Idol redVelvet = new Idol('슬기', '레드벨벳');
  redVelvet.sayName();
그러면 이런식으로 작성하면 되고 
2. 기존 생성자와 다르게 생성자명이자 클래스 명에 .fromMap(Map values)
를 사용하여 생성단계의 매개변수에서 값을 넣고 지정해주는 방법이다.

  Idol.fromMap(Map values)
      : this.name = values['name'],
        this.group = values['group'],
        this._id = values['id'];

 Idol seulgi2 = new Idol.fromMap({'name': '슬기', 'group': '레드벨벳', 'id': '3'});
물론 생성자는 클래스 안에 존재한다.

class Idol {
  final name;
  final group;
  final _id;
  Idol(String name, String group, int id)
      : this.name = name,
        this.group = group,
        this._id = id;
  Idol.fromMap(Map values)
      : this.name = values['name'],
        this.group = values['group'],
        this._id = values['id'];
  void sayName() {
    print('저는 ${this.name}입니다.');
  }
}

private 변수
final _id; <- 이렇게 변수의 시작이 _로 시작되는 변수가 private 변수라고한다.
private변수는 원래는 가져올 수 없어야 한다. 하지만 연습할때 private변수를 가져올 수 있는 이유는 이것이 한 페이지에 같이 있기 때문이다. 만약 private변수가 다른 페이지에 있다면 이렇게 불러올 수가 없다. 

dart에서 priavte 변수 또는 메소드는 클래스단위로 감춰지는 것이 아니라 페이지 단위로 감춰진다는 것을 알아야 합니다.

Getter와 Setter
get id{
return this._id;
}

set id(int id){
this._id = id;
}

상속
class BoyGroup extends Idol {
  BoyGroup(String name, String group, int _id) : super(name, group, _id);
  void sayMale() {
    print('저는 남자 아이돌입니다.');
  }
}
class GirlGroup extends Idol {
  GirlGroup(String name, String group, int _id) : super(name, group, _id);
  void sayFemale() {
    print('저는 여자 아이돌입니다.');
  }
상속을 할때 Idol 클래스를 상속받은 BoyGroup과 GirlGroup은 생성자를 반드시 생성하여야 하며 부모 클래스인 Idol의 생성자를 super(name, group, _id) 받아와야한다.

오버라이딩

class Parent {
  final int number;
  Parent(int number) : this.number = number; // 생성자를 뜻한다.
  int calculate() {
    return this.number * this.number;
  }
}
class Child extends Parent {
  Child(int number) : super(number);
  @override
  int calculate() {
    int result = super.calculate();
    return result + result;
  }
}
오버라이딩은 자바와 똑같은 개념이다. 상속받을때 생성자가 다르니 생성자를 한번 더 확인하자! 
* 오버라이딩을 해도 super.calculate() // 이런식으로 부모의 메소드를 사용할 수 있다.

Static 키워드
static 으로 정의한 변수는 클래스에 바로 귀속이 되며 
static 변수 값을 사용할 때는 클래스명에 .을 붙여 바로 사용할 수 있다. 

interface
dart에서 interface는 좀 특이한 점이 있다. 다른 언어들처럼 키워드가 따로 있는 것이 아니라 클래스를 그대로 인터페이스로 사용할 수 있다.

void main() {
  BoyGroup bts = new BoyGroup('BTS');
  bts.sayName();
  GirlGroup redVelvet = new GirlGroup('레드벨벳');
  redVelvet.sayName();
}
class IdolInterface {
  void sayName() {}
}
class BoyGroup implements IdolInterface {
  String name;
  BoyGroup(String name) : this.name = name;
  void sayName() {
    print('제 이름은 ${name}입니다.');
  }
}

cascadeoperate
밑의 코드에서 보면 위의 코드에서는 3줄로 작성해야 하지만
cascadeoperate를 사용하면 아래와 같이 한줄로 작성할 수 있다.
  BoyGroup bts = new BoyGroup('BTS');
  bts.sayName();
  bts.sayGroup();

  new BoyGroup('BTS')
    ..sayName()
    ..sayGroup();

List의 getter들

  print(redVelvet.first);  // 첫번째껄 나타내는 것
  print(redVelvet.isEmpty);  // 비어있는지 확인하는거
  print(redVelvet.isNotEmpty);  // 안비어있는지 확인하는 것
  print(redVelvet.length);  // 길이 나타내는 것
  print(redVelvet.last); // 마지막껄 나타내는 것
  print(redVelvet.reversed);  // 값을 반대로 나타내는 것
  redVelvet.add('코드팩토리');  // ()안의 값을 리스트에 추가하는 것
  redVelvet.addAll(['코팩1', '코팩2']);  // ()안에 추가로 []안에 적어 추가하는 방법

List 탐색하는 법

void main() {
  List membersList = [
    {
      'id' : 0,
      'name' : '슬기'
    },
    {
      'id' : 1,
      'name' : '아이린'
    },
    {
      'id' : 2,
      'name' : '조이',
    }
  ];
  var item = membersList.firstWhere((item) => item['id'] == 1);
  print(item);
}
이건 첫번째로 조건에 해당되는 리스트를 탐색하는 방법이다.
여기서 중요한건 리스트 변수명인 membersList. 뒤의 내용이다.
1) firstWhere <- 이 뜻은 첫번째로 조건에 해당되는 리스트의 값을 가져온다는 뜻이다.
2) var index = membersList.indexWhere((item) => item['id'] == 1);
이건 위와 마찬가지로 indexWhere이므로 조건에 해당되는 인덱스를 찾는 것이다.
위와 같이 indexWhere를 사용하여 찾을 수 있다.
3) var index2 = [10, 20, 30].indexOf(20);
indexOf를 배울건데 이것은 값이 똑같아야 한다. indexOf()의 괄호안에 넣은 값과
리스트에 있는 값이 똑같은 인덱스를 찾는 것이다.
4) var contains = [10, 20, 30].contains(30);
이건 contains이다. 해당 리스트에 ()안의 값이 포함되어있으면 true 없으면 false이다.

List의 forEach, map

void main() {
  List membersList = [
    {'id' : 0,
    'group' : '레드벨벳',
    'name' : '아이린'
    },
    {
      'id' : 1,
      'group' : 'BTS',
      'name' : 'RM'
    },
    {
      'id' : 2,
      'group' : '레드벨벳',
      'name' : '슬기'
    }
  ];
  membersList.forEach((i){print(i);});
}
forEach는 다음과 같이 사용한다. 

var newList = membersList.map((item){
    return item['name'];
  });
  print(newList);
map은 다음과 같이 사용한다. 위와같이 하면 membersList에서 name의 값들로만
이루어진 리스트가 새로 만들어진다.

 dart Operators
int number = 4;
number /= 2; <- 이렇게 하면 오류가 발생한다. dart에서는 기본적으로 설정이 되어있는데 /=을 하였을때 2를 double 형식의 타입으로 인식하게 된다. 따라서 int인 number를 double로 나누려하니 오류가 발생하게 된다.

- 타입을 비교하는 방법
ex)
int number1 = 1;
print(number is int);
결과값 : true
타입을 비교하고 싶을땐 is를 써서 참 거짓을 확인할 수 있다.
~이 아니다 같은 경우에는
print(number is! int); <- 이렇게 is! 을 써서 아니다란 의미로 사용할 수 있다.

enum 타입의 장점
직관적으로 어떠한 요소들이 있는지 쉽게 파악할 수 있다.
따로 멘션을 넣지 않더라도 알 수 있다. 열거형을 사용하지 않았을때는
철자 오류 같은 부분도 쉽게 알 수 없다.

마지막으로 모든 요소(옵션)들을 보고 싶을때는 열거형변수에
.values를 사용하여 확인할 수 있다.

getter와 setter 추가!
getter와 setter를 사용할때 함수처럼 .name() 이렇게 붙이는 것이 아니라
.name 이렇게만 사용해 준다.

List를 선언하는 방법은 2가지이다.
List arr = [];
List arr = new List();

List arr = new List(3); // 3개의 데이터를 가지는 List로 선언한다.
List<String> // <>안에는 type을 지정 가능

split() 메소드
ex) var Str = 'Hello world!';
str.split(" "); 
출력 값 : ['Hello', 'world!']; 이렇게 배열의 형태로 쪼개준다. 
위의 내용을 바탕으로 
String data 에서 공백을 포함한 값 여러개를 받은 다음 그걸 split()메소드를 이용하여 List arr에 넣어준다. 그러면 arr은 공백을 기준으로 입력한 만큼의 배열이 된다.
그렇게 만들어진 arr 배열을 다시 int값만 받는 arrInt 변수에 map(int.parse).toList();를 이용하여 넣어준다. map()함수는 반복되는 값을 다른 형태로 변환시켜 줍니다.
	String data = stdin.readLineSync();
	List<String> arr = data.split(' ');
	List<int> arrInt = arr.map(int.parse).toList();

Map() 심화!

Map map = {
'Apple' : '사과',
'Banana' : '바나나',
'Kiwi' : '키위',
};
map.keys.toList() <- 이렇게 하면 이거 자체가 다시 리스트가 되기떄문에
리스트에 사용가능한 모든 함수들을 사용할 수 있다.

String에 대한 크기(길이)를 구할 수 있다.
ex) 
int a = 33;
String myNum = a.toString();
print(myNum.length); 
결과 값 : 2
ex2)
String h = 'harang';
print(h.length);
결과 값 : 6
 
문법이 쉽다고 생각했는데 세부적으로 아직 숙달이 덜 됐다는 것을 느꼇고 내일 왕초보 유투브를 다시 정독하여 확실히 익히고 문제를 풀어보려한다. 

		     
# 1/4

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

