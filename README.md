#### List.map() 메소드에 대한 설명
- arr.map(parameter) map 메서드는 함수를 parameter로 받고, parameter에 들어가는 함수의 파라미터에 배열 메서드(map)에서 제공하는 파라미터를 자동으로 넣어준다. 
- 그래서 int.parse(val)라고 명시적으로 적어주지 않아도 되는 것이다.

#### 올림, 버림, 반올림
1. 올림
- 소수점 이하를 올리기 위해서는 ceil이라는 함수를 사용한다.
		double targetNum = 3.514;
		print(targetNum.ceil());
		// 4
2. 버림
- 소수점 이하를 버리기 위해서는 floor라는 함수를 사용한다.
		double targetNum = 3.514;
		print(targetNum.floor());
		// 3
3. 반올림
- 소수점 이하를 반올림하기 위해서는 round라는 함수를 사용한다.
		double targetNum = 3.514;
		print(targetNum.round());
		// 4
		targetNum = 3.154;
		print(targetNum.round());
		// 3
4. 소수점 길이 고정 (고정 이하 반올림)
- 소수점 길이를 고정하기 위해서는 toStringAsFixed라는 함수를 사용한다. 
		var targetNum = 3.125;
		print(targetNum.toStringAsFixed(2));
		// 3.13
		targetNum = 3.121;
		print(targetNum.toStringAsFixed(2));
		// 3.12
=> 여기서 중요한 것은 toStringAsFixed함수를 사용하면 문자열로 반환하기 때문에 숫자로 사용하기 위해서는 double타입으로 형변환을 해야한다. 
double.parse(targetNum.toStringAsFixed(숫자));
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
## List - 메서드
### 1. Looping(순환한다는 뜻) - forEach
		List<String> redVelvet = [
		'아이린', '슬기', '웬디', '조이', '예리',
		];
		redVelvet.forEach((value){
			print(value);
		});
Looping - forEach // forEach에서는 파라미터로 함수를 받는다. 해당 함수에 파라미터도 받는다. 이 파라미터값은 어떠한 변수를 설정하여 넣어준다.
위의 코드에서는 value를 변수로 지정하여 파라미터에 넣었다. 위의 코드를 실행하면 List redVelvet의 요소들이 차례로 출력이된다.
위의 forEach문과 아래의 for-in 구문은 완전히같은 것이다. 어떤걸 선택하여 쓰는지는 개인적인 취향에 따라 다르다.
	for(String value in redVelvet){
		print(value);
	};
### 2. Mapping - map 
		final newList = redVelvet.map((value){
			return '제 이름은 $value입니다.';
		});
map 함수의 특징
* map함수는 해당 리스트를 새로운 값이나 새로운 형태로 바꾸고 싶을 때 사용한다.
	- 배열의 값들을 변경해 새로운 배열을 리턴한다.
	- 배열의 값을 바꾸는거는 파라미터로 넣는 함수의 내용대로 변경한다. 
* map함수의 파라미터로 함수를 넣고 그 함수 안에 리턴값이 있다. => 기존배열의 배열값을 이용해 함수를 적용한 새 배열값으로 변경이 가능하다.
* Iterable(List의 부모 클래스) 형태로 리턴된다, List형식으로 바꾸고 싶으면 리턴값에 .toList()를 붙여주면된다.
이런식으로 작성하면 redVelvet에 들어있는 각각의 값들을 value로 받아 '제 이름은 $value입니다.'로 값들을 변경해주며 그 값들을 다시 newList의 값들로 넣어주게 됩니다.
### 3. fold
		List<String> names = [
		'코드팩토리', '레드벨벳', 'BTS'
		];
		int total3 = names.fold(0, (total, element){
			return total + element.length;
		});
