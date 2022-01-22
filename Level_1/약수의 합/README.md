# 약수의 합

## 문제 설명
정수 n을 입력받아 n의 약수를 모두 더한 값을 리턴하는 함수, solution을 완성해주세요.  

<br/>

## 제한 조건
- `n`은 0 이상 3000이하인 정수입니다.

<br/>

## 입출력 예
| n | return |
|------|---|
|12|28|
|5|6|

<br/>

## Solution

```swift
func solution(_ n:Int) -> Int {
    
    var result: Int = 0
    
    if n == 0 { return 0 }
    
    for i in 1...n {
        if n % i == 0 { result += i }
    }
    
    return result
}
```

```swift
func solution(_ n:Int) -> Int {   
    guard n != 0 else {
        return 0
    }
    return Array(1...n).filter{n % $0 == 0}.reduce(0, +)
}
```
