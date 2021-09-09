대부분은 sort를 쓰면 된다. 그러나 특별한 상황에선 이분탐색을 쓸수도 있으니 이 두개가 제일 중요한 것 같다. (개인적인 생각)



그래도 기본적으로 알고있어야할 지식 같은거니까 정리하자.



# sort ()





# 이분 탐색 (Binary Search)

- 결정 알고리즘으로 사용 됨



## 코드

```javascript
function binarySearch(n, arr) {
  let start = 0;
  let end = arr.length - 1;
  while (start <= end) {
    let mid = Math.floor((start + end) / 2);
    if (arr[mid] === n) {
      return '1';
    } else if (arr[mid] < n) {
      start = mid + 1;
    } else {
      end = mid - 1;
    }
  }
  return '0';
}
```





# 모두 오름차순으로 정렬하는 예시



# 선택 정렬

- 시간 복잡도
  - Best : n^2
  - Avg : n^2
  - Worst : n^2



- 제자리 정렬 (in-place sorting) 알고리즘의 하나
  - 입력 배열(정렬되지 않은 값들) 이외에 다른 추가 메모리를 요구하지 않는 정렬 방법
- 해당 순서에 원소를 넣을 위치는 이미 정해져 있고, 어떤 원소를 넣을지 선택하는 알고리즘
  - 첫 번째 순서에는 첫 번째 위치에 가장 최솟값을 넣는다.
  - 두 번째 순서에는 두번째 위체에 남은 값 중에서의 최솟값을 넣는다.
  - ... 끝까지
- 과정 설명
  1. 주어진 배열 중에서 최솟값을 찾는다.
  2. 그 값을 맨 앞에 위치한 값과 교체한다 (패스)
  3. 맨 처음 위치를 뺀 나머지 리스트를 같은 방법으로 교체한다
  4. 하나의 원소만 남을 때 까지 위으 1~3 과정을 반복한다.



- 설명 출처
  - https://gmlwjd9405.github.io/2018/05/06/algorithm-selection-sort.html

## 코드

```javascript
function selectionSort (arr) {
  let result = arr;
  for (let i = 0; i < arr.length; i++) {
    let idx = i;
    for (let j = i + 1; j < arr.length; j++) {
      if (arr[j] < arr[idx]) idx = j;
    }
    [arr[i], arr[idx]] = [arr[idx], arr[i]]
  }
  return result;
}

const arr = [13, 5, 11, 7, 23, 15];
console.log(selectionSort(arr));

```





# 버블 정렬

- 시간 복잡도
  - Best : n^2
  - Avg : n^2
  - Worst : n^2

- 서로 인접한 두 원소를 검사하여 정렬하는 알고리즘

  - 인접한 2개의 레코드를 비교하여 크기가 순서대로 되어 있지 않으면 서로 교환한다.

- 선택 정렬과 기본 개념이 유사하다

- 구현

  - 첫번째 자료와 두 번째 자료를, 두 번째 자료와 세 번째 자료를, 세 번째와 네 번째를, ... 이런 식으로 마지막 - 1 번쨰 자료와 마지막 자료를 비교하여 교환하면서 자료를 정렬
  - 1회전을 수행하고 나면 가장 큰 자료가 맨 뒤로 이동하므로 2회전에서는 맨 끝에 있는 자료는 정렬에서 제외되고, 2회전을 수행하고 나면 끝에서 두 번째 자료까지 정렬에서 제외된다. 이렇게 정렬을 1회전 수행할 때마다 정렬에서 제외되는 데이터가 하나씩 늘어난다.

  

- 설명 출처

  - https://gmlwjd9405.github.io/2018/05/06/algorithm-selection-sort.html

## 코드

```javascript
function bubbleSort(arr) {
  let result = arr;
  for (let i = 0; i < arr.length; i++) {
    for (let j = 0; j < arr.length - i - 1; j++) {
      if (arr[j] > arr[j + 1]) {
        [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
      }
    }
  }
  return result;
}
const arr = [13, 5, 11, 7, 23, 15];
console.log(bubbleSort(arr));
```











# 삽입 정렬

- 시간 복잡도
  - Best : n^2
  - Avg : n^2
  - Worst : n^2





# 셀 정렬



# 퀵 정렬



# 힙 정렬



# 병합 정렬

