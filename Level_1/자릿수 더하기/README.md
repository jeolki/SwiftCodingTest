# 자릿수 더하기

## 문제 설명 
자연수 N이 주어지면, N의 각 자릿수의 합을 구해서 return 하는 solution 함수를 만들어 주세요.
예를들어 N = 123이면 1 + 2 + 3 = 6을 return 하면 됩니다.

<br/>

## 제한 조건
- N의 범위 : 100,000,000 이하의 자연수

<br/>

## 입출력 예
| N | return |
|------|---|
|123|6|
|987|24|


<br/>

## Solution

```swift
import Foundation

func solution(_ n:Int) -> Int {
    var answer:Int = 0
    
    let array = String(n).map { Int(String($0))! }
    
    for i in array { 
        answer += i
    }
    
    return answer
}
```

```swift
func solution(_ n:Int) -> Int {

    String(n).map { Int(String($0))! }.reduce(0) { $0 + $1 }
    
}
```

<br/>

## Check
- 숫자 배열에선 reduce method를 사용하면 배열요소의 합 또는 곱한 결과를 알아낼 수 있습니다.