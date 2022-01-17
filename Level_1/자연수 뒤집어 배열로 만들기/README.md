# 자연수 뒤집어 배열로 만들기

## 문제 설명 
자연수 n을 뒤집어 각 자리 숫자를 원소로 가지는 배열 형태로 리턴해주세요. 예를들어 n이 12345이면 [5,4,3,2,1]을 리턴합니다.

<br/>
## 제한 조건
- n은 10,000,000,000이하인 자연수입니다.

<br/>
## 입출력 예
| n | return |
|------|---|---|
|12345|[5,4,3,2,1]|



<br/>
## Solution

```swift
func solution(_ n:Int64) -> [Int] {
    return String(n).map { Int(String($0))! }.reversed()
}
```

```swift
func solution(_ n:Int64) -> [Int] {
    let arr = String(n).compactMap { Int(String($0)) }
    return arr.reversed()
}
```

<br/>
## Check
- n을 String으로 변형한 다음 각각의 문자를 String으로 바꿔주고 Int로 바꿔 map으로 배열에 담아준 다음 reversed() 메소드를 이용해 거꾸로 정렬해준다.