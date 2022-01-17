# 행렬의 덧셈

## 문제 설명 
행렬의 덧셈은 행과 열의 크기가 같은 두 행렬의 같은 행, 같은 열의 값을 서로 더한 결과가 됩니다. 2개의 행렬 arr1과 arr2를 입력받아, 행렬 덧셈의 결과를 반환하는 함수, solution을 완성해주세요. 

<br/>
## 제한 조건   
- 행렬 arr1, arr2의 행과 열의 길이는 500을 넘지 않습니다.

<br/>
## 입출력 예    
| arr1 | arr2 | return |
|------|---|---|
|[[1,2],[2,3]]|[[3,4],[5,6]]|[[4,6],[7,9]]|
|[[1],[2]]|[[3],[4]]|[[4],[6]]|


<br/>
## Solution    

```swift
func solution(_ arr1:[[Int]], _ arr2:[[Int]]) -> [[Int]] {
    
    var arr = Array(repeating:Array(repeating: 0, count: arr1[0].count), count: arr1.count)
    
    for i in 0 ..< arr.count {
        for j in 0 ..< arr[0].count {
            arr[i][j] = arr1[i][j] + arr2[i][j]
        }
    }
    
    return arr
}
```

```swift
import Foundation

func solution(_ arr1:[[Int]], _ arr2:[[Int]]) -> [[Int]] {
    return zip(arr1, arr2).map{zip($0,$1).map{$0+$1}}
}
```

<br/>
## Check    
- Array(repeating:Array(repeating: 0, count: 3), count: 3) : 크기가 정해져 있는 배열 생성하기