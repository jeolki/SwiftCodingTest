# 2016년

## 문제 설명 
2016년 1월 1일은 금요일입니다. 2016년 a월 b일은 무슨 요일일까요? 두 수 a ,b를 입력받아 2016년 a월 b일이 무슨 요일인지 리턴하는 함수, solution을 완성하세요. 요일의 이름은 일요일부터 토요일까지 각각 `SUN,MON,TUE,WED,THU,FRI,SAT`

입니다. 예를 들어 a=5, b=24라면 5월 24일은 화요일이므로 문자열 "TUE"를 반환하세요.

<br/>

## 제한 조건
- 2016년은 윤년입니다.
- 2016년 a월 b일은 실제로 있는 날입니다. (13월 26일이나 2월 45일같은 날짜는 주어지지 않습니다)

<br/>

## 입출력 예
| a | b | return |
|------|---|---|
|5|24|"TUE"|


<br/>

## Solution

```swift
func solution(_ a:Int, _ b:Int) -> String {
    
    let day = ["SUN","MON","TUE","WED","THU","FRI","SAT"]
    let month = [31,29,31,30,31,30,31,31,30,31,30,31]
    
    var daynumber = 5
    for i in 0..<a-1{
        daynumber += month[i]
    }
    
    daynumber += b-1
    
    
    return "\(day[daynumber%7])"
}
```

```swift
func solution(_ a:Int, _ b:Int) -> String {

    let w = ["THU", "FRI", "SAT", "SUN", "MON", "TUE", "WED"]
    let monthDay = [ 31, 29, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
    let totalDay = monthDay[0..<a-1].reduce(0, +) + b

    return w[totalDay % 7]
}
```

<br/>

## Check
- 요일이 담겨있는 배열과 윤영일때 각 월별 일수를 담겨있는 배열을 만듭니다
-  daynumber를 만들어 주고 시작값을 1월 1일 금요일에 맞춰 4로 설정합니다
-  for를 월 바로 앞 (a-1) 까지 돌려줍니다. 그 안에서 daynumber에 각 월 별 일수를 더해줍니다.
-  for문을 나와 daynumber에 마저 b까지 더해줍니다 ( -1을 하는 이유는 월 별 일수를 더해주면 1일 이기 때문에 1일을 빼줍니다.)
-  7을 나눠서 남을 요일을 반환하게 합니다.