# 정수 내림차순으로 배치하기

## 문제 설명 
함수 solution은 정수 n을 매개변수로 입력받습니다. n의 각 자릿수를 큰것부터 작은 순으로 정렬한 새로운 정수를 리턴해주세요. 예를들어 n이 118372면 873211을 리턴하면 됩니다. 

<br/>
## 제한 조건
- n은 1이상 8000000000 이하인 자연수입니다.

<br/>
## 입출력 예
| n | return |
|------|---|
|[[1,2],[2,3]]|[[3,4],[5,6]]|
|[[1],[2]]|[[3],[4]]|


<br/>
## Solution

```swift
func solution(_ n:Int64) -> Int64 {
    return Int64(String(Array(String(n)).sorted(by: > )))! 
}
```

```swift
func solution(_ n:Int64) -> Int64 {
    return Int64(String(Array(String(n)).sorted { $0 > $1 }))!
}
```

<br/>
## Check
- Int형을 String으로 변환하여 배열화 시켜서 정렬후 다시 스트링으로 변환하여 인트로 변환합니다.