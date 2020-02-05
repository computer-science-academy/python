## 논리 연산(Boolean Operations)

### 연산자
수학에서와 마찬가지로, 각 논리 연산자의 우선순위는 직관적입니다.
- `not`
  + 셋 중 가장 우선순위가 높은 부정 단항연산자.
  + 피연산자의 `bool` 타입 값이 `True`면 `False`를, `False`면 `True`를 반환
- `and`
  + 두번째로 우선순위가 높은 논리곱 이항연산자.
  + 왼쪽 피연산식을 평가 후 그 결과의 `bool` 타입 값이 `True`면 평가결과를 반환
  + 그렇지 않으면 오른쪽 피연산식을 평가 후 그 결과를 반환
- `or`
  + 셋 중 가장 우선순위가 낮은 논리합 이항연산자.
  + 왼쪽 피연산식을 평가 후 그 결과의 `bool` 타입 값이 `False`면 평가 결과를 반환
  + 그렇지 않으면 오른쪽 피연산식을 평가 후 그 결과를 반환

### 단락평가(short-circuit evaluation)
많은 언어에서 단락평가 지원을 위해 논리연산자에 대해서는 평가 순서를 보장합니다(그 외에는 최적화 등을 위해 평가 순서가 보장되지 않는 경우가 많습니다). 단락평가는 일부 피연산자를 통해 최종 값이 확정이 될 때에, 더 이상의 피연산자를 평가하지 않고 바로 값을 반환하는 평가방식을 의미합니다.

### 반환값
파이썬에서는 `and` 및 `or` 연산의 반환값이 `True` / `False`로 한정되지 않습니다. 마지막에 평가된 피연산자를 반환하게 되어있는데, 이 부분을 유용하게 활용할 수 있습니다.

### 참고
- [파이썬 튜토리얼 > 자료구조 > 조건 더보기](https://docs.python.org/ko/3/tutorial/datastructures.html?highlight=short%20circuit#more-on-conditions)
- [파이썬 언어 레퍼런스 > 표현식 > 논리 연산](https://docs.python.org/ko/3/reference/expressions.html#boolean-operations)