fold 함수의 특징
- 각각의 요소들의 총합을 루핑으로 순환하며 쌓아가는 함수이다.
- 시작값을 파라미터로 정해준다.
- numbers 리스트 요소의 값과 fold함수를 사용하여 리턴한 값의 형태가 달라도 상관없다.
fold에는 포지셔널 파라미터가 2개가 있으며 처음에 들어가는 파라미터는 처음 시작하는 값이 들어간다. ex) 0부터 시작할거면 0, 1부터 시작할거면 1
두번째로 들어갈 파라미터로는 함수가 들어가는데 해당 함수에도 2개의 파라미터가 있다.
여기서 numbers의 각 값들이 두번째 파라미터 자리에 들어간 함수의 파라미터중 element자리에 들어가게된다 . 
루핑을 할때마다 처음에는 0부터 시작하며 리턴한 값이 다음 루핑의 total값이 된다.
계속 루핑을 하고나면 int total 값으로 numbers 리스트에 있는 모든 값들을 더한 값이 들어가게 된다. 
여기서 위의 파라미터 안의 total 값은 무조건 첫번째 값이 됨으로 0이 된다. 
(0, (total, element) <- 여기서처음시작하는값이  0이기 떄문에 total은 0으로 시작하게된다 . 
fold는 값을 쌓아서 누적된 값을 알고 싶을때 사용한다.
### 4. reduce
		List<int> numbers = [
			0, 1, 2, 3, 4, 5, 
		];
		int toal2 = numbers.reduce((total, element){
			return total + element;
		});
reduce 함수의 특징
- numbers 리스트 요소의 값과 reduce함수를 사용하여 리턴한 값의 형태가 반드시 같아야 한다. ex) numbers요소가 int형이면 반드시 리턴값이 int형이어야 한다.
reduce에서는 파라미터를 하나 받는데 함수를 받는다. 
reduce는 fold와 다르게 시작하는 값을 적어줄 필요가 없고 파라미터로 함수를 하나 받아 실행하며 가장 처음 시작하는 값이 total값이 된다.
return total + element가 첫번째로 실행될때 total에는 첫번째 값이 들어가고 element에는 두번째 값부터 들어가기 시작한다!!
### 5. arrow
		int total3 = numbers.reduce((total, element) => total + element); 
		
			// 위와 아래의 코드가 같은 코드이다.
			
		int toal2 = numbers.reduce((total, element){
			return total + element;
		});
		--------------------------------------------------------------
		final newList = redVelvet.map((value) => '제 이름은 $value입니다.'); 
		
			// 위와 아래의 코드가 같은 코드이다.
			
		final newList = redVelvet.map((value){
			return '제 이름은 $value입니다.';
		});
arrow 함수의 특징
- 단, 함수내부의 내용이 한줄일 때만 사용이 가능하다. 두 줄이 넘어가면 arrow함수로 작성할 수 없다.
****
# Map
#### 정의 : map과 array는 자료구조이다. Map을 보통 Key Value Pair라고 부른다. 사전과 같다고 보면된다.
map의 선언방법 : 크게 형태는 2가지이고 값을 넣지 않았을 경우와 넣었을 경우로 나누어보았다.
1) Map dictionary = {}; 
2) Map dictionary2 = {
	Key값 : Value값, Key값 : Value값, Key값 : Value값, Key값 : Value값...
};
3) Map dictionary3 = new Map(); 
4) Map dictionary4 = new Map.from({
	Key값 : Value값, Key값 : Value값, Key값 : Value값, Key값 : Value값...
});
Map에서 값 추가방법 : 
dictionary.addAll({
	Key값 : Value값, Key값 : Value값, Key값 : Value값, Key값 : Value값...
});
Map에서 값 지우는 방법 : dictionary.remove(key값);
Map에서 값 변경하는 방법 : dictionary[key값] = value값;
key값만 가져오는 방법 : dictionary.keys;
value값만 가져오는 방법 : dictionary.values;
하지만 이렇게만 값을 가져온다면 리턴값은 Iterable형태를 취하게 됨으로 List형태로 리턴하고 싶다면 dictionary.keys.toList() or dictionary.values.toList() 로 작성을 해주어야한다.
- Map에서의 key값은 유니크해야한다. 이 말은 만약 key의 값에 또다른 value를 넣어주면 이전에 있던 해당 key에 대한 value값에 새로 넣어준 value값이 덮어 씌워진다. 
List와 다르게 같은 값을 중복하여 넣을수 없다는 뜻이다. Map에서 Key는 딱 하나만 존재할 수 있다. 같은 값 존재 불가능!
## Map - map이랑 List랑 연계되는것이  많아 알아놔야할게 있다.
	Map<String, String> map = {
		'Apple' : '사과',
		'Banana' : '바나나',
		'Kiwi' : '키위',
	};
map.values.toList() -> 이렇게 List로 map의 값들을변경해 주고나면 위의 List심화에서 배웠던 여러 메소드들을 사용할 수 있게 된다. 
map에서도 mapping을 할 수 있다. entries를 사용하면되는데 아래와 같이 사용하면 map을 사용할 수 있다.
	final newMap = map.entries.map((entry){
		final key = entry.key;
		final value = entry.value;
		return '$key는 한글로 $value입니다.';
	});
mapping이니까 리턴을해줘야하는데 위와같이 사용하면 map에 들어있는 값들이
Apple는 한글로 사과 입니다., Banana는 한글로 바나나입니다., Kiwi는 한글로 키위 입니다.) 이런식으로 바뀌는것을알 수있다. 
이렇게 해서 List심화에서배웠던 forEach, map, reduce, fold와 같은 메소드들을 다 사용할 수 있다. 
map 변수.entries. forEach / map / reduce / fold 이렇게 사용이  가능하다.
### asMap()
	List<int> numbers = [
		0, 1, 2, 3, 4, 
	];
	final newMap2 = numbers.map((item){
		return '값이 $item 입니다.';
	});
