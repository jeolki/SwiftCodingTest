# 최대공약수와 최소공배수

## 문제 설명 
두 수를 입력받아 두 수의 최대공약수와 최소공배수를 반환하는 함수, solution을 완성해 보세요. 배열의 맨 앞에 최대공약수, 그다음 최소공배수를 넣어 반환하면 됩니다. 예를 들어 두 수 3, 12의 최대공약수는 3, 최소공배수는 12이므로 solution(3, 12)는 [3, 12]를 반환해야 합니다.

<br/>

## 제한 조건
- 두 수는 1이상 1000000이하의 자연수입니다.

<br/>

## 입출력 예
| n | m | return |
|------|---|---|
|3|12|[3, 12]|
|2|5|[1, 10]|



<br/>

## Solution

```swift
func gcd(_ a: Int, _ b: Int) -> Int {
    let mod: Int = a % b
    return mod == 0 ? min(a, b) : gcd(b, mod)
}
 
func lcm(_ a: Int, _ b: Int) -> Int {
    return a * b / gcd(a, b)
}
 
func solution(_ n:Int, _ m:Int) -> [Int] {
    return [gcd(n, m), lcm(n, m)]
}
```


<br/>

## Check
- 최대공약수와 최소공배수를 구하는 함수 만들기
-  두 수를 나누어 0이 아니면 최소값이 최소공약수 아니면 계속 나누어 준다
-  최소공배수는 두 수를 곱한값에 최대공약수를 나눈 값
