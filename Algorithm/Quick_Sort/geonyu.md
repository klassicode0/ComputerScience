# Quick Sort

> 불안정 정렬+비교정렬+분할정복

## 과정(오름차순 기준)

1. 리스트에 있는 한 요소를 선택한다. (피벗을 선택)
2. 피벗을 기준으로 피벗보다 작은 요소들은 모두 피벗의 왼쪽으로, 큰 요소들은 오른쪽으로 옮겨진다.
3. 피벗을 제외한 왼쪽 리스트와 오른쪽 리스트를 다시 정렬한다.
4. 분할이 불가능할 때까지 반복한다.



## 특징

### 시간 복잡도

- 최선의 경우 T(n)=**O(nlog₂n)** 
- 최악의 경우 T(n) = **O(n^2)**
- 평균 T(n) = **O(nlog₂n)**이지만 그래도 같은 평균 시간 복잡도에서의 알고리즘과 비교했을 때도 빠르다.

### 장점

- 속도가 빠르다
- 추가 메모리 공간을 필요로 하지 않는다.

### 단점

- 이미 정렬된 리스트에 대해서는 수행시간이 더 많이 걸린다.