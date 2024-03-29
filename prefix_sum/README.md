# Prefix Sum 

구간 합 알고리즘이란 수들의 나열에서 특정 구간의 합을 의미한다. 특정 구간은 일차원 배열인 경우가 일반적이나 이차원 배열의 경우에도 특정 구간을 제한하여 합을 구하는 알고리즘이라면 충분히 활용가능하다.  

구간 합 알고리즘의 포인트는 __미리 계산하기__ 이다. 시간복잡도가 높아서 시간이 초과될 경우에는 아예 다른 알고리즘을 고려해야하는 경우가 많은데 구간 합의 경우에는 메모리를 사용하여 계산의 양을 상수 시간으로 줄일 수 있다.

## 접근방식 떠올리기
k번째 부터 l번쨰 숫자를 모두 더하는 방법은 배열을 순서대로 참조했다는 가정하에 O(n)번의 시간복잡도를 가진다. 구간 합 알고리즘을 사용하면 상수시간으로 줄일 수 있으므로 특정 구간의 합을 구하는 알고리즘에서 시간복잡도를 줄여야 할 경우 메모리를 사용하여 미리 계산하는 방식을 떠올리자. 

### 백준 11658번 - 구간 합 구하기 4
> 1 ≤ N ≤ 100,000  
1 ≤ M ≤ 100,000

n 개의 배열의 특정 구간의 합을 m번 계산하는 문제이다. 이중 반복문으로 해당 문제를 해결하게 된다면 최대 초당 100번의 계산이 이루어진다. 이 경우 구간 합 알고리즘의 prefix 기법을 사용하면 구간합 계산은 O(1)로 상수시간으로 줄어들며 이를 m번 계산하므로 총 시간복잡도는 O(m)이므로 1초 제한을 통과할 수 있다.