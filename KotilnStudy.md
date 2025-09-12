
# Kotlin 공부

## 변수 선언

```kotlin
var i : int = 1
var name : String = "김철수"
var point : float= 4.4
```
<span style="color: #FF4C4C;">var</span> 이라는 키워드는 변경이 가능한 변수를 생성할때 사용한다.
그리고 뒤에 타입을 지정할 때에는 : (자료형) 과 같이 표현한다.

```kotlin
val j = 10
val name2 = "정종윤"
val pickmeup = 4.1
```
<span style="color: #FF4C4C;">val</span> 이라는 키워드는 변경이 불가능한 불변 변수를 생성할때 사용한다.
이것은 Java 에서 final 과 같은 역할입니다.

## NULL을 다루는 방법
```kotlin
var name: String = "정종윤" // NULL을 허용하지 않음
var name2 : String? = NULL // NULL을 허용함
```
Kotlin 에서는 NULL을 다룰 때 자료형 뒤에 <span style="color: #FF4C4C;">?</span>만 붙이면 NULL 을 허용을 합니다.

## Safe call Operator
```kotlin
fun main(){
 BookRepository.findBook(1L)
 ?.updateTitle("new title")
 }
```
<span style="color:green">Safe call Operator(.?)</span> 를 쓰면 이 메서드나 객체에 접근 할 때 만약에 NULL 이라면 넘기는 연산자 입니다.
```java
public static void main(String[] args){
BookRepository.findBook(id :1L)
	.ifPresent(book -> book.updateTitle("new title")
```
Java는 Kotlin에 비해서 NULL을 따로 체크를 해줘야하는 성향이 있습니다. 하지만 Kotlin에서는 .? 하나로 NULL Check를 할수있습니다


## Elvis Operator (?:)
<span style ="color:green"> Elvis Operator (?:)</span>를 쓰면 만약이 값이 NULL 이라면 ?: 오른쪽에 있는 값을 넘겨줍니다.

```kotlin
val name: String? = null
val displayName = name ?: "Unknown"
println(displayName)  // 출력: Unknown
```

```java
Optional<String> name = Optional.ofNullable(null);
String displayName = name.orElse("Unknown");
System.out.println(displayName); // 출력: Unknown
```
Java에서는 Optional 이라는 것을 객체를 생성해 NULL Check를 합니다. **name.orElse("Unknown");** 을 보면 만약에 NULL이라면 "Unknown" 이라는 값을 반환해줍니다. 
