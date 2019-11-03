### 증분 할당문(Augmented assignment statement)

다음 연산자들은 각각 해당 연산자 우측에 할당 구분자와 같은 `=`를 붙이면 증분 할당 구분자(delimiter)가 됩니다.
- 비트 이항연산자(`^`, `|`, `&`)
- 시프트 연산자(`<<`, `>>`)
- 산술 이항 연산자(`+`, `-`, `*`, `/`, `**`, `//`, `@`, `%`)

증분 할당 구분자는 연산의 역할도 수행하긴 하지만, 문법적으로는 할당 구분자처럼 구분자이기 때문에 표현식(expression)에 등장할 수 없습니다.
증분 할당문은 일반 할당문으로 비슷하게 풀어쓸 수 있기는 하지만,
[표준 문서](https://docs.python.org/ko/3/reference/simple_stmts.html#augmented-assignment-statements)
에도 나와있듯이 증분할당은 일반 할당과 같지는 않습니다.

```python
a = a_ = [1]
b = b_ = [1]

a = a + [2]
b += [2]

print(a is a_)
print(b is b_)
print(a, a_)
print(b, b_)
```

증분할당의 경우, 재할당 없이 해당 연산을 수행할 수 있다면 in-place로 연산이 이뤄집니다.
대표적으로는 `list`나 `set`의 연산이 이에 해당됩니다.
그렇지만 `int`의 경우 재할당이 반드시 필요하기 때문에, 이에 해당되지 않습니다.

```python
class Foo:
    x = [1]
    y = 1

foo = Foo()
foo.x += [1]
foo.y += 1

print(Foo.x is foo.x)
print(Foo.y is foo.y)
print(Foo.x, foo.x)
print(Foo.y, foo.y)
```