asMap함수를 어떨때 사용하냐면 위와같이 mapping을 사용하여 numbers 리스트안의 값들을변경해 주는데 그 값들의 인덱스와 value값을 통째로 받고 싶을때 사용한다. 
	final newMap3 = numbers.asMap(); 
위와같이 numbers의 값들을 map으로 바꿀수가 있는데 이렇게 설정을 해주면 print(newMap3)를 했을 때 
{0: 0, 1: 1, 2: 2, 3: 3, 4: 4} 이런식으로 출력이된다. 이 뜻이 무엇이냐하면 List인 numbers의 값들 앞에 인덱스 번호가 key값으로 들어간것이다 .
	final newMap3 = numbers.asMap().entries.map((entry){
		final index = entry.key;
		final value = entry.value;
		return 'index가 $index 일때 값은 $value 입니다.';
	});
그런다음 위와같이 작성해주면 index가 0일때 값은 0입니다. 이런식으로 mapping을 사용할수가 있게된다.
****
# 나머지 메서드 문법 정리
## switch
개념 : Switch문은 크고 작다를 표현할 수 없고 오직 동등조건만 검사할 수 있다.
## Operators(연산자)
	int number1 = 10;
	number1 = 9;
	number1 ?? = 4; // 이 뜻은 만약 number1이 null값이면 4를 넣어라는 뜻이다. 만약 null값이 아니라면 이 코드는 아무것도 실행시키지 않는다.
	print(number1 is int); => true;
	print(number1 is String); => false;
	print(number1 is bool); => false;
	print(number1 is! String) => true;
이렇게 is를 사용할떄는 is! <- is not이렇게 부호를 적어줘야한다.
## switch && if
두가지 문법의 차이 : 만약 조건이 한가지이고 그에 해당하는 값이 여러개인 경우 - switch문을 사용하는게 효율적이고 좋다.
하지만 여러가지 조건을 사용하게 되면 if문을 사용하는게 좋다.
## final && const
개념 정리 : 
1) final과 const는 둘다 처음 선언한 값을 다시 바꿀 수 없다.
2) final과 const의 dart에서의 차이는 final은 런타임에 값이 지정돼도 상관이 없다. ex) final now = new DateTime.now();
하지만 const는 빌드타임에 꼭 값이 지정이 돼있어야 한다. const타입일 경우 빌드타입에 값이 선언되어있지 않으면 런타임때 오류가 발생한다.
## enum 
	enum Color{
		red, black, yellow
	}
개념 정리 : 
1) 한정된 상수 값 집합을 나타내기 위해 사용한다.
2) 직관적인 코드 작성에 용이하다.
3) 오타를 예방할 수 있다.
열거형의 변수를 설정할 때 명칭의 첫 문자를 대문자로 쓰는 게 관례이다.
앞에 enum 키워드를 붙이고 필드로 상수값들을 나열한다. 
상수 목록은 List와 마찬가지로 인덱스로 관리할 수 있다.
상수 목록 전체 값을 읽을 때는 .values를 사용한다.
	enum Status 
	{
	  approved,
	  rejected,
	  pending, 
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
## 파라미터
1) 포지셔널 파라미터(기본 파라미터를 뜻하며 위치에 따라 구별한다)
2) 옵셔널 파라미터([double b = 2])
3) 네임드 파라미터({double b} -> 값을 지정할때 b : 3 이런식으로 작성하며 네임드 파라미터들은 순서가 중요하지않다.)
## typedef
개념 정리 : 
1) 함수를 미리 시그니처와 해서 여러가지 함수를 유용하게 다룰 수 있는 기능을 제공해준다.
2) typedef에 정의해둔 것과 사용하려는 함수의 파라미터가 같아야 한다.
3) typedef Operation(int x, int y);이렇게 지정하였을때 파라미터로(Operation oper)에 들어갈 수 있는 함수명들의 조건으로는 반드시 
   typedef Operation에서 지정한것과 같은 자료형을 가진 2개의 파라미터를 가져야 한다는 것이다. 
## 생성자
	  Idol(
	    String name
	  ) : this.name = name;
기본형태이다. 자바와 다르니 기억하기!
### 생성자 오버로딩
2가지 방법이 있다.
1. 기존 생성자에서 매개변수 내용의 값을 추가하는 법
		Idol(
			String name,
			String group,
			int id
			) : this.name = name,
			    this.group = group,
			    this._id = id;
