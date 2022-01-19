# 평균 구하기

## 문제 설명 
정수를 담고 있는 배열 arr의 평균값을 return하는 함수, solution을 완성해보세요.

<br/>

## 제한 조건
- arr은 길이 1 이상, 100 이하인 배열입니다.
- arr의 원소는 -10,000 이상 10,000 이하인 정수입니다.

<br/>

## 입출력 예
| arr | return |
|------|---|
|[1,2,3,4]|2.5|
|[5,5]	|5|



<br/>

## Solution

```swift
func solution(_ arr:[Int]) -> Double {
    
    var result : Double = 0.0
    
    for i in 0 ..< arr.count {
        result += Double(arr[i])
    }
    result = result / Double(arr.count) 
    
    return result
}
```

```swift
func solution(_ arr:[Int]) -> Double {

    return Double(arr.reduce(0,+))/Double(arr.count)
}

```

<br/>

## Check
- 연산자는 중위 연산자로 왼쪽 값이 $0, 오른쪽 값이 $1임을 추론 가능하므로 다음과 같이 생략 가능합니다.

		array.reduce( 0, + )

    만일 initial 값이 0이라면 초기 항목은 {0 + 1}입니다. 값이 1이라면 {1 + 1} 입니다.
