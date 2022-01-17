# 핸드폰 번호 가리기

## 문제 설명 
프로그래머스 모바일은 개인정보 보호를 위해 고지서를 보낼 때 고객들의 전화번호의 일부를 가립니다.
전화번호가 문자열 phone_number로 주어졌을 때, 전화번호의 뒷 4자리를 제외한 나머지 숫자를 전부 *으로 가린 문자열을 리턴하는 함수, solution을 완성해주세요.

<br/>
## 제한 조건
- s는 길이 4 이상, 20이하인 문자열입니다.

<br/>
## 입출력 예
| phone_number | return |
|------|---|
|"01033334444"|"*******4444"|
|"027778888"|	"*****8888"|


<br/>
## Solution

```swift
func solution(_ phone_number:String) -> String {
    
    var arr = Array(phone_number).map { String($0) }
    
    for i in 0 ..< (arr.count-4) {
        arr[i] = "*"
    }
    
    return arr.joined(separator: "")
}
```

```swift
func solution(_ phone_number:String) -> String {
    return String("\(String(repeating: "*", count: phone_number.count - 4))\(phone_number.suffix(4))")
}
```

<br/>
## Check
- String to Array  
	map() : 고차함수 map을 사용하여 문자열을 문자 하나하나로 쪼개서 배열로 만드는 방법이다.
	let str = "aBcDeF"

		// Character형을 요소로 갖는 배열
		let charArr = str.map {$0}
		print("\(charArr) : \(type(of: charArr))") // ["a", "B", "c", "D", "e", "F"] : Array<Character>
		
		
		// String형을 요소로 갖는 배열
		let strArr = str.map {String($0)}
		print("\(strArr) : \(type(of: strArr))") // ["a", "B", "c", "D", "e", "F"] : Array<String>
		
- Array to String   
	배열의 joined()나 reduce()를 사용한다.
	
		let array = ["A", "B", "C"]
		let str1 = String(Array)
		let str2 = array.joined(separator: "")
		let str3 = array.reduce("", +)
		
- 접두어, 접미어 확인  
	prefix(_:), suffix(_:)    
맨 앞 또는 뒤에서 몇번째 글자까지 오는 접두어나 접미어를 확인할 수 있다. 반환형은 Substring이다.
		
		let str = "aBcDeF"
		
		// 접두어 (앞에서부터 몇 글자)
		print(str.prefix(3)) // aBc
		print(str.prefix(4)) // aBcD
		
		// 접미어 (뒤에서부터 몇 글자)
		print(str.suffix(1)) // F
		print(str.suffix(2)) // eF