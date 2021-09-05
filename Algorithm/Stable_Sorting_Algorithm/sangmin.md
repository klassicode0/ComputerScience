# Sorting Algorithm에서 stable 하다는 것은 무엇을 의미하나요?

정렬 알고리즘을 사용하고 난 후 배열에서 중복된 값의 순서가 변하지 않으면 stable한 정렬 알고리즘이라고 말할 수 있습니다.
예를 들면, 어떠한 길이가 5인 배열이 있고 1이라는 값이 0번째와 3번째에 존재한다고 가정해보겠습니다. 이러한 상황에서는 0번째 1이 첫 번째 1이고 3번째 인덱스에 있는 1이 두 번째 1입니다.
정렬 알고리즘을 통해 정렬을 완료한 후 1들중에 첫 번째 였던 1이 그대로 첫 번째이고 두 번째였던 1이 두 번째이면 해당 알고리즘은 stable한 알고리즘이라고 볼 수 있습니다.

### 종류는?

Insertion Sort, Merge Sort, Bubble Sort, Counting Sort가 있습니다.

아닌 것은, Selection sort, Heap Sort, Shell Sort, Quick Sort가 있습니다.
