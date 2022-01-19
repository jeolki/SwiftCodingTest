# 문자열 다루기 기본

## 문제 설명 
문자열 s의 길이가 4 혹은 6이고, 숫자로만 구성돼있는지 확인해주는 함수, solution을 완성하세요. 예를 들어 s가 "a234"이면 False를 리턴하고 "1234"라면 True를 리턴하면 됩니다.

<br/>

## 제한 조건
- s는 길이 1 이상, 길이 8 이하인 문자열입니다.

<br/>

## 입출력 예
| arr1 | return |
|------|---|
|"a234"|false|
|1234|true|


<br/>

## Solution

```swift
func solution(_ s:String) -> Bool {
    return (s.count == 4 || s.count == 6) 
            && (Int(s) ?? nil != nil ? true : false)
}
```

```swift
func solution(_ s:String) -> Bool {
    return (Int(s) != nil && (s.count == 4 || s.count == 6)) ? true : false
}
```

<br/>

## Check
- Int()를 통해서 문자가 포함되어 있는지 확인, count를 통해서 문자열의 길이확인
