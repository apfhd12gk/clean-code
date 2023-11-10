## 목차

---

> 소프트웨어에서 이름은 어디나 쓰인다. 우리는 변수, 함수, 인수와 클래스 패키지, 소스파일 등 여기저기에 이름을 사용한다.  
 이렇듯 많이 사용하므로 이름을 잘 지으면 여러 모로 편하다.

## 의도를 분명히 밝혀라
- 변수나 함수 클래스 이름은 다음과 같은 굵직한 질문에 모두 답해야 한다.
  - 존재의 이유는?
  - 수행 기능은?
  - 사용방법은?
- 단순히 이름만 고쳤는데도 함수가 하는 일을 이해하기 쉬워진다.

## 그릇된 정보를 피하라
- 실제 컨테이너 유형을 이름에 넣지 않는 편이 바람직하다.
- 서로 흡사한 이름을 사용하지 않도록 주의한다.
- 일관성이 떨어지는 표기법은 그릇된 정보다.

## 의미 있게 구분하라
- 컴파일러나 인터프리터만 통과하려는 생각으로 코드를 짜면 안된다.
- 이름이 달라야 한다면 의미도 달라져야 한다.
  - 연속적인 숫자를 덧붙인 이름은(a1,a2, ... ,aN) 의도적인 이름과 정반대다.
- 읽는 사람이 차이를 알도록 이름을 지어라.

## 발음하기 쉬운 이름을 사용하라

## 검색하기 쉬운 이름을 사용하라
- 문자 하나를 사용하는 이름과 상수는 텍스트 코드에서 쉽게 눈에 띄지 않는다.
- 이름 길이는 범위 크기에 비례해야한다.

## 인코딩을 피하라
- 유형이나 범위정보까지 인코딩에 넣으면 그만큼 이름을 해독하기 어려워진다.
- 멤버 변수에 접두어를 붙일 필요 없다. 멤버 변수를 다른 색상으로 표현해주는 IDE를 사용해야 마땅하다.

## 자신의 기억력을 자랑하지 마라
- 독자가 코드를 읽으면서 변수 이름을 자신이 아는 이름으로 변환해야 하면 그 변수 이름은 바람직하지 못하다.
- 문자 하나만 사용하는 변수 이름은 문제가 있다. (루프에서 반복 횟수를 세는 i,j,k 정도는 쾐찮다)
  
## 클래스 이름
- 클래스 이름과 객체 이름은 명사나 명사구가 적합하다.

## 메서드 이름
- 메서드 이름은 동사나 동사구가 적합햐다.
- 접근자, 변경자, 조건자는 javabean 표준에 따라 값 앞에 get, set, is를 붙인다.
- 생성자를 중복정의 할 때는 정적 팩토리 메소드를 사용하고, 메서드는 인수를 설명하는 이름을 사용한다.

```java
Complex fulcrumPoint = Complex.FromRealNumber(23.0);
// 위 코드가 아래 코드보다 좋다.
Complex fulcrumPoint = new Conplex(23.0);
//생성자 사용을 제한하려면 해당 생성자를 private로 선언한다.
```

## 기발한 이름은 피하라
- 재미난 이름보다 명료한 이름을 선택하라.
- 특정 문화에서면 사용하는 농담은 피하는 편이 좋다.
- 의도를 분명하고 솔직하게 표현하라

## 한 개념에 한 단어를 사용하라
- 추상적인 개념 하나에 단어 하나를 선택해 이를 고수한다.
- 이름이 다르면 독자는 당연히 클래스도 다르고 타입도 다르다고 생각한다.

## 말장난을 하지 마라
- 한 단어를 두 가지 목적으로 사용하지 마라.
- 집중적인 탐구가 필요한 코드가 아니라 대충 훑어봐도 이해할 코드 작성이 목표다
  
> 예를 들어, 지금까지 구현한 add 메서드는 모두가 기존 값 두개를 더하거나 이어서 새로운 값을 만든다고 가정하자.
새로 작성하는 메서드는 집합에 값 하나를 추가한다. 이 메서드를 add라 불러도 괜찮을까? 하지만 새 메소드는 기존 add메소드와 맥락이 다르다
그러므로 insert나 append라는 이름이 적당하다.


## 해법 영역에서 가져온 이름을 사용하라
- 코드를 읽을 사람도 프로그래머라는 사실을 명심한다. 그러므로 전산 용어, 알고리즘 이름, 패턴 이름, 수학 용어 등을 사용해도 괜찮다.
- 모든 이름을 문제 영역에서 가져오는 정책은 현명하지 못하다.
  
## 문제 영역에서 사져온 이름을 사용하라
- 적절한 '프로그래머 용어'가 없다면 문제 영역에서 이름을 가져온다.
- 문제 영역 개념과 깊은 코드라면 문제 영역에서 이름을 가져와야 한다.

## 의미있는 맥락을 추가하라
- 클래스, 함수, namespace등으로 감싸 맥락을 부여하자.
- 그래도 불분명 하다면 접두사를 사용하자.

```java
// Bad
private void printGuessStatistics(char candidate, int count) {
    String number;
    String verb;
    String pluralModifier;
    if (count == 0) {  
        number = "no";  
        verb = "are";  
        pluralModifier = "s";  
    }  else if (count == 1) {
        number = "1";  
        verb = "is";  
        pluralModifier = "";  
    }  else {
        number = Integer.toString(count);  
        verb = "are";  
        pluralModifier = "s";  
    }
    String guessMessage = String.format("There %s %s %s%s", verb, number, candidate, pluralModifier );

    print(guessMessage);
}
```

```java
// Good
public class GuessStatisticsMessage {
    private String number;
    private String verb;
    private String pluralModifier;

    public String make(char candidate, int count) {
        createPluralDependentMessageParts(count);
        return String.format("There %s %s %s%s", verb, number, candidate, pluralModifier );
    }

    private void createPluralDependentMessageParts(int count) {
        if (count == 0) {
            thereAreNoLetters();
        } else if (count == 1) {
            thereIsOneLetter();
        } else {
            thereAreManyLetters(count);
        }
    }

    private void thereAreManyLetters(int count) {
        number = Integer.toString(count);
        verb = "are";
        pluralModifier = "s";
    }

    private void thereIsOneLetter() {
        number = "1";
        verb = "is";
        pluralModifier = "";
    }

    private void thereAreNoLetters() {
        number = "no";
        verb = "are";
        pluralModifier = "s";
    }
}


```

## 불필요한 맥락을 없애라
- '고급 휘발유 충전소' 라는 애플리케이션을 짠다고 모든 클래스 이름을 GSD로 시작하겠다는 생각은 전혀 바람직하지 못하다.

> 여느 코드 개선 노력괴 마찬가지로 이름ㅇ역시 나름대로 바꿧다가는 누군가 질책할지도 모른다. 그렇다고 코드를 개선하려는 노력을 중단해서는 안된다.