2. '네임드 생성자'로 불린다. 생성자뒤에 자기가 이름을 붙일수가 있다.
아래의 예시에서는 .fromMap이란 이름을 지었는데 이 이유는 파라미터로 Map을 받아 생성자를 만드려하기 때문이다.
해당 Map에 입력되어 있는 값을 기준으로 name, group, id값이 정해지게 된다.
	Idol seulgi2 = new Idol.fromMap({'name': '슬기', 'group': '레드벨벳', 'id': '3'});  //아래의 네임드 생성자로 만든 인스턴스이다.
	  Idol.fromMap(Map values)
	      : this.name = values['name'],
		this.group = values['group'],
		this._id = values['id'];
## private 변수
개념 정리 : 
1) final _id; <- 이렇게 변수의 시작이 _로 시작되는 변수가 private 변수라고한다.
2) dart언어에서는 private변수가 클래스별로 구별되는 것이 아닌 페이지 별로 구별된다. 따라서 한 페이지에 private변수가 있으면 해당 페이지에서는 자유롭게 변경이 가능하다.
## Getter && Setter
개념 정리 : (최근에 변경점이 있어 다시 정리해보자!)
	int get id{
		return this._id;
	}
	set id(int id){
		this._id = id;
	}
## 상속
개념 정리 : 
상속을 할때 Idol 클래스를 상속받은 BoyGroup과 GirlGroup은 생성자를 반드시 생성하여야 하며 부모 클래스인 Idol의 생성자를 super(name, group, _id) 받아와야한다.
	class BoyGroup extends Idol {
	  BoyGroup(String name, String group, int _id) : super(name, group, _id);
	  
	  void sayMale() {
	    print('저는 남자 아이돌입니다.');
	  }
	}
## 오버라이딩
주요 개념 : 
- 오버라이딩은 자바와 똑같은 개념이다. 오버라이딩을 해도 super.calculate() // 이런식으로 부모의 메소드를 사용할 수 있다.
		class Parent {
		  final int number;
		  Parent(int number) : this.number = number; 
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
## Static
개념 정리 : 
1) static 으로 정의한 변수는 클래스에 바로 귀속이 되며 static 변수 값을 사용할 때는 클래스명에 .을 붙여 바로 사용할 수 있다. 
2) static은 함수나 변수에 설정가능하다.
3) static 키워드를 사용하여 모든 해당 클래스의 인스턴스들에 영향을 미칠수 있다.
## interface
개념 정리 : 
1) dart에서 interface는 좀 특이한 점이 있다. 다른 언어들처럼 키워드가 따로 있는 것이 아니라 클래스를 그대로 인터페이스로 사용할 수 있다.
2) interface는 설계를 하는 것이다. interface에서 설계한 변수나 메소드는 반드시 구현하여야한다. 
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
## cascade operate
	  BoyGroup bts = new BoyGroup('BTS');
	  bts.sayName();
	  bts.sayGroup();
		//위의 코드와 아래의 코드가 같다. 아래의 코드를 cascade operate라고 부르며 좀더 간단히 작성할 수 있다.
	  new BoyGroup('BTS')
	    ..sayName()
	    ..sayGroup();
## List의 getter
	  print(redVelvet.first);  // 리스트의 첫번째 요소를 나타내는 것
	  print(redVelvet.isEmpty);  // 비어있는지 확인하는거
	  print(redVelvet.isNotEmpty);  // 안비어있는지 확인하는 것
	  print(redVelvet.length);  // 길이를 나타내는 것
	  print(redVelvet.last); // 리스트의 마지막 요소를 나타내는 것
	  print(redVelvet.reversed);  // 값을 반대로 나타내는 것
	  redVelvet.add('코드팩토리');  // ()안의 값을 리스트에 추가하는 것
	  redVelvet.addAll(['코팩1', '코팩2']);  // ()안에 추가로 []를 적어주고 그 안에 적어 여러요소를 한번에 추가하는 방법
## List를 탐색하는 법
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
1) firstWhere 
.firstWhere 메서드는 첫번째로 저건에 해당되는 리스트의 요소를 탐색하는 방법이다.
2) indexWhere
.indexWhere((item) => item['id'] == 1); -> 이건 .indexWhere이므로 조건에 해당되는 인덱스를 찾는 것이다.
3) indexOf
.indexOf()이다. 이것은 ()안의 값과 리스트의 요소의 값이 같은 인덱스를 찾는 것이다.
4) contains
.contains()이다. 이는 해당 리스트에 ()안의 값이 포함되어있으면 true 없으면 false를 반환한다.
## split() 
	var Str = 'Hello world!';
	str.split(" "); 
		=> ['Hello', 'world!'];  // split()메서드를 사용하여 배열의 형태로 쪼개준다.
## join()
	 List<String> fruit = [
	    '사과', '바나나', '딸기'
	  ];
	  String arr = fruit.join(', ');  // join()메서드를 사용하여 List 요소들의 값을 String으로 만들어 준다.
	  print(arr);
	
