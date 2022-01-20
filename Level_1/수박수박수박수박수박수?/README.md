# 수박수박수박수박수박수?

## 문제 설명 
길이가 n이고, "수박수박수박수...."와 같은 패턴을 유지하는 문자열을 리턴하는 함수, solution을 완성하세요. 예를들어 n이 4이면 "수박수박"을 리턴하고 3이라면 "수박수"를 리턴하면 됩니다.

<br/>

## 제한 조건
- n은 길이 10,000이하인 자연수입니다.

<br/>

## 입출력 예
| n | return |
|------|---|
|3|"수박수"|
|4|"수박수박"|


<br/>

## Solution

```swift
func solution(_ n:Int) -> String {
    
    var result: String = ""
    
    for i in 1...n {
        if i % 2 == 1 { result += "수" } 
        if i % 2 == 0 { result += "박" }
    }
    
    return result
}
```

```swift
func solution(_ n:Int) -> String {
    return "\(String(repeating: "수박", count: n / 2))\(n % 2 == 0 ? "" : "수")"
}
```

<br/>

## Check
- if문을 사용하여 수박을 출력
-  String repeating을 이용하여 수박을 출력후 마지막 부분을 홀 짝수를 구분하여 출력